# Fruiting Room Environmental Design

## 1 Purpose

This document defines the physical environmental architecture of the Fungi4u fruiting room.

It serves as the authoritative description of:

* room environmental design
* airflow architecture
* environmental conditioning architecture
* plenum architecture
* fresh-air architecture
* environmental assumptions
* commissioning philosophy
* future environmental expansion

The document exists to support:

* future upgrades
* maintenance
* troubleshooting
* environmental-control development
* ESP32 integration
* Home Assistant integration
* project continuity after interruptions in development

This document defines physical environmental architecture only.

Environmental control-system behaviour is defined separately in:

`ESP32_Environmental_Control_Architecture.md`

---

# 2 System Intent

The fruiting room exists to provide a controlled fruiting environment for grey oyster mushrooms.

The primary objective of the environmental system is:

* improved yield
* improved mushroom quality
* improved production consistency

The environmental architecture supports this objective through:

* stable humidity
* controlled temperature distribution
* low-velocity airflow
* controlled fresh-air introduction
* environmental uniformity
* gradual environmental stabilization

The design prioritizes:

* soft continuous circulation
* environmental stability
* distributed airflow
* plenum-based environmental conditioning
* maintainability
* future automation compatibility

The architecture assumes that environmental stability is achieved primarily through:

* continuous circulation
* conditioned air distribution
* gradual environmental adjustment
* environmental mixing

rather than through aggressive environmental correction.

---

# 3 Building Description

The fruiting room is located within the outbuilding behind the main house.

The building:

* has a flat corrugated iron roof

* is approximately rectangular

* is approximately:

  * 4650 mm on the shorter side
  * 7000 mm on the longer side

* shares one side wall with the boundary wall

The fruiting room occupies the left-hand side of the outbuilding.

The space originated as a drive-through garage structure and was later converted into a mushroom-production environment.

Construction details:

* external walls approximately 250 mm thick
* internal partition wall approximately 75 mm thick

Ceiling height:

* front approximately 2720 mm
* rear approximately 2550 mm

---

# 4 Fruiting Room Construction

## Front Wall

The front garage door remains in place and is insulated internally using:

* 100 mm Isoboard insulation

At floor level:

* a gap of approximately 50 mm remains
* the gap is covered by a perforated aluminium plate

The perforated opening functions as a passive exhaust path.

---

## Rear Wall

The rear garage opening has been closed using:

* insulated dry-wall construction
* Isoboard insulation

An insulated access door is positioned centrally.

---

## Air Conditioner Position

The air-conditioner is mounted:

* above the rear access door
* on the internal wall surface

The air-conditioner currently operates independently of the environmental-control system.

Future integration remains possible.

---

## Interim Divider Wall

The room currently operates in an interim configuration.

The divider separates:

* fruiting room
* grow room

The divider is insulated and includes a centrally positioned access door.

During this phase:

* airflow ducts remain installed
* unused duct openings remain sealed

Future full-room conversion remains planned.

---

# 5 Environmental Design Philosophy

The environmental design is based on:

* continuous low-velocity circulation
* environmental stability
* distributed airflow
* environmental mixing
* gradual environmental correction
* low turbulence near mushroom surfaces
* modular future expansion

The system is designed to:

* avoid direct airflow onto mushrooms
* reduce environmental stratification
* reduce dead zones
* improve environmental consistency
* improve production consistency

The design assumes that:

* proper air mixing is more important than high airflow volume
* stable conditions are preferable to aggressive correction
* continuous circulation is preferable to intermittent high-speed airflow

The architecture is intended to improve yield through improved environmental consistency.

---

# 6 Airflow Architecture

The airflow system is based on a circulation loop centred around the plenum.

Primary airflow path:

1. Air is collected through the low-level return duct.
2. Air enters the circulation fan.
3. Air is delivered into the plenum.
4. Air is mixed and conditioned within the plenum.
5. Conditioned air enters the ceiling-level supply duct.
6. Air returns through the room volume toward the return duct.

The plenum functions as the central environmental conditioning hub.

The airflow architecture is intended to create:

* gentle circulation
* environmental uniformity
* stable environmental transport
* low directional airflow stress on mushrooms

The architecture prioritizes environmental consistency over airflow intensity.

---

# 7 Plenum Specification

## General Construction

The plenum is the central environmental conditioning component.

Approximate dimensions:

* 520 mm × 520 mm
* 660 mm high

Construction:

* 12 mm plywood
* waterproofed internally and externally

The plenum is mounted:

* near ceiling level
* on the right-hand wall

The plenum functions as:

* environmental mixing chamber
* humidification chamber
* fresh-air mixing chamber
* pressure equalization chamber
* supply-air preparation chamber

---

## Drainage Design

The plenum includes:

* sloped internal base
* drain outlet
* drain trap

The trap prevents unwanted air leakage.

The base panel remains removable for:

* inspection
* cleaning
* maintenance

