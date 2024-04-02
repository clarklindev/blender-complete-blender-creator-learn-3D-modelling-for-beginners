# Section 02 - Modular dungeon
### 23 Barrel
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
