# Fruiting Room Environmental Design

## 1 Purpose

This document defines the physical structure, airflow design, and environmental conditioning philosophy of the Fungi4u fruiting room.

It serves as a reference for:

* future upgrades and redesigns
* ESP32 and Home Assistant integration
* environmental control development
* maintenance and troubleshooting
* documentation of assumptions and constraints
* expansion planning

The document captures both the current implementation and the intended final airflow architecture.

This document defines the physical environmental architecture only.

ESP32 control-system behaviour is defined separately in:

`ESP32_ENVIRONMENTAL_CONTROL_ARCHITECTURE.md`

---

# 2 System Intent

The fruiting room is intended to provide a controlled environment for oyster mushroom fruiting with emphasis on:

* stable humidity
* uniform temperature distribution
* low direct airflow on mushrooms
* controlled fresh air exchange
* CO₂ management
* modular future expansion
* low operating cost
* compatibility with automation systems

The design prioritizes:

* soft continuous circulation
* gradual environmental stabilization
* distributed airflow rather than point-source airflow
* plenum-based environmental conditioning

The design assumes that environmental stability is achieved primarily through:

* continuous circulation
* conditioned air distribution
* gradual environmental adjustment
* and proper environmental mixing.

---

# 3 Building Description

The fruiting room is located inside an outbuilding positioned behind and close to the main house.

The building:

* has a flat corrugated iron roof
* is approximately rectangular
* has outside dimensions:

  * 4650 mm on the shorter side
  * 7000 mm on the longer side
* shares the left-side wall with the neighbour-side boundary fence

The fruiting room occupies the left side of the outbuilding.

Originally, the space contained two garage door openings:

* one at the front
* one at the back

Each opening is:

* 2500 mm wide
* 2200 mm high

Construction details:

* external walls: approximately 250 mm thick
* internal dividing wall: approximately 75 mm thick

Ceiling height:

* front (street side): 2720 mm
* back: 2550 mm

The room was converted from a drive-through garage space into a mushroom fruiting environment.

---

# 4 Fruiting Room Construction

## Front Wall

The front garage door was permanently fixed closed and insulated internally with:

* 100 mm Isoboard insulation

This reduced the usable room depth by approximately 100 mm.

At floor level below the garage door:

* a gap of approximately 50 mm remains
* the gap is covered with an aluminium plate
* the plate contains:

  * 8 mm holes
  * 20 mm hole spacing

This opening functions as a passive exhaust path for surplus air during fresh air exchange.

---

## Rear Wall

The rear garage opening was closed externally using:

* double-layer dry wall construction
* 50 mm insulated wall assembly
* Isoboard insulation between wall layers

A matching insulated access door is positioned centrally in this wall.

Because the wall is mounted externally to the original opening:

* approximately 250 mm of additional internal floor space is recovered across the width of the opening.

---

## Air Conditioner Position

The air-conditioning unit is mounted:

* above the rear access door
* on the internal brick wall surface

---

## Interim Divider Wall

An interim insulated partition currently divides the space into:

* fruiting room (front section)
* growing room (rear section)

Divider construction:

* 50 mm insulated dry wall
* door positioned centrally

Divider position:

* 1720 mm from the front wall

During this interim stage:

* airflow ducts remain installed
* duct holes are sealed using duct tape

---

# 5 Environmental Design Philosophy

The environmental design is based on the following principles:

* continuous low-velocity circulation
* gradual environmental stabilization
* even distribution of humidity and temperature
* distributed airflow rather than point-source airflow
* passive exhaust management
* plenum-based air conditioning and mixing
* modular airflow control
* future automation compatibility

The system is designed to:

* avoid strong drafts on mushrooms
* prevent stagnant air zones
* reduce humidity stratification
* improve consistency across shelving levels
* reduce aggressive environmental cycling
* maintain stable environmental transport conditions

The design assumes that proper air mixing is more important than high airflow volume.

Continuous circulation is considered preferable to intermittent high-speed airflow.

---

# 6 Airflow Architecture

The airflow system is based on a closed circulation loop with controlled fresh air introduction.

Main airflow path:

1. Air is extracted from a low-level inlet duct
2. Air moves through the circulation fan
3. Air enters the central plenum
4. Air is conditioned and humidified
5. Air is redistributed through ceiling-level ducts
6. Air returns through the room volume toward the low-level inlet duct

Fresh air is introduced into the plenum for future CO₂ management.

Surplus air exits passively through:

* the perforated lower front wall exhaust opening

---

# 7 Plenum Specification

## General Construction

External dimensions:

* 520 mm × 520 mm
* 660 mm high

Construction materials:

