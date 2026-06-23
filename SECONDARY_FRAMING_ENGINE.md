# DIY Building Designs Professional
# SECONDARY_FRAMING_ENGINE.md

## Purpose

The Secondary Framing Engine is responsible for generating and updating all non-primary structural framing members.

This includes roof purlins, wall girts, eave struts, base angle, rake angle, door jambs, headers, window framing, and other secondary support members.

The goal is to eliminate repetitive manual layout work and keep all secondary framing tied directly to the Building object.

---

# Core Principle

Secondary framing must be automatically generated from the building geometry, openings, frame layout, and design settings.

The user should not manually redraw girts, purlins, jambs, headers, or secondary members after a building change.

---

# Included Secondary Framing

Version 1.0 should support:

- Roof purlins
- Wall girts
- Eave struts
- Base angle
- Rake angle
- Door jambs
- Door headers
- Window jambs
- Window headers
- Framed opening members
- Basic flange bracing

---

# Generation Sequence

When secondary framing is generated, the software should follow this order:

1. Read the Building object.
2. Read primary frame locations.
3. Read bay spacing.
4. Read roof geometry.
5. Read wall geometry.
6. Read all openings.
7. Generate roof purlin lines.
8. Generate sidewall girt lines.
9. Generate endwall girt lines.
10. Generate eave struts.
11. Generate base angle.
12. Generate rake angle.
13. Generate jambs and headers around openings.
14. Resolve conflicts between girts and openings.
15. Update material quantities.
16. Notify pricing and drawing systems.

---

# Roof Purlins

Roof purlins are generated across the roof planes between main frames.

Each purlin should include:

- Purlin ID
- Roof plane
- Bay location
- Size
- Gauge
- Length
- Spacing
- Start point
- End point
- Frame connection points

Example IDs:

```text
P-1
P-2
P-3
```

The software should automatically recalculate purlin quantity and length when the user changes:

- Building width
- Building length
- Roof pitch
- Frame count
- Bay spacing
- Overhang
- Roof extension

---

# Wall Girts

Wall girts are generated on sidewalls and endwalls.

Each girt should include:

- Girt ID
- Wall location
- Elevation
- Size
- Gauge
- Length
- Start point
- End point
- Connection points
- Interrupted-by-opening status

Example IDs:

```text
G-1
G-2
G-3
```

Wall girt spacing should be controlled by default building settings but editable from the 3D interface or properties panel.

---

# Eave Struts

Eave struts are generated at the top of the sidewalls along the eave line.

Each eave strut should include:

- Eave strut ID
- Sidewall location
- Size
- Length
- Start point
- End point
- Connection to frames
- Roof panel support reference
- Wall panel support reference

---

# Base Angle

Base angle is generated along the bottom of the wall panels.

Each base angle should include:

- Base angle ID
- Wall location
- Size
- Length
- Start point
- End point
- Connection points

The base angle should automatically account for large openings when required.

---

# Rake Angle

Rake angle is generated along the roof slope at the endwalls.

Each rake angle should include:

- Rake angle ID
- Endwall location
- Roof slope
- Size
- Length
- Start point
- End point

---

# Openings and Conflict Resolution

Openings must automatically modify secondary framing.

When a door, window, louver, or framed opening is added, the software should:

- Cut or interrupt girts where required
- Add jamb members
- Add header members
- Add sill members when required
- Add trim references
- Update material quantities
- Update drawings

The user should not manually delete girts or manually build opening frames for normal openings.

---

# Door Framing

Door framing should be generated based on the opening type.

For roll-up doors and overhead doors, generate:

- Left jamb
- Right jamb
- Header
- Optional sill or base condition
- Trim references

Door framing should remain attached to the wall and move automatically if the door is moved.

---

# Window Framing

Window framing should generate:

- Left jamb
- Right jamb
- Header
- Sill
- Trim references

Windows should be moved visually in the 3D model.

The framing should update automatically.

---

# Editing Rules

The user should be able to click secondary framing members in the 3D model.

The properties panel should display:

- Member ID
- Member type
- Size
- Gauge
- Length
- Wall or roof location
- Elevation or spacing
- Connection references

Advanced users may override individual members, but overrides should be clearly marked.

---

# User Override Rules

Automatic generation is the default.

Manual overrides should be allowed only when needed.

Examples of overrides:

- Change one girt size
- Change purlin spacing in one bay
- Add custom jamb member
- Lock a member length
- Force a member to remain after regeneration

Overridden members should be marked as:

```text
Manual Override: Yes
```

If a future building change conflicts with an override, the software should warn the user before deleting or changing it.

---

# Automatic Update Behavior

If the user changes building length, the engine should update:

- Purlin lengths
- Purlin quantities
- Sidewall girt lengths
- Bay-based members
- Eave struts
- Base angle
- Material takeoff
- Pricing
- Drawings

If the user adds a door, the engine should update:

- Affected wall girts
- Door jambs
- Door header
- Trim references
- Material takeoff
- Drawings

If the user changes eave height, the engine should update:

- Wall girt elevations
- Endwall framing
- Sidewall framing
- Opening positions when tied to wall references
- Material takeoff
- Drawings

---

# 3D Interface Requirements

Secondary framing should be editable visually.

The user should be able to:

- Select a wall
- View girt spacing
- Select a roof plane
- View purlin spacing
- Add or move openings
- See framing update immediately
- Toggle secondary framing on or off
- Show only selected wall framing
- Show only roof purlins
- Show hidden-line or wireframe mode

---

# Assistant Mode Note

The software may include a guided design assistant for newer users.

This assistant must be optional.

Experienced users must be able to disable hints, walkthroughs, popups, and suggestions so the interface does not become annoying or slow down production work.

Assistant mode should help new users without interfering with experienced users.

---

# Design Goal

The Secondary Framing Engine should make common framing layout work automatic.

A user should be able to change the building, move a door, or adjust roof pitch without manually rebuilding girts, purlins, jambs, headers, or trim references.

The software should handle the repetitive work so the designer can focus on the building.

# End of Document
