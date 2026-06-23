# DIY Building Designs Professional
# BUILDING_DESIGN_WORKFLOW.md

## Purpose

This document defines the standard workflow for creating a steel building inside DIY Building Designs Professional.

The goal is to make the process simple, visual, and fast while still producing professional design, estimating, fabrication, and drawing outputs.

---

# Core Workflow Rule

The user should be able to create and revise a building primarily from the 3D design workspace.

The workflow should not require the user to manually edit files, folders, hidden settings, or disconnected tables.

---

# Main Workflow

## Step 1 – Create Project

The user starts by creating a new project.

Required information:

- Project name
- Customer name
- Job location
- Building name or building number
- Prepared by
- Date

This information is used later for drawings, reports, proposals, and file organization.

---

## Step 2 – Create Building Geometry

The user enters the basic building dimensions.

Required inputs:

- Building width
- Building length
- Eave height
- Roof pitch
- Bay count or frame count

Example:

```text
Width: 40'-0"
Length: 60'-0"
Eave Height: 16'-0"
Roof Pitch: 4:12
Bay Count: 3
Frame Count: 4
```

The software immediately generates a basic 3D gable building frame.

---

## Step 3 – Generate Primary Frames

The software automatically creates the main rigid frames.

Generated items:

- Frame centerlines
- Columns
- Rafters
- Haunches
- Base plates
- Anchor bolt locations
- Frame IDs

Frame IDs:

```text
F-1
F-2
F-3
F-4
```

The user should be able to click any frame in the 3D model and edit its properties from the side panel.

---

## Step 4 – Generate Bays

The software automatically creates bays between the frames.

Each bay includes:

- Bay ID
- Bay spacing
- Start frame
- End frame
- Roof purlin zone
- Sidewall girt zone
- Bracing zone

Bay IDs:

```text
BAY-1
BAY-2
BAY-3
```

If the building length changes, bay spacing updates automatically.

---

## Step 5 – Generate Endwalls

The software creates front and back endwall framing.

Each endwall includes:

- Endwall columns
- Endwall rafters or rake members
- Girts
- Door framing
- Window framing
- Trim references

Endwalls should be editable from the 3D model.

---

## Step 6 – Generate Sidewalls

The software creates left and right sidewall framing.

Each sidewall includes:

- Wall girts
- Eave strut
- Base angle
- Door framing
- Window framing
- Bracing
- Trim references

---

## Step 7 – Add Openings

The user adds doors, walk doors, windows, louvers, or framed openings directly in the 3D model.

Opening inputs:

- Opening type
- Wall location
- Width
- Height
- Horizontal position
- Sill height
- Header height

Opening types:

- Roll-up door
- Overhead door
- Walk door
- Window
- Louver
- Framed opening

When an opening is added, the software automatically updates:

- Jambs
- Headers
- Girts
- Trim
- Material quantities
- Drawings

---

## Step 8 – Generate Secondary Framing

The software automatically adds secondary steel.

Secondary framing includes:

- Roof purlins
- Wall girts
- Eave struts
- Base angle
- Rake angle
- Door jambs
- Door headers
- Window framing

The user should be able to select a wall or roof plane and view or edit secondary framing spacing.

---

## Step 9 – Add Bracing

The software places standard bracing based on building geometry and design requirements.

Bracing may include:

- Roof X-bracing
- Wall X-bracing
- Rod bracing
- Cable bracing
- Wind columns
- Portal frames

Version 1.0 should support basic roof and wall X-bracing.

---

## Step 10 – Apply Materials and Colors

The user selects material and finish options.

Examples:

- Primary steel material
- Secondary steel material
- Roof panel type
- Wall panel type
- Roof color
- Wall color
- Trim color
- Paint system

The 3D model updates visually when colors are changed.

---

## Step 11 – Generate Material Takeoff

The software automatically generates material quantities.

Takeoff categories:

- Primary steel
- Secondary steel
- Panels
- Trim
- Bolts
- Anchor bolts
- Bracing
- Plates
- Miscellaneous steel

The takeoff updates every time the building changes.

---

## Step 12 – Generate Pricing

The pricing engine calculates customer pricing from the building model.

Pricing may include:

- Steel weight
- Material cost
- Fabrication labor
- Hardware
- Panels
- Trim
- Paint
- Freight
- Markup
- Total sell price

Pricing should update automatically when the building changes.

---

## Step 13 – Generate Drawings

The drawing engine creates project documents from the Building object.

Drawing outputs:

- Approval drawings
- Anchor bolt plan
- Erection drawings
- Frame elevations
- Roof framing plan
- Wall framing plans
- Shop drawings
- Material order sheets

The user should not manually redraw these documents.

---

## Step 14 – Generate Reports

Reports are created from the same Building object.

Reports may include:

- Customer proposal
- Weight summary
- Material takeoff
- Pricing summary
- Fabrication report
- Shipping report

---

# Project Tree Layout

The application should include a simple project tree.

```text
Project
└── Building A
    ├── Geometry
    ├── Primary Frames
    ├── Bays
    ├── Endwalls
    ├── Sidewalls
    ├── Openings
    ├── Secondary Framing
    ├── Bracing
    ├── Materials
    ├── Pricing
    ├── Drawings
    └── Reports
```

Clicking an item in the tree should highlight that part of the building in the 3D model.

---

# Revision Workflow

The software must make revisions simple.

Example revision:

```text
Change building length from 60'-0" to 80'-0"
```

Expected result:

- Building geometry updates
- Frame positions update
- Bay spacing updates
- Girts update
- Purlins update
- Bracing updates
- Openings stay on their assigned wall when possible
- Material takeoff updates
- Pricing updates
- Drawings update
- Reports update

The user should not manually rebuild the model.

---

# Workflow Goal

A basic building should be created in minutes.

A common revision should take seconds.

The design workflow should feel visual, modern, and simple.

# End of Document
