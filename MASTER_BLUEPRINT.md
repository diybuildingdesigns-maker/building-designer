# DIY Building Designs Professional

# Master Blueprint v1.0

## Core Rule

Everything in this software is controlled by one central Building
object.

The user edits the building.

The software automatically regenerates the 3D model, framing, materials,
pricing, drawings, and reports.

## Version 1.0 Scope

Version 1.0 will focus on simple gable red iron buildings.

### Included

-   Width
-   Length
-   Eave height
-   Roof pitch
-   Bay spacing
-   Main frames
-   Endwalls
-   Sidewalls
-   Girts
-   Purlins
-   Bracing
-   Openings
-   Material takeoff
-   Weight-based pricing
-   Shop drawing output

### Not included in Version 1.0

-   Mezzanines
-   Crane systems
-   Multi-span buildings
-   Complex roof systems
-   Advanced lean-tos

## Building Object

``` text
Building
│
├── Project Info
├── Geometry
├── Roof
├── Bays
├── Frames
├── Endwalls
├── Sidewalls
├── Openings
├── Secondary Framing
├── Bracing
├── Materials
├── Loads
├── Pricing
├── Drawings
└── Reports
```

## First Development Goal

Create a working application that accepts:

-   Building width
-   Building length
-   Eave height
-   Roof pitch
-   Number of bays

and automatically generates a basic 3D red-iron building frame.
