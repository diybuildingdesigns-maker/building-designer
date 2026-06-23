# DIY Building Designs Professional
# Building Object Specification v1.0

## Purpose

This document defines the central Building object used by DIY Building Designs Professional.

The Building object is the single source of truth for the entire project. Every part of the software reads from and updates this object.

The 3D model, framing, engineering, material takeoff, pricing, drawings, and reports must all be generated from this one Building object.

## Core Rule

The user edits the Building object through the 3D interface.

The software automatically regenerates everything downstream.

The user should not manually edit drawings, material lists, pricing sheets, or engineering output.

---

# Building Object Structure

```text
Building
│
├── project
├── geometry
├── roof
├── bays
├── frames
├── endwalls
├── sidewalls
├── openings
├── secondaryFraming
├── bracing
├── materials
├── loads
├── pricing
├── drawings
└── reports
```

---

# 1. Project

Stores basic job information.

```text
project
├── projectName
├── customerName
├── projectNumber
├── buildingName
├── jobLocation
├── city
├── state
├── zipCode
├── preparedBy
├── dateCreated
└── dateModified
```

Example:

```json
{
  "projectName": "Smith Garage",
  "customerName": "John Smith",
  "buildingName": "Building A",
  "jobLocation": "Daphne, Alabama",
  "preparedBy": "DIY Building Designs"
}
```

---

# 2. Geometry

Stores the main building dimensions.

```text
geometry
├── width
├── length
├── eaveHeight
├── ridgeHeight
├── roofPitch
├── leftEaveHeight
├── rightEaveHeight
├── startWall
├── endWall
├── leftSidewall
└── rightSidewall
```

Version 1.0 assumes a simple rectangular gable building.

Example:

```json
{
  "width": "40 ft",
  "length": "60 ft",
  "eaveHeight": "16 ft",
  "roofPitch": "4:12"
}
```

---

# 3. Roof

Stores roof shape and roof surface settings.

```text
roof
├── roofType
├── roofPitch
├── ridgeDirection
├── roofPanelType
├── roofPanelColor
├── roofTrimColor
├── roofOverhang
└── soffit
```

Version 1.0 roof type:

```text
gable
```

Future roof types may include:

- single slope
- hip roof
- monitor roof
- gambrel roof
- multi-span roof

---

# 4. Bays

Stores the spacing between main frames.

```text
bays
├── bayCount
├── frameCount
├── baySpacingType
└── baySpacing
```

Example:

```json
{
  "bayCount": 3,
  "frameCount": 4,
  "baySpacingType": "equal",
  "baySpacing": ["20 ft", "20 ft", "20 ft"]
}
```

The software must be able to automatically recalculate bay spacing when the user changes building length or frame count.

---

# 5. Frames

Stores main rigid frame information.

```text
frames
├── frameId
├── frameType
├── position
├── leftColumn
├── rightColumn
├── leftRafter
├── rightRafter
├── haunches
├── basePlates
├── connectionPlates
└── anchorBolts
```

Version 1.0 frame type:

```text
rigid gable frame
```

Frame members should be automatically generated from the building width, eave height, roof pitch, and frame position.

---

# 6. Endwalls

Stores framing information for the two endwalls.

```text
endwalls
├── frontEndwall
└── backEndwall
```

Each endwall may contain:

```text
endwall
├── endwallType
├── columns
├── girts
├── rakeAngles
├── openings
└── trim
```

Version 1.0 endwall types:

- bearing frame
- post-and-beam endwall

---

# 7. Sidewalls

Stores framing information for both sidewalls.

```text
sidewalls
├── leftSidewall
└── rightSidewall
```

Each sidewall may contain:

```text
sidewall
├── columns
├── girts
├── openings
├── eaveStrut
├── baseAngle
└── trim
```

---

# 8. Openings

Stores doors, walk doors, windows, louvers, and framed openings.

```text
openings
├── openingId
├── openingType
├── wall
├── width
├── height
├── location
├── sillHeight
├── headerHeight
├── framedOpening
└── trim
```

Opening types:

- roll-up door
- overhead door
- walk door
- window
- louver
- framed opening

Example:

```json
{
  "openingType": "roll-up door",
  "wall": "front endwall",
  "width": "12 ft",
  "height": "12 ft",
  "location": "centered"
}
```

Openings should be placed visually from the 3D interface.

---

# 9. Secondary Framing

Stores girts, purlins, eave struts, base angle, and other secondary steel.

```text
secondaryFraming
├── roofPurlins
├── wallGirts
├── eaveStruts
├── baseAngles
├── rakeAngles
└── jambsAndHeaders
```

Each member should include:

```text
member
├── memberId
├── memberType
├── size
├── gauge
├── length
├── location
├── quantity
└── materialGrade
```

---

# 10. Bracing

Stores cable bracing, rod bracing, portal frames, and wind columns.

```text
bracing
├── roofBracing
├── wallBracing
├── portalFrames
├── windColumns
└── flangeBracing
```

Version 1.0 should support:

- roof X-bracing
- wall X-bracing
- basic wind columns

---

# 11. Materials

Stores default material grades and coating settings.

```text
materials
├── primarySteel
├── secondarySteel
├── panels
├── trim
├── bolts
├── anchorBolts
└── paint
```

Default primary steel:

```text
ASTM A992
```

---

# 12. Loads

Stores design loads and code settings.

```text
loads
├── buildingCode
├── windSpeed
├── exposureCategory
├── riskCategory
├── roofLiveLoad
├── collateralLoad
├── snowLoad
├── seismicData
└── deflectionLimits
```

Version 1.0 default wind speed:

```text
158 mph
```

Engineering calculations should be handled internally and not shown to the customer unless included in an engineering report.

---

# 13. Pricing

Stores pricing inputs and final calculated pricing.

```text
pricing
├── steelPricePerPound
├── panelPrice
├── trimPrice
├── boltPrice
├── fabricationLabor
├── paintCost
├── freightCost
├── markup
├── totalWeight
├── totalCost
└── sellPrice
```

Pricing should update automatically when the building changes.

---

# 14. Drawings

Stores drawing output information.

```text
drawings
├── approvalDrawings
├── anchorBoltPlan
├── erectionDrawings
├── frameDrawings
├── shopDrawings
├── materialSheets
└── pdfPackage
```

The user does not manually edit drawings.

Drawings regenerate from the Building object.

---

# 15. Reports

Stores generated project reports.

```text
reports
├── customerProposal
├── materialTakeoff
├── weightSummary
├── pricingSummary
├── engineeringSummary
├── fabricationReport
└── shippingReport
```

---

# Required Behavior

When the user changes a major building property, the software must automatically update every affected part of the Building object.

Example:

If the user changes:

```text
Length: 60 ft → 80 ft
```

The software should automatically update:

- Bay spacing
- Frame positions
- Sidewall girts
- Roof purlins
- Bracing locations
- Panel quantities
- Trim quantities
- Material takeoff
- Weight
- Pricing
- Drawings
- Reports

---

# Version 1.0 Development Priority

The first working development target is the Geometry section.

The software should first be able to create:

- Building width
- Building length
- Eave height
- Roof pitch
- Bay count
- Frame count
- Equal bay spacing
- Basic 3D frame layout

Once this works correctly, the next step is adding secondary framing.

---

# End of Document
