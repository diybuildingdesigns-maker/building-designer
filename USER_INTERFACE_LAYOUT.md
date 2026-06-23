# DIY Building Designs Professional
# USER_INTERFACE_LAYOUT.md

## Purpose

This document defines the layout of the main application window.

The interface should remain clean, modern, and focused on the 3D model.

---

# Primary Layout

```text
+---------------------------------------------------------------+
| Menu Bar                                                      |
+---------------------------------------------------------------+
| Toolbar                                                       |
+-------------+-----------------------------------+-------------+
| Project     |                                   | Properties  |
| Tree        |        3D Building View           | Panel       |
|             |                                   |             |
| Geometry    |                                   | Selected    |
| Frames      |                                   | Object      |
| Bays        |                                   | Properties  |
| Endwalls    |                                   |             |
| Sidewalls   |                                   |             |
| Openings    |                                   |             |
| Materials   |                                   |             |
+-------------+-----------------------------------+-------------+
| Status Bar                                                  |
+-------------------------------------------------------------+
```

---

# Left Panel - Project Tree

The left panel contains the project structure.

Project
- Building A
  - Geometry
  - Primary Frames
  - Bays
  - Endwalls
  - Sidewalls
  - Openings
  - Secondary Framing
  - Bracing
  - Materials
  - Pricing
  - Drawings
  - Reports

Selecting an item highlights it in the 3D view.

---

# Center Panel - 3D Workspace

The 3D workspace is the primary work area.

Users should be able to:

- Orbit
- Pan
- Zoom
- Select objects
- Drag supported objects
- Measure distances
- Display dimensions
- Toggle framing, panels, and trim

The model should update immediately after edits.

---

# Right Panel - Properties

The properties panel changes based on the selected object.

Example: Selecting a frame

- Frame ID
- Position
- Column size
- Rafter size
- Bay spacing

Example: Selecting a door

- Width
- Height
- Wall
- Offset
- Header elevation

Changes made here update the model immediately.

---

# Toolbar

Common tools should always be one click away.

- New Project
- Open
- Save
- Undo
- Redo
- Select
- Move
- Rotate View
- Measure
- Add Door
- Add Window
- Frame View
- Panel View
- Material Takeoff
- Pricing
- Drawings

---

# Design Goals

- Minimal clicks
- No hidden workflows
- Immediate visual feedback
- Consistent layout
- Easy for first-time users
- Fast for experienced designers

# End of Document
