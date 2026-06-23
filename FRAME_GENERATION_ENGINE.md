# DIY Building Designs Professional
# FRAME_GENERATION_ENGINE.md

## Purpose

The Frame Generation Engine is responsible for converting a building definition into a complete primary steel frame layout.

The user never places rigid frames manually. Frames are generated automatically from the building dimensions and user-defined layout settings.

---

# Core Principle

Frame generation must be automatic.

Changing the building geometry automatically regenerates the frame layout while preserving valid user overrides whenever possible.

---

# Generation Sequence

When a new building is created, the software follows this order:

1. Read building width.
2. Read building length.
3. Read eave height.
4. Read roof pitch.
5. Determine frame count or bay spacing.
6. Generate frame centerlines.
7. Create rigid frames.
8. Position frames.
9. Create endwall framing.
10. Notify downstream systems to generate secondary framing.

---

# Frame Identification

Frames receive permanent IDs in order.

F-1
F-2
F-3
...

These IDs are used throughout drawings, reports, fabrication, and pricing.

---

# Frame Position Logic

The software supports:

- Equal bay spacing
- Custom bay spacing (future enhancement)

Example:

Building Length: 60'-0"
Frame Count: 4

Result:

F-1 = 0'-0"
F-2 = 20'-0"
F-3 = 40'-0"
F-4 = 60'-0"

---

# Automatic Updates

If the user changes:

60'-0" → 80'-0"

The engine should:

- Recalculate frame positions
- Update bay spacing
- Move connected framing
- Notify secondary framing
- Notify material takeoff
- Notify pricing
- Notify drawing generation

No manual "rebuild" command should be required.

---

# 3D Editing Rules

The user may click any frame in the 3D model.

The properties panel should display:

- Frame ID
- Position
- Left column size
- Right column size
- Left rafter size
- Right rafter size
- Bay spacing before
- Bay spacing after

Editing one of these values updates the Building object and regenerates affected geometry.

---

# Future Expansion

The engine should be designed to support:

- Unequal bays
- Multi-span buildings
- Lean-tos
- Crane systems
- Mezzanines
- Interior frames
- Monitor roofs

These features are not part of Version 1.0 but should not require redesign of the engine.

---

# Design Goal

Frame generation should feel instantaneous.

A user should be able to resize a building, add a frame, or change spacing in seconds while the software updates the entire model automatically.

# End of Document