---

## Internal Configuration

The plenum is divided into:

* lower chamber
* upper chamber

A central baffle separates the chambers while permitting controlled airflow transfer.

---

## Lower Chamber Functions

The lower chamber contains:

* circulation-air inlet
* fresh-air inlet
* airflow baffles
* water reservoir
* float valve
* ultrasonic humidifier

The lower chamber functions as:

* environmental mixing chamber
* humidification chamber

---

## Upper Chamber Functions

The upper chamber distributes conditioned air into the supply duct system.

The upper chamber functions as:

* pressure equalization zone
* conditioned-air stabilization zone
* air distribution chamber

---

# 8 Ducting Specification

The duct system uses:

* 110 mm PVC drain pipe

Two primary duct runs are used.

## Low-Level Return Duct

Location:

* along the lower section of one wall

Function:

* collect room air
* deliver room air to the circulation fan

---

## High-Level Supply Duct

Location:

* along the upper section of the opposite wall

Function:

* distribute conditioned air

---

## Air Distribution Holes

The ducts use distributed 10 mm holes.

Purpose:

* reduce local air velocity
* distribute airflow
* improve environmental consistency
* reduce directional airflow stress

The final hole pattern remains subject to operational validation.

---

# 9 Air Movement Strategy

Air movement is generated by:

* variable-speed circulation fan

The circulation fan:

* extracts air from the return duct
* delivers air into the plenum
* drives environmental circulation
* influences environmental transport rate

The fan is intended to operate continuously.

The design assumes:

* low-speed operation
* gradual adjustment
* avoidance of aggressive airflow changes

The distributed duct arrangement is intended to:

* reduce dead zones
* improve environmental consistency
* minimize local drying effects

---

# 10 Fresh-Air Strategy

Fresh air is introduced into the plenum.

The fresh-air system consists of:

* dedicated fresh-air fan
* fresh-air connection to the plenum

The current design uses a dedicated SFIB1-130-01 fan to introduce fresh air into the plenum.

Fresh air mixes with recirculated air before entering the supply duct.

This architecture was selected to:

* reduce direct airflow disturbances
* improve environmental mixing
* support future CO₂ management
* support future automation

The previous direct-injection fresh-air fan is considered a temporary implementation and is intended to be retired once the plenum-fed fresh-air system is operational.

During commissioning:

* fresh-air fan speed is manually adjusted
* CO₂ is monitored using an Inkbird CO₂ monitor

Automatic CO₂ control remains a future development.

---

# 11 Environmental Instrumentation Philosophy

Environmental instrumentation exists to support:

* commissioning
* troubleshooting
* environmental understanding
* future automation

The architecture anticipates:

* room environmental sensing
* validation sensing
* future plenum sensing
* future CO₂ sensing
* future door-event sensing

The architecture intentionally allows instrumentation to evolve as operational understanding improves.

Final sensor placement decisions remain subject to commissioning results.

---

# 12 Environmental Control Assumptions

The design assumes:

* ultrasonic humidification can maintain target humidity
* the plenum provides effective environmental mixing
* distributed airflow improves environmental consistency
* passive exhaust is sufficient for surplus airflow removal
* continuous circulation is preferable to intermittent circulation
* fresh-air introduction through the plenum supports future CO₂ management

The design further assumes that:

* commissioning must precede automation
* environmental behaviour should be validated before advanced control is implemented
* airflow validation is a required project activity
* yield improvement remains the primary objective

The design anticipates future integration of:

* ESP32 control
* Home Assistant supervision
* CO₂ sensing
* automated fresh-air control
* air-conditioner integration
* door-event awareness

---

# 13 Commissioning Philosophy

The immediate objective is to validate the environmental architecture.

Commissioning activities include:

* validating airflow distribution
* validating humidity control
* validating environmental uniformity
* validating fresh-air strategy
* understanding room CO₂ behaviour

The commissioning phase intentionally emphasizes:

* observation
* operational learning
* environmental validation

before introducing advanced automation.

The environmental architecture shall be validated before automated environmental optimization is attempted.

---

# 14 Future Expansion

Potential future developments include:

* CO₂ sensing
* automated fresh-air control
* automated circulation control
* plenum instrumentation
* air-conditioner integration
* environmental data logging
* door-event monitoring
* alarm escalation
* adaptive environmental control
* full-room conversion

Future expansion shall preserve:

* environmental stability
* maintainability
* simplicity
* yield-focused operation

---

# 15 Open Questions

The following areas remain open and require operational validation:

* final environmental sensor placement
* duct airflow distribution
* optimal circulation-fan operating speed
* optimal fresh-air fan operating speed
* environmental response timing
* humidifier carry-over behaviour
* condensation behaviour within ducts and plenum
* long-term airflow balancing
* future CO₂-control strategy
* future air-conditioner integration strategy
* future door-event handling strategy

These questions are expected to be resolved through commissioning and operational experience.
