# ESP32 Environmental Control Architecture

## 1 Purpose

This document defines the initial ESP32-based environmental control architecture for the Fungi4u fruiting room.

The document separates:

* physical environmental architecture
  from:
* environmental control-system architecture.

The purpose of the control system is to:

* maintain stable fruiting conditions,
* support continuous environmental circulation,
* manage operational disturbances,
* provide supervisory environmental control,
* support future Home Assistant integration,
* and provide a stable foundation for future automation expansion.

This document does not define:

* stock-control logic,
* business logic,
* economic logic,
* or production analytics.

---

# 2 Architectural Role

The ESP32 controller is architecturally defined as:

> Environmental State Controller

The controller supervises:

* environmental sensing,
* humidification control,
* circulation control,
* disturbance handling,
* recovery handling,
* and telemetry reporting.

The ESP32 operates within the environmental conditioning architecture defined by the plenum and circulation system.

---

# 3 Environmental Control Philosophy

The environmental control philosophy is based on:

* continuous low-speed circulation,
* gradual environmental adjustment,
* distributed airflow,
* low turbulence near mushroom surfaces,
* and environmental stability rather than aggressive correction.

The control architecture assumes:

* the plenum performs primary air mixing,
* the duct system distributes conditioned air evenly,
* environmental changes propagate gradually through the room,
* and continuous circulation is preferable to intermittent airflow.

The design intentionally avoids:

* rapid environmental cycling,
* aggressive airflow modulation,
* and unstable correction loops.

---

# 4 Initial Implementation Scope

## Included

* ESP32 controller
* Room DHT22 sensor
* Supply/plenum DHT22 sensor
* Door sensor
* Variable-speed circulation fan control
* Humidifier relay control
* Home Assistant telemetry integration

## Excluded

* CO₂ sensor integration
* Automatic fresh-air control
* IR air-conditioner integration
* Yield analytics
* Production analytics

---

# 5 Sensor Architecture

## 5.1 Room Reference Sensor

Hardware:
DHT22

Purpose:
Authoritative room-condition measurement.

Responsibilities:

* humidity control reference
* room-condition telemetry
* environmental history
* operational monitoring

Recommended placement:

* canopy height
* central fruiting zone
* protected from direct supply airflow
* protected from direct water droplets

---

## 5.2 Supply / Plenum Sensor

Hardware:
DHT22

Purpose:
Observe conditioned air leaving the plenum.

Responsibilities:

* conditioned-air observation
* humidification behaviour observation
* environmental transport observation
* plenum stability observation

The supply/plenum sensor is not intended as a redundancy sensor.

Recommended placement:

* upper plenum chamber
  or
* supply duct entry region.

---

## 5.3 Door Sensor

Purpose:
Detect operational disturbance events.

Responsibilities:

* activate Access Mode
* activate Recovery Mode
* distinguish environmental drift from operator disturbance

The door sensor is considered part of the first implementation phase.

---

# 6 Actuator Architecture

## 6.1 Variable-Speed Circulation Fan

Purpose:
Primary airflow-conditioning actuator.

The circulation fan:

* pulls return air from the fruiting room,
* pushes air into the plenum,
* influences circulation intensity,
* influences environmental transport rate,
* and influences plenum pressure behaviour.

Control philosophy:

* continuous operation
* low-speed baseline operation
* gradual modulation only
* no aggressive cycling

Initial design assumptions:

* moderate baseline speed
* elevated recovery speed after disturbances
* stable airflow preferred over rapid correction

---

## 6.2 Humidifier Relay

Purpose:
Primary humidity-correction actuator.

The humidifier introduces ultrasonic fog into the lower plenum chamber.

Initial control philosophy:

* simple hysteresis control
* no PID control initially

Reasoning:
The plenum and duct architecture already introduce environmental smoothing and transport delay.

Initial design targets:

* humidifier ON below lower humidity threshold
* humidifier OFF above upper humidity threshold

Exact thresholds remain configurable.

---

# 7 Environmental State Model

## 7.1 Stable Fruiting Mode

Purpose:
Normal fruiting operation.

Characteristics:

* door closed
* continuous circulation
* automatic humidity control
* standard telemetry behaviour

---

## 7.2 Access Mode

Purpose:
Manage environmental disturbance during room access.

Activated when:

* door opens.

Typical behaviour:

* humidity correction limited or paused
* fan held at moderate stable speed
* temporary alarms suppressed

Purpose:
Prevent unstable environmental over-correction during operator access.

---

## 7.3 Recovery Mode

Purpose:
Restore environmental stability after door closure.

Activated when:

* door closes after Access Mode.

Typical behaviour:

* elevated circulation speed
* humidification enabled
* temporary stabilization period

Recovery timing remains configurable.

---

## 7.4 Safe Mode

Purpose:
Provide stable fallback behaviour during sensing failure.

Activated when:

* critical environmental sensing becomes invalid.

Typical behaviour:

* humidifier disabled
* safe circulation maintained
* alarm state raised

---

# 8 Telemetry Philosophy

The ESP32 controller is intended to provide telemetry to Home Assistant.

Telemetry responsibilities include:

* room temperature
* room humidity
* supply/plenum temperature
* supply/plenum humidity
* door state
* fan state
* humidifier state
* environmental operating state
* alarm state

The ESP32 provides environmental telemetry only.

Business logic and production logic remain external to the environmental controller.

---

# 9 Future Expansion

Potential future developments include:

* CO₂ sensing
* automated fresh-air control
* motorized dampers
* advanced circulation control
* air-conditioner integration
* environmental data logging
* alarm escalation
* adaptive environmental control
* airflow balancing refinement

Future expansion must preserve:

* architectural separation,
* environmental stability,
* and operational simplicity.

---

# 10 Open Questions

The following areas still require validation or refinement:

* exact environmental sensor placement
* recovery-mode timing
* fan-control implementation method
* airflow balancing inside ducts
* condensation behaviour inside plenum and ducts
* environmental response timing
* humidifier carry-over behaviour
* long-term circulation tuning
* Home Assistant supervisory role definition

