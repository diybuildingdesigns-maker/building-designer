# DIY Building Designs Professional
# MAIN_WORKSPACE_SPECIFICATION.md

## Purpose

This document defines the primary workspace used by all three user modes.

The workspace must remain familiar while exposing different levels of capability depending on the selected mode.

---

# Workspace Layout

Top
- Menu Bar
- Quick Access Toolbar

Left
- Project Tree

Center
- Large 3D Building View

Right
- Smart Inspector (context-sensitive properties)

Bottom
- Status Bar

The 3D view should occupy the majority of the screen.

---

# Smart Inspector

The Smart Inspector changes based on the selected object.

Selecting a frame displays:
- Frame ID
- Position
- Member sizes
- Bay spacing
- Connections

Selecting a door displays:
- Width
- Height
- Offset
- Header
- Jambs

Selecting a roof plane displays:
- Roof pitch
- Panel type
- Purlin spacing
- Color

The inspector should never show unrelated settings.

---

# Three Workspace Modes

## Designer Mode

Visible:
- Geometry
- Openings
- Colors
- Materials
- Customer options

Hidden:
- Structural calculations
- Load combinations
- Member overrides

Goal:
Design the building quickly.

---

## Professional Mode

Adds:
- Frame editing
- Bay editing
- Secondary framing controls
- Member overrides
- Material libraries

Goal:
Fine tune the structure without exposing engineering calculations.

---

## Engineering Mode

Adds:
- Code selection
- Design loads
- Deflection limits
- Connection review
- Calculation reports

Goal:
Validate and approve the structural design.

---

# Selection Philosophy

The building is the menu.

Clicking an object should reveal only the tools needed for that object.

No searching through nested dialogs.

---

# View Modes

The user can toggle:

- Full Building
- Primary Steel
- Secondary Steel
- Panels
- Trim
- Openings
- Bracing
- Foundation
- Wireframe
- Transparent

---

# Design Goal

The interface should allow a new user to become productive quickly while providing experienced designers and engineers the depth they need without cluttering the workspace.

# End of Document
