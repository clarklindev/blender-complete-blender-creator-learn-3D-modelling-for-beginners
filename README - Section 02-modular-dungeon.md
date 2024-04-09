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

## 26 Pillar details
- modifiers -> apply (CTRL + A)
- to merge vertice, select multiple vertices, right click -> merge -> by distance (adjust distance limit before merge)
- select edge -> then further down... CTRL + Left click (selects all edges between + including start and finish edge)
- the modifier (mirror) needs to be applied (in object mode) to tweak individual vertices else it applies to the mirror side as well.

## 27 Pillars (knife / bisect cut) 
- edge slide -> Even (e) to mimic edge (top/bottom) and 'flipped' for (top/bottom)
- loop cuts only work on quads, not n-gon (more than 4 verices)
- FIX: knife (K) -> allows you to make cuts (on edge/vertices) -> enter
- FIX: knife tool (hold in) -> biscect
- before using bisect tool, have to select vertices/edges/faces (A - to select all) that you want to be affected -> then click and draw line across shape to bisect

#### Pillars distort with "Randomize" 
- select A (except top and bottom by CTRL + select drag)
- then mesh -> transform -> randomize -> 0.01 
- add material color

## 28 Adding materials
#### Link material (CTRL + L)
- the select all that you want to match color with (like style painter) then select the object with material you want to copy, then CTRL + L (link materials)
- render engine EEVEE -> ambient occlusion -> ON 
- screen space reflections -> ON

---

## 29 walls
- build block by block vs. plane with extrusions (less polygons)
- USE knife tool (K) to make brick-cuts
- once you are complete "ENTER" to complete using knife cut
- in facemode, select faces -> Inset (I) -> check individual
-> OBJECT MODE: main viewport -> viewport gizmos (top) -> object gizmos -> move -> shows gizmos
-> main viewport -> transform orientation -> (change from global to local)
- MIRRORING ERROR -> N (menu)-> item -> rotation is not 0
- Mirror Modifier is taking the local axis instead of global axis
- NEED TO APPLY ROTATION (CTRL + A) -> this resets values to 0 as if its the reset position
- Turn off Object Gizmos -> Move
- Edit mode
- select all (A) 
- Grab (G + Y) on Y-axis AND separate the mirrored part
- the top of the walls should now hav a gap, need to join
- select the edge then Grab (G) + Y (ensure modifiers-> clipping is on)
- dissolve extra edges (on the top)

## 30 Completing the wall
- simple join (CTRL + J)
- or join with boolean
- joining eg. B to A, B will lose its modifiers -> so apply modifiers to B before joining.
- to join, select all you want to join and what you want to join to last 
- CTRL + J after selecting to join together
- SHIFT + D -> duplicate -
    -> Move (X 5)
    -> Rotate (R) + Z + 90

#### Overlapping geometry
- inside faces where pillar / wall meet -> FIX: booleans
- for speed - weld building with overlapping geometry is common and is fine...

## 32 CREATE HOLDDOOR
- TODO: draw outline of door then negative extrude
- SHIFT RIGHT CLICK (move cursor)
- use a plane -> rotate x:90deg, size: 1m
- plane will be mirrored to right side
- modifier -> mirror (Axis X)
- so up to this point because the origin of the plane is centered on the plane, it doesnt look like anything has happened BUT
- if you move the origin (towards center of doorway outside of plane dimensions), then the mirror will also be offset  
- TURN off TRANSFORM -> "affect only origin"

#### Create the arch
- then scale down
- then select plane top edge -> Extrude (E) and Rotate(R) as needed
- MODIFIER -> turn on clipping (for overlaps) when they overlap at the top, move so they just touch (stick) on top/bot of edge to mirrored edge
- also mirror on Y 
- isolate door shape (numpad + /) 
- extrude (E) when in isolation (with modifiers -> clipping on) so you can see what you're doing
- bevel the arch lines
- merge vertices together -> select ALL (A) -> merge (M) -> by distance
- Select all (A) -> mesh -> Transform -> randomize

## 33 Cutting the door opening
- OPTION 1 - use knife tool to cut hole
- OPTION 2 - using a shape to cut a hole in shape using BOOLEAN operation
- in WIREFRAME + XRAY mode -> make cuts and select faces you wont need -> delete faces (deletes both side of wall (because its XRAY/WIREFRAME mode)) 

## 34 Shading the walls

#### Linked Selection
- TIP: selects linked (L) 
- select inverse (CTRL + I)
- hide pillar
- select wall faces (minus outer CTRL + MINUS) 
- reveal Hidden (ALT + H) 
- zoom-in on selected object -> select object (from scene collection *right viewport) + "NUM /"

## 35 Creating the floor modules
- ctrl + a (APPLY transformations)
- turn snapping on  
- Linked Duplicate (Alt + D)
- Duplicate (NOT linked) (Shift + D)
- repeat last action (SHIFT + R)
- when joining asset -> remember to select the object you want to join to last

#### editing library asset 
- to edit, duplicate and move to its own collection
- then select face/vertice/edge + select linked object (L)
- right click -> separate -> by selection 
- then dont forget to right click -> set origin -> set origin to geometry