# ESP32 Environmental Control Architecture

## 1 Purpose

This document defines the ESP32-based environmental control architecture for the Fungi4u fruiting room.

The document defines:

* environmental sensing
* environmental monitoring
* humidity control
* environmental telemetry
* commissioning responsibilities
* future automation boundaries
* environmental authority rules

This document does not define:

* physical room construction
* plenum construction
* duct design
* production management
* yield analytics
* business logic

Physical environmental architecture is defined in:

`ENVIRONMENTAL_SYSTEM_ARCHITECTURE.md`

---

# 2 Architectural Role

The ESP32 controller is architecturally defined as:

> Environmental Monitoring and Humidity Control Controller

The controller is responsible for:

* environmental sensing
* humidity control
* environmental telemetry
* future automation integration

The controller is not initially responsible for:

* fresh-air control
* circulation-fan control
* CO₂ control
* air-conditioner control

The design prioritizes successful environmental commissioning before advanced automation.

---

# 3 Environmental Control Philosophy

The environmental control philosophy is based on:

* environmental stability
* gradual environmental change
* simple control loops
* low operational complexity
* commissioning before automation

The architecture assumes:

* the plenum performs environmental mixing
* the duct system distributes conditioned air
* circulation is continuous
* environmental changes propagate gradually through the room

The design intentionally avoids:

* aggressive environmental correction
* unnecessary automation
* complex control loops during commissioning

The primary objective of the environmental system is:

* improved yield
* improved mushroom quality
* improved production consistency

Environmental monitoring and automation exist to support these objectives.

---

# 4 Environmental Authority Model

## 4.1 Environmental Priority Hierarchy

The environmental control architecture shall apply the following priority order:

1. Temperature
2. CO₂
3. Humidity

The purpose of this hierarchy is to maintain stable fruiting conditions while minimizing operational risk and control-system complexity.

---

## 4.2 Conflict Resolution

### Temperature versus Humidity

Temperature takes precedence over humidity.

Humidity may temporarily deviate from target values when required to maintain acceptable temperature conditions.

### CO₂ versus Temperature

CO₂ takes precedence over temperature during normal operation.

However, approved temperature safety limits override CO₂ control requirements.

The controller shall not permit unsafe temperature excursions solely to achieve CO₂ targets.

---

## 4.3 Sensor Authority

Environmental control decisions shall be based on a designated Primary Sensor.

The Primary Sensor is selected by configuration rather than hardware type.

The Primary Sensor is authoritative for:

* environmental control decisions
* environmental operating-state determination
* environmental alarm evaluation

Additional sensors may be used for:

* validation
* comparison
* commissioning
* diagnostics
* future redundancy

Validation sensors are not authoritative unless explicitly promoted to Primary Sensor status.

---

## 4.4 Sensor Failure Behaviour

If the Primary Sensor becomes unavailable:

1. Transfer authority to an approved fallback sensor if available.
2. Raise a critical environmental alarm.
3. Record the sensor-failure event in telemetry.

If no approved fallback sensor exists:

1. Enter Safe Mode.
2. Maintain conservative environmental operation.
3. Raise a critical alarm requiring operator attention.

Operation using stale sensor values is not considered an approved control strategy.

---

## 4.5 System Responsibility Boundaries

### ESP32 Responsibilities

The ESP32 controller is responsible for:

* environmental sensing
* real-time environmental control
* safety limits
* environmental operating states
* autonomous operation during Home Assistant outages

Environmental control must remain functional when Home Assistant, Wi-Fi, or external services are unavailable.

### Home Assistant Responsibilities

Home Assistant is responsible for:

* supervision
* dashboards
* alarms
* operator interaction
* configuration management

Home Assistant is not required for basic environmental control operation.

### Supabase Responsibilities

Supabase is responsible for:

* historical environmental records
* reporting
* analytics
* future operational intelligence

Supabase is not part of the real-time environmental control path.

---

# 5 Initial Implementation Scope

## Included

* ESP32 controller
* Room temperature and humidity sensor
* Second temperature and humidity sensor
* Door sensor
* Humidifier control
* Environmental telemetry
* Home Assistant integration

## Excluded

* CO₂ sensor integration
* Automatic fresh-air control
* Automatic circulation-fan control
* Air-conditioner integration
* Yield analytics
* Production analytics
* Advanced environmental optimization

---

# 6 Sensor Architecture

## 6.1 Room Authority Sensor

Purpose:

Authoritative environmental measurement for humidity control.

Responsibilities:

* humidity control reference
* environmental telemetry
* operational monitoring

Recommended placement:

* representative fruiting location
* protected from direct water droplets
* protected from direct supply airflow

The Room Authority Sensor is the environmental control reference during Phase 1 operation.

---

## 6.2 Validation Sensor

Purpose:

Validate environmental behaviour within the fruiting room.

Responsibilities:

* environmental comparison
* airflow validation
* commissioning support
* environmental uniformity assessment

The Validation Sensor is not initially used for control decisions.

The Validation Sensor exists to answer questions such as:

* Is the room becoming more uniform?
* Is the airflow architecture functioning as intended?
* Are temperature differences acceptable?
* Are humidity differences acceptable?

Final long-term placement remains subject to commissioning results.

Possible future locations include:

* secondary room position
* plenum position
* supply-air position

---

## 6.3 Door Sensor

Purpose:

Detect room-access events and environmental disturbances.

Responsibilities:

* door-state telemetry
* environmental event correlation
* commissioning support
* operational monitoring

Phase 1 Behaviour:

* telemetry only
* event detection only

The door sensor is not initially used to trigger automatic environmental behaviour.

Future Expansion:

* Access Mode
* Recovery Mode
* alarm suppression
* disturbance analysis
* environmental recovery optimization

The door sensor is considered part of the intended environmental-control architecture.

---

# 7 Actuator Architecture

## 7.1 Humidifier Control

Purpose:

Primary humidity-correction actuator.

Implementation:

* ESP32 controlled
* Sonoff switched
* ultrasonic humidification within the plenum

Control philosophy:

* simple hysteresis control
* gradual environmental correction
* no PID control during initial implementation

Initial operating philosophy:

* humidifier ON below lower threshold
* humidifier OFF above upper threshold

Exact thresholds remain configurable.

---

## 7.2 Fresh-Air Fan

Purpose:

Provide controllable fresh-air introduction into the plenum.

Architecture:

* fresh air enters the plenum
* fresh air mixes with conditioned return air
* mixed air enters the supply duct system

Control Authority:

Phase 1:

* manual adjustment

Feedback Source:

* Inkbird CO₂ monitor

Future automation remains outside the initial implementation scope.

---

## 7.3 Circulation Fan

Purpose:

Provide continuous environmental circulation.

Responsibilities:

* move air from return duct
* move air through plenum
* distribute conditioned air through supply duct

Control Authority:

Phase 1:

* manually commissioned operating speed

The circulation fan is not initially controlled by the ESP32.

The relationship between circulation speed, environmental uniformity, and yield remains subject to validation.

Future automation remains an open design decision.

---

# 8 Environmental Operating Model

## 8.1 Commissioning Mode

Purpose:

Validate the environmental architecture.

Objectives:

* validate airflow behaviour
* validate humidity control
* validate environmental uniformity
* validate fresh-air strategy

Characteristics:

* manual fan adjustment
* operator-guided CO₂ management
* environmental observation

---

## 8.2 Stable Fruiting Mode

Purpose:

Normal fruiting operation.

Characteristics:

* continuous circulation
* automatic humidity control
* environmental telemetry
* manual fresh-air adjustment

The objective is environmental stability rather than aggressive correction.

---

# 9 Telemetry Philosophy

The ESP32 shall provide telemetry to Home Assistant.

Telemetry may include:

* room temperature
* room humidity
* validation-sensor temperature
* validation-sensor humidity
* door state
* humidifier state
* controller health

Telemetry exists to support:

* commissioning
* troubleshooting
* environmental understanding

Telemetry does not replace operational observation of mushroom performance.

---

# 10 Future Expansion

Potential future developments include:

* CO₂ sensing
* automatic fresh-air control
* automatic circulation-fan control
* air-conditioner integration
* plenum instrumentation
* environmental data logging
* alarm escalation
* adaptive environmental control
* Access Mode
* Recovery Mode

Future expansion shall preserve:

* simplicity
* maintainability
* environmental stability
* yield-focused operation

Automation shall be introduced only when supported by operational evidence.

---

# 11 Open Questions

The following areas remain open:

* final second-sensor placement
* exact humidity-control thresholds
* optimal circulation-fan speed
* optimal fresh-air fan speed
* duct airflow distribution
* environmental response timing
* humidifier carry-over behaviour
* long-term circulation tuning
* future CO₂-control strategy
* future air-conditioner integration strategy
* future door-event handling strategy

These questions are expected to be resolved through commissioning and operational experience.

---

# 12 Revision History

v1

Initial architecture publication.

v2

Refined environmental monitoring and humidity-control architecture.

v3

Added Environmental Authority Model.

Defined:

* environmental priority hierarchy
* conflict resolution rules
* sensor authority model
* sensor failure behaviour
* ESP32 / Home Assistant / Supabase responsibility boundaries

Resolved Home Assistant supervisory-role governance question.