* 12 mm plywood
* interior and exterior coated with roof waterproofing paint

The plenum is mounted:

* against the right wall
* near ceiling level
* centrally positioned on the wall

The plenum functions as:

* environmental mixing chamber
* humidification chamber
* pressure equalization chamber
* conditioned supply preparation chamber

The plenum therefore acts as the central environmental conditioning unit of the fruiting room.

---

## Drainage Design

The plenum base is sloped internally to direct water toward:

* a drain outlet fitted with a trap

The trap prevents unintended air leakage.

The bottom panel is removable for:

* cleaning
* inspection
* maintenance

---

## Internal Configuration

The plenum is internally divided into:

* lower chamber
* upper chamber

A central baffle separates the two chambers while leaving side gaps that allow airflow transfer.

---

## Lower Chamber Functions

The lower chamber contains:

* air inlet from circulation duct
* fresh air inlet from outside
* internal baffles for air mixing
* water reservoir tub
* float valve for automatic water level control
* five-disk ultrasonic mist maker

The lower chamber functions as:

* mixing chamber
* humidification chamber

---

## Upper Chamber Functions

The upper chamber distributes conditioned air into:

* ceiling-level ducts on both sides

This chamber functions as:

* final pressure equalization zone
* conditioned-air stabilization zone
* air distribution chamber

---

# 8 Ducting Specification

The ducting system uses:

* 110 mm PVC drain pipe

Two primary duct runs are planned:

## Low-Level Return Duct

Location:

* along the bottom of the left wall

Function:

* extract room air

---

## High-Level Supply Duct

Location:

* along the top of the right wall

Function:

* distribute conditioned air

---

## Air Distribution Holes

Both ducts use:

* distributed 10 mm holes

The hole system is intended to:

* spread airflow evenly
* reduce local air velocity
* encourage uniform circulation

---

# 9 Air Movement Strategy

Air movement is generated using:

* a variable-speed circulation fan

The fan:

* pulls air from the low-level return duct
* pushes air into the plenum
* drives environmental circulation
* controls circulation intensity
* influences environmental transport rate

The air then passes through:

* the plenum
* humidification section
* mixing section

Conditioned air is redistributed through:

* ceiling-level supply ducts

The system is designed to create:

* soft continuous airflow
* gentle circulation patterns
* minimal turbulence near mushroom surfaces

The distributed hole arrangement is intended to:

* reduce dead zones
* improve environmental consistency
* prevent localized drying

Continuous circulation is considered part of normal operation.

The design assumes gradual fan-speed modulation rather than aggressive cycling.

---

# 10 Environmental Control Assumptions

The design assumes:

* humidity can be maintained primarily through ultrasonic fogging
* air mixing inside the plenum is sufficient for environmental equalization
* passive exhaust is adequate for surplus airflow removal
* distributed airflow holes will reduce directional airflow stress
* variable fan speed can regulate circulation intensity
* fresh air input can manage CO₂ concentration
* continuous low-speed circulation is preferable to intermittent high-speed airflow

The design also assumes that:

* environmental control will eventually be automated
* sensors and control systems will be integrated later
* the plenum will become the central environmental conditioning point
* environmental transport occurs gradually through the room volume
* separate sensing of room conditions and conditioned supply air may be beneficial

Detailed ESP32 environmental control logic is defined separately in:

`ESP32_ENVIRONMENTAL_CONTROL_ARCHITECTURE.md`

---

# 11 Future Expansion

Potential future developments include:

* automated ESP32 environmental control
* dynamic fresh air control
* CO₂-based airflow regulation
* variable humidification control
* integration with Home Assistant
* additional sensors
* improved plenum airflow balancing
* full-room conversion after interim divider removal
* environmental data logging
* automated fault detection

Possible future airflow enhancements:

* motorized fresh air dampers
* condensation management improvements
* additional airflow balancing baffles
* positive pressure tuning

---

# 12 Open Questions

The following areas still require validation or refinement:

* final sizing of distributed duct holes
* optimal fan capacity and operating range
* actual airflow distribution patterns
* effectiveness of passive exhaust sizing
* condensation behavior inside ducts and plenum
* cleaning accessibility of ducts
* long-term durability of waterproofed plywood
* fresh air intake positioning
* optimal sensor placement
* air velocity near mushroom clusters
* balance between humidity retention and fresh air exchange
* future integration of heating or cooling assistance
* noise levels during continuous operation
* impact of shelving layout on circulation patterns
* recovery timing after operational disturbances
* fan-control implementation method
* environmental response timing
* humidifier carry-over behaviour

Additional validation through operational testing is expected to refine the final design.
