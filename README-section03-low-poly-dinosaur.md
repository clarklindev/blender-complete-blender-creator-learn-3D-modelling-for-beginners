# section 03 - low poly dinosaur
- import reference images (drag onto 3d viewport)
- object data properties (right panel) -> opacity 0.2
- object data properties (right panel) -> show in (toggle showing in perspective and orthographic view mode)
- ensure the reference images line up (in front/side view)
- in outliner (right panel - top) -> filter options -> selectable button -> on -> this allows toggling if items are selectable

#### dinosaur modelling
- start with a plane
- rotate it (side view) on y-axis so 90 degress and flat like the reference image
- APPLY rotation (CTRL + A)
- draw out shape with edge extrudes then extrude the whole shape
- tweak and move vertices so it traces outline of dinosaur
- do extra loop cuts if neccessary around head
- extrude
- use mirror modifier on x axis to mirror the other side
- overlays button (3d viewport menu (top right)-> viewport overlays)-> face orientation -> checked
- normals for object are correct when blue -> if red -> normals are wrong way round -> need to be flipped (ALT+N) -> flip
- you can use proportional editing / circle of influence to adjust edges/vertice/faces and the area around it

#### FIX NORMALS
- FIX: in edit mode -> SHIFT + N (check recalculate normals inside checkbox) -> object should be blue

#### merge vertices
- select all (edit mode)-> merge menu (M) -> by distance
- mirror options -> clipping
- play with the merge distance threshold

#### round out 
- for rounding out the shape: select edges from head to tail -> G (g) + grabe slide (G)

## 46 DINO FACE
![section03 - low poly dinosaur - 46-dinosaur-face.png](./section03-low-poly-dinosaur/section03%20-%20low%20poly%20dinosaur%20-%2046-dinosaur-face.png)

- inset but with boundary (so it doesnt include the mirror edges)
- AUTO merge vertices -> OFF
- the way to create depth at the mouth is extrude (e) -> then scales with the normals of the faces selected (alt + s)

## 47 LANDSCAPE
- use a grid for landscape
- use decimate modifier for low poly feel (0.01)
- copy landscape and store in spares collection -> hide from render and view
- apply the decimated landscape after to the original

## 48 lighting - trees

![section03 - low poly dinosaur - 48-trees-lighting_2.png](./section03-low-poly-dinosaur/section03%20-%20low%20poly%20dinosaur%20-%2048-trees-lighting_2.png)

![section03 - low poly dinosaur - 48-trees-lighting.png](./section03-low-poly-dinosaur/section03%20-%20low%20poly%20dinosaur%20-%2048-trees-lighting.png)

## 50 mountains
- node wrangler addon -> select principle BSDF -> CTRL + T -> (only keep texture editor)
- or add texture coordinate directly: shader editor -> input -> texture coordinate
- add (SHIFT + A) -> converter -> separate x,y,z 
- connect texture coordinate object -> to separate xyz vector
- shader editor -> add (SHIFT + A) -> input -> texture coordinate -> using texture coordinate to create gradient on mountain
- make sure you have applied your rotation else the gradient can look weird

#### preview effect in node wrangler
- CTRL + SHIFT + left click on A NODE -> hooks up to a viewer node

#### resetting preview
- CTRL + SHIFT + left click on Principle BSDF node resets preview
- hook up separate XYZ z -> principle BSDF base color

#### covert b/w info into color
- add (SHIFT + A) -> converter -> use "color ramp" to tweak colors
- add it between separate xyz and principle bsdf node
- now you can adjust gradient


## 51 tweaks
- you can make background transparent -> render output -> film -> transparent
