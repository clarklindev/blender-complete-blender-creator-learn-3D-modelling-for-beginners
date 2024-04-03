# Section 02 - Modular dungeon

## 23 Barrel
- create cylinder
- horizontal loop cut (CTRL + R) x 2 
- scale (s) + (AND SHIFT + Z (exclude scaling on z axis))
- inset (i)

### create metal rings
- select both loopcut edges 
- bevel (CTRL + B) / or left toolbar -> adjust for thickness
- E (extrude) + S (Scale) + (AND SHIFT + Z (exclude Z axis)) 
- SELECT BOTH (top and bottom) face + I (inset)
- E (extrude) -> S (scale on Z) -> applies to both top and bottom

#### NOTCHES
- notches on top of barrel -> select edge -> CTRL + B 
- use mouse wheel to create edge down middle
- select edge and drag down on z

#### EDGE SLIDE (5min 47sec)
- Vertex mode
- SELECT single vertex
- G (grab) 
- G (again) to slide along each edge
- moving vertexes together (but it only moves them ontop of each other) AKA "DOUBLE"

#### Merge vertices
FIX: select shape (edit mode) -> M
    - choose "by distance" (valueS should be low so it really only merges vertices super close to each other)
Alt FIX: 
    - main viewport -> top-right -> auto-merge-vertices icon (icon with like 2 vertices and dashed line joining both)

---

## 24 Crate
- cube (1.2m)
- edit -> faces mode
- inset (i) -> i (i again for "individual")
- toolbar hold extrude region button -> EXTRUDE ALONG NORMALS (ALT + E)
- use loop-cut to make slats in wood

#### Makes lines thicker (BEVEL)
- select the loop-cut cuts by holding down SHIFT + CLICK 
-> then CTRL + Mouse Click on far side to select all edges inbetween
- once edges are selected, use bevel (CTRL + B)
- then use mouse wheel to create extra loop in middle
- then select only the middle edges (of the opposite sides of the edges)
- Scale (s) -> y (move them inwards)
- vertex mode -> select corner -> CTRL + B (BEVEL) -> V (Affect (edges)) -> THEN use mouse wheel to control bevel edge (detail)
- to tell blender which direction to join vertices -> select 2 opposite vertices

---

## 25 Pillar

### Mirror Modifier + clipping
- EDIT MODE -> in wireframe mode 
- loop cut (horizontal)
- select half the shape *(we will only work on half the pillar) and DELETE faces
- OBJECT CENTER is important
- Object mode -> main view -> top-right -> affect only origins -> move origin to position where everything will reflect from
- add modifier (spanner icon) -> mirror on Z
- SELECT: "clipping" -> will "stick" shape together
- loop cut
- select faces (xray + wireframe mode)
- Extrude (e) -> Scale(S) + (Shift + Z (not on Z)) 