# DIY Building Designs Professional
# DESIGN_PRINCIPLES.md

## Purpose

This document defines the non-negotiable principles that guide every feature in DIY Building Designs Professional.

If a new feature violates these principles, the design should be reconsidered before implementation.

---

# Principle 1 – The Building Is the Single Source of Truth

Everything is generated from one Building object.

The user edits the building.

The software updates everything else automatically.

Never maintain duplicate building data.

---

# Principle 2 – The 3D Model Is the Primary Interface

The model is not just for viewing.

It is where users interact with the building.

Users should be able to click frames, bays, doors, windows, girts, purlins, and other components to edit their properties.

---

# Principle 3 – Immediate Feedback

Normal design changes should update the model instantly.

Avoid "Rebuild", "Regenerate", or "Calculate" buttons for common edits.

---

# Principle 4 – Simplicity Before Complexity

If two solutions produce the same result, prefer the one that is easier to understand.

The software should be approachable for builders, salespeople, designers, and engineers.

---

# Principle 5 – Automation Over Repetition

The user should enter information once.

Every downstream task—material takeoff, pricing, drawings, reports, and fabrication outputs—should reuse that information automatically.

---

# Principle 6 – Professional Results

Simple does not mean limited.

The software should produce professional-grade outputs suitable for estimating, fabrication, and construction.

---

# Principle 7 – Expand Without Rebuilding

Version 1.0 focuses on simple gable buildings.

The architecture must allow future additions such as:

- Lean-tos
- Mezzanines
- Multi-span buildings
- Crane systems
- Advanced roof types
- Cold-formed framing

without redesigning the core software.

---

# Principle 8 – Every Feature Must Save Time

Before adding a feature, ask:

Does this reduce the time required to design, estimate, fabricate, or revise a building?

If not, reconsider the design.

---

# Long-Term Vision

DIY Building Designs Professional should become the complete workflow for steel building projects:

Design → Engineer → Estimate → Fabricate → Produce → Deliver

using one intelligent building model.

# End of Document
