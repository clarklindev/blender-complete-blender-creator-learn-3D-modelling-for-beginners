# blender-complete-blender-creator-learn-3D-modelling-for-beginners

- https://www.udemy.com/course/blendertutorial/

## SHORTCUTS

### settings (preferences)
- preferences -> input -> keyboard -> emulate numpad -> use number keys on keyboard: 1,2,3,4,5,6,7 / CTRL + 1,2,3,4,5,6,7 (for reverse of 1-7) 
- note: if emulate numpad is on, this prevents surface subdivision (CTRL + 1, CTRL + 2, CTRL + 3, etc) from working
- emulate 3 button mouse -> alt + left click

#### numpad replacements
- leave emulate 3 button mouse off and to emulate numpad use ` key...
- alt key and then middle mouse button to drag to orientation of gizmo (where view should go)

### 05 moving around the scene (buttons are also on main view (top - right))
- move around viewport -> hold middle mouse button
- straph -> shift + hold middle mouse button
- middle mouse button -> perspective mode (remove background grid)
- toggle orthographic/perspective mode -> numpad 5
- camera view -> numpad 0 
- exit camera view -> middle click

### 06 adding object
- move 3d cursor -> hold SHIFT + right click 
- CREATE menu -> SHIFT + A
- toolbar (left) -> T
- grab axis move -> G + X,Y,Z (right-click to cancle before left click)
- grab axis rotate -> R + X,Y,Z (right-click to cancle before left click)
- grab axis scale -> S + X,Y,Z (right-click to cancle before left click)
- selected -> yellow (active object) + orange (others)
- main view side menu -> N
- after adding an object, there is a properties menu on the 3d viewport which dissapears if you confirm the shape after creation, to bring it back F9
- to add subdivision modifier to added shape (CTRL + 1)

### 07 Viewport and renderings

![section01 - introduction - 07-Viewport & Rendering.jpg](./section01-introduction/section01%20-%20introduction%20-%2007-Viewport%20&%20Rendering.jpg)

- modes: 
    - xray, 
    - wireframe, 
    - solid, 
    - material preview (shading workspace / eevee), 
    - render preview (move light / cycles (ray-tracing)(higher quality but slower / device: GPU compute))
- scene collection: viewport visibility / render visibilty
- render image -> F12
    -> N (main viewport side menu) -> view -> view lock -> lock camera to view
    -> ADJUST CAMERA: hold SHIFT + mouse button to shaft camera
    -> ADJUST CAMERA: mouse wheel to zoom
- EEVEE vs Cycles (slower)

### 08 Material color
- mode: "material preview" OR "render preview" to view material colors
- shading workspace (top navbar)
- add new material in shading workspace / link multiple material and output in material output
    - base color
- sharing a material, changing the color changes all instances of where the material is used.

#### increase quality of render (render properties panel)
- select ambient occlusion (rays of light cant penetrate tiny gaps)
    - distance
- select screen space reflections

### 09 Material reflections
- metalic 
- roughness
- normals (bumpiness)
- rightclick -> shade smooth
- change background -> shader editor -> world -> change background color
- https://polyhaven.com/ - HDRI's, textures, models

#### add image into world as background
- add -> texture -> environment texture -> "new window generated" -> link environment texture-color to background-color
- this updates background color to like a pink/purple

### 10 lighting

![section01 - introduction - 10-Lighting.png](./section01-introduction/section01%20-%20introduction%20-%2010-Lighting.png)

- to see light should be in render mode
- light bulb props -> types:
    1. point -> all directions
    2. sun
    3. spot
    4. area
- duplicate a light (shift + D)
- can change background strength from world settings

### 11 editing objects
- tab -> change between edit and object mode
- vertex select mode
- edge select mode
- face select mode
    - E (extrude face) / or on left toolbar extrude button 
    - do not negate the extrude 
- disect a face (loop cut) 
    - select a face -> CTRL + R -> move to get position -> left click (or right click to cancel)

### 12 simple houses

![section01 - introduction - 12-Simple houses.png](./section01-introduction/section01%20-%20introduction%20-%2012-Simple%20houses.png)

- adding another while in edit mode joins the parts into a single object (so be in object mode)
- ungroup -> edit mode -> P (separate) -> by loose parts 
- when loop cut is not "straight" but follows same contour of shape its cutting, you can once clicked on loop cut, 
- tool options (bottom-left) -> even (this evens out shape to make it flat)
- tool options (bottom-left) -> flipped will make shape mimic the top side
- exact positions (eg on z) while in edit mode, if you are adjusting an edge (G - grab mode) -> Z (lock to z-axis) -> type the values

### 13 make a Lighthouse
- TODO: make a lighthouse, collections, inset tool
- scene collection -> eye icon -> hides from viewport
- scene collection -> camera icon -> hides from render
- organize scene collection with "collections"

#### to unselect item from a group: 
    - drag-select multiple objects in viewport
    - hold down control AND THEN drag select a box over item to remove from group selection

- M (move selection menu) -> to new collection
- rename item/collection -> F2

#### zoom in /focus/center to viewport on selected object
- if you lose focus on an item from viewport, to re-center
- goto scene selection, select the object/item/collection layer so its highlighted
- numpad press "." OR select the object/item/collection from scene selection -> main view menu -> frame select

#### lighthouse continued...
- add cylinder
- create cylinder menu (bottom left) -> down vertices to 16
- edit mode -> faces -> select cylinder top face

#### lathe machine like effect / #### INSET-faces (left menu) command (i) 
- "inset faces" (i) - does extrude AND scale
- E (extrude - then immediately afterwards) -> S (scale)  > make it smaller (mouse move) to make smaller radius
- E again and pull up to make shape longer -> S (scale)

#### SELECTING SIMILAR FACES
- deselect -> SELECT A FACE -> Alt + Left click On an NB!!!! "EDGE" of that selected face of face loop (selects similar faces BUT it depends on if you clicked on horizonal or vertical edge)

#### SCALE
- S (scale)-> SHIFT + Z (this scales on every axes except Z) 

---

## 14 making a rocky base
- TODO: learn how to use sculting brush

- create a plane -> scale x,y,z to 30x
### sculpting
- start with base shape (*3d shape): create shape (SHIFT + A)-> mesh -> ico sphere

#### SCULPTING WORKSPACE (top menu) 
- change to sculpting workspace
- TODO: SCULPT mode
- DRAW BRUSH (V)
- CHANGE BRUSH SIZE (F)
- TODO: paint (hold left mouse button )

#### Dyntopo - Adding topology complexity (more faces) 
- select sculting workspace (top menu) 
- Dyntopo (top menu) -> checked -> this allows adding more faces to low triangle surfaces 
    -> detail size: size of faces it creates
    -> detailing -> relative detail 
        -> resolution 12: lower number = smaller the faces
        -> changes face size/ detail level depending on how zoomed in you are...
    -> detailing -> constant detail 
        -> resolution 3: higher number = smaller the faces
        -> same face size no matter zoom.
#### GRAB 
    -> sculpting mode -> grab brush
    -> doesnt add faces on stretch
#### SUBTRACT FROM MESH
    -> hold down CTRL while in sculpting mode
    
---

## 15 Decimate modifier
- modifier used to change the poly count
- sculpting workspace -> sculpt mode
- TODO: low poly style

#### DECIMATE 
- modifier panel (wrench) -> TYPE: generate modifier -> DECIMATE -> RATIO (adjust) 
- reducing decimate ratio reduces poly count
- decimate modifier tool -> dropdown -> apply
- show stats -> top main toolbar -> overlays -> statistics
- modifiers need to be applied in object mode
- it is a desctructive workflow -> meaning there is no going back if modifier is applied

#### Proportional editing 
-> edit mode
- sculting toolbar menu -> target like button (o) 
-> then select a vertice 
-> G (to grab)
-> move around vertice + use mouse wheel (affects "circle of influence") to move multiple vertices around
- NB!!! DONT FORGET TO TURN THIS OFF

---

## 16 Snapping
- first scale up/down lighthouse and place ontop rock
- scale down houses
- move houses onto rock
- sculpting workspace -> top toolbar -> snapping (magnet icon) -> use snapping tool if necessary
- OPTION: snap with -> center -> snap to face -> align rotation to target -> aligns to rotation of the object face normal (direction perpendicular to the face)
- OPTION: turn on Project individual elements

### set object origin
- sculpting workspace -> top toolbar -> SNAPPING -> off
- OBJECT MODE -> select object -> main view -> top right -> options -> affect only -> ORIGIN -> SELECT -> moving only affects object origin
- NB!!!! DONT FORGET TO TURN THIS OFF AFTER USE (affect only -> ORIGIN -> 0FF)
OR
- in edit mode, if you move the object, it doesnt move the origin (you are moving whole object away from origin)

## 17 linked duplicates
- changing one item changes the other
- DUPLICATE LINKED (ALT + D) -> creates a linked duplicate
- DUPLICATE (SHIFT + D) -> duplicate (but not linked)

#### LINK OBJECTS TO A PROTOTYPE
- to link an object, select it, then shift + click on the object you want to link to  -> CTRL + L -> link object data

#### SEPARATE OBJECT FROM GROUP PROTOTYPE
- if you want to separage from a group where it was duplicate linked, 
- LAYOUT WORKSPACE -> select the one you want to separate -> object -> relations -> make single user -> object and data

#### Scaling options
- modeling workspace -> default is "medium point" meaning all objects scale to their collective average center
- modeling workspace -> individual origins
NB!!!! DONT FORGET TO TURN BACK TO "medium point" for expected default behavior

---
## 18 material slots
- SHADING workspace
- VIEWPORT SHADING -> working in "material preview" mode
- to drag-close a window, goto the panel top-left corner until cursor changes to crosshair -> then click+drag to the panel that you would like to "consume"
- adding colors to objects by creating materials

#### How to set up one object with 2 materials on it?
- give whole object a material color (eg. house color)
- create the slots
- make use of slots -> each slot gets a material (*material has to exist)
- so you go into edit mode and select the face/s and then assign slot a material

## 19 lighthouse materials
![section01 - introduction - 19-lighthouse-materials.png](./section01-introduction/section01%20-%20introduction%20-%2019-lighthouse-materials.png)

- TODO: lighthouse loopcut + EMISSION materials (emit light)
- loop cut (CTRL + R) AND use mouse wheel to set more cuts -> then click to confirm amount of cuts
- TODO: create material slots x4 (red, white, gray-base, light)
- emission -> strength
- so step is to create the slot, create the material or assign to slot, then with the faces selected, you assign the slot

#### grow selection
- alt + left click on edge -> CTRL + (NUMPAD +) to grow selection
- SHADING WORKSPACE -> Select -> select more or less (CTRL + numpad +/-)

## 20 lighting and atmosphere
![section01 - introduction - 20-lighting-and-atmosphere.png](./section01-introduction/section01%20-%20introduction%20-%2020-lighting-and-atmosphere.png)