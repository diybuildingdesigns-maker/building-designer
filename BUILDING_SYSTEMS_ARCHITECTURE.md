# DIY Building Designs Professional
# BUILDING_SYSTEMS_ARCHITECTURE.md

## Purpose

This document defines the system-based architecture for DIY Building Designs Professional.

The software should not treat a building as a loose collection of individual steel parts. It should treat the building as a group of connected building systems.

Each system understands its own purpose, components, rules, and relationship to the rest of the building.

---

# Core Principle

Users design building systems.

The software generates the members, framing, materials, drawings, pricing, and engineering information required to build those systems.

The user should not need to manually manage every beam, girt, purlin, plate, trim piece, or bolt unless they are working in Professional Mode or Engineering Mode.

---

# Main Building Systems

```text
Building
│
├── Project System
├── Geometry System
├── Main Frame System
├── Sidewall System
├── Endwall System
├── Roof System
├── Opening System
├── Secondary Framing System
├── Bracing System
├── Addition System
├── Material System
├── Color System
├── Engineering System
├── Pricing System
├── Drawing System
└── Manufacturing System
```

---

# System Interaction Rule

Each system may depend on other systems, but the Building object remains the single source of truth.

Example:

```text
User changes building length
↓
Geometry System updates
↓
Main Frame System updates
↓
Sidewall System updates
↓
Roof System updates
↓
Secondary Framing System updates
↓
Material System updates
↓
Pricing System updates
↓
Drawing System updates
↓
Manufacturing System updates
```

The user makes one change. The software updates every affected system.

---

# 1. Project System

Stores job-level information:

- Project name
- Customer name
- Job location
- Building name
- Prepared by
- Date
- Revision history
- Project status

This information feeds proposals, drawings, reports, and file organization.

---

# 2. Geometry System

Controls the base building shape:

- Building type
- Width
- Length
- Eave height
- Roof pitch
- Ridge height
- Roof style
- Main bay layout
- Endwall bay layout
- Endwall inset

The Geometry System drives nearly every other system.

Roof pitch should support practical steel building options up to 14:12.

---

# 3. Main Frame System

Controls the primary rigid frames along the length of the building:

- Frame count
- Frame spacing
- Main bay layout
- Column locations
- Rafter geometry
- Frame IDs
- Base plates
- Anchor bolt references

The user edits this through the Bays control.

The bay editor should visually represent the sidewall, not the gabled endwall.

---

# 4. Sidewall System

Controls the long walls of the building:

- Left sidewall
- Right sidewall
- Wall panels
- Girts
- Eave struts
- Base angle
- Openings
- Sidewall bracing
- Trim

The Sidewall System is driven by building length, eave height, frame spacing, openings, and panel type.

---

# 5. Endwall System

Controls the left and right endwalls:

- Left endwall
- Right endwall
- Endwall bay layout
- Endwall columns
- Girts
- Rake members
- Openings
- Endwall inset settings
- Trim

Endwall bay layout is separate from main bay layout.

Endwall inset is also separate from main bay layout.

---

# 6. Roof System

Controls the roof planes and roof-related features:

- Roof type
- Roof pitch
- Roof panels
- Roof purlins
- Ridge condition
- Rake trim
- Eave trim
- Skylights
- Ridge vents
- Overhangs
- Roof extensions

---

# 7. Opening System

Controls doors, windows, louvers, and framed openings:

- Walk doors
- Garage doors
- Roll-up doors
- Windows
- Louvers
- Framed openings
- Jambs
- Headers
- Sills
- Trim
- Panel cuts

When an opening is added, the software automatically updates framing, trim, material takeoff, pricing, and drawings.

---

# 8. Secondary Framing System

Controls non-primary framing:

- Roof purlins
- Wall girts
- Eave struts
- Base angle
- Rake angle
- Jambs
- Headers
- Flange bracing

This system regenerates automatically when the building changes.

---

# 9. Bracing System

Controls stabilizing systems:

- Roof X-bracing
- Wall X-bracing
- Cable bracing
- Rod bracing
- Wind columns
- Portal frames
- Flange bracing

Bracing should be placed automatically when possible and editable in Structure Mode or Engineering Mode.

---

# 10. Addition System

Controls add-ons and extensions:

- Lean-tos
- Awnings
- Canopies
- Eave extensions
- Soffits
- Gutters
- Downspouts
- Roof-only extensions

These attach to the main Building object and update when the main building changes.

---

# 11. Material System

Controls material profiles, grades, and quantities:

- Primary steel
- Secondary steel
- Roof panels
- Wall panels
- Trim
- Bolts
- Anchor bolts
- Plates
- Paint
- Accessories

This feeds material takeoff, pricing, manufacturing, and reports.

---

# 12. Color System

Controls visual finishes:

- Wall color
- Roof color
- Trim color
- Door color
- Frame paint color
- Accent colors

Color selection should be visual, with color swatches available directly near the selected item.

---

# 13. Engineering System

Controls structural validation and member design:

- Building code
- Wind speed
- Exposure
- Risk category
- Roof live load
- Snow load
- Seismic settings
- Deflection limits
- Member sizing
- Connection checks

Most engineering information should remain hidden in Building Mode.

---

# 14. Pricing System

Controls estimating and customer pricing:

- Steel weight
- Material cost
- Panel cost
- Trim cost
- Hardware cost
- Fabrication labor
- Paint cost
- Freight
- Markup
- Final selling price

Pricing updates automatically as the building changes.

---

# 15. Drawing System

Controls drawing generation:

- Approval drawings
- Anchor bolt plans
- Frame elevations
- Roof framing plans
- Wall framing plans
- Erection drawings
- Shop drawings
- Material order sheets
- PDF packages

The user should not manually redraw drawings after a design change.

---

# 16. Manufacturing System

Controls production-ready output:

- Cut lists
- Saw lists
- Drill lists
- Plate lists
- CNC export
- Piece marks
- Shipping lists
- Bundle lists

This system is future-focused but should be planned from the beginning.

---

# User Mode Visibility

## Building Mode

Shows:

- Geometry
- Building type
- Main bays
- Endwall bays
- Endwall inset
- Openings
- Additions
- Panels
- Colors

## Structure Mode

Adds:

- Main frames
- Secondary framing
- Bracing
- Member overrides
- Connection previews
- Material profiles

## Engineering Mode

Adds:

- Loads
- Codes
- Calculations
- Deflection
- Reactions
- Connection checks
- Engineering reports

---

# Design Goal

The software should feel simple because users interact with building systems instead of hundreds of individual parts.

The software can still generate professional engineering, fabrication, and construction outputs because every system contains detailed data behind the scenes.

# End of Document
