# UV Mapping

## 53 section intro
- using photographic images as textures on buildings / 3d models
- start with cube in blender. 

## 54 Basic UV Mapping
- textures.com (subscription based..)

### MATERIAL PREVIEW WINDOW / WORKSPACE
- edit mode -> faces mode -> select all (A)
- primitives shapes come with uv maps.. (except circle) 
- select all (A) -> shows uv map in uv editor..
- right view menu -> material properties -> VIEWPORT display -> turn on backface culling so image maps are not double sided.

### UV EDITOR WINDOW / WORKSPACE 
- NOTE: selecting a face on object only shows individual face on uv editor...
- NOTE: if nothing is selected on 3d model, nothing will show on UV editor
- you can create textures directly in blender -> new image ("test")
- OPTIONAL: change generated type to color grid (THIS IS ONLY IN UV EDITOR...)
- OPTIONAL: NB!!!! selecting face/vertice/edges in (UV editor) while all is showing AND moving it -> affects the whole 3d shape (and surrounding textures) as the edges joining the selected face is being moved.
- NOTE: in uv editor selection, you can also: scale, rotate
- CTRL + SPACE -> window to fullscreen
- WRONG ROTATION: NB!!! if image is mapped wrong onto 3d object, select he affected face (this shows only the face on UV Editor) and then ROTATE

### SHADER EDITOR WINDOW / WORKSPACE
- open shade editor workspace   
- add image texture node (SHIFT + A)
- need to add the image created in UV editor into Shader editor
- TODO: image texture -> click image icon -> "test" (select image created in uv editor)
- TODO: hook up by linking "image Texture node" color with "principle BSDF" color

## 55 UV Islands and Seams
- changing scale of objects will not affect UV's, it will just Stretch them.
- uv islands is the mapping to grouped shapes
- activate by clicking uv selection mode to "ISLAND"
- seams are the outside edges of islands.
- NODE wrangler should be enabled: menu -> edit -> preferences -> add-ons -> search -> node wrangler
- SHADER EDITOR WORKSPACE: with node wrangler enabled... add a new material -> with principle BSDF selected can press CTRL+T (to bring up 3 other nodes: texture coordinates, mapping, image texture)
- UPDATE: the below switch out image texture (SHIFT + S) has been removed from node wrangler
- click on image texture node -> Switch texture (SHIFT + S) ... same as deleting and adding a new "image texture"
- add texture (SHIFT + A) -> musgrave texture (remove default image texture node)
- UV EDITOR WORKSPACE: to see seams, select all (A) from object-> select all in UV editor Workspace -> uv menu (UV EDITOR WORKSPACE)-> show seams from island (shows up as darker orange line on material preview viewport)

### Creating your own UV Map
- delete uv map from uv maps (right viewport)
- select object -> unwrap menu (U) -> unwrap
- object view with object selected -> apply  (CTRL + A) -> scale
- UV Workspace -> unwrap menu (u) -> unwrap

## 56 wooden barrels UV's
- SHORTCUTS: NUMPAD . -> zoom in on object ONLY
- SHORTCUTS: NUMPAD / -> zoom in on object and hide all else 

#### clear seams
- 3d viewport -> EDIT MODE -> select all (A) -> 3d viewport menu -> edge -> clear seams

#### Marking your own seams
- delete uv map
- edit mode -> select all (A) -> unwrap menu (u) -> unwrap
- NO SEAMS? -> edge mode -> alt left click edge -> right click -> mark seam
- barrel texture -> can drag directly from file explorer onto shader editor viewport (one at a time)

## 57 lots of barrels
- technique to reuse texture... just rotate the 3d object to expose different part of uv map
- each unique texture needs a material
- NOTE: when uv's go outside the bounds of the texture, it just repeats itself (ie. the UV shape can be larger than the texture)
- 3d viewport -> if you edgeslide (g + g -> instead of grab (g)) it alows you to move the UV texture AND the edge on 3d object

#### Clamping / edge slide (C)
- EDGE SLIDE -> can be used to change shape of 3d object without changing shape of UVs (G -> G)
- edit mode: edge slide options: clamp (c) DEFAULT IS on (restricts to shape of 3d object) C -> turns it off 

---

## 58 Spitfire plane model
- drag front, top, side images from explorer into 3d viewport.
- ALT + G (remove movement)
- ALT + R (remove rotation)
- after importting images, align them up by using a 3d mesh cube as reference
TIP: you can set 3d cursor (SHIFT + right click) to a new position
- then set transform pivot point (main menu -> transform pivot point -> 3d cursor)

#### TOP, FRONT, SIDE show ref images ONLY
- after setting the box size, object data properties (right viewport) -> empty -> turn off perspective for (top, side and front)

#### mesh auto mirror tool (model only on one side)
- edit -> preferences -> add-ons -> mesh: auto-mirror tool
- menu (N) -> edit -> auto mirror
- auto mirror mirrors around object origin (FIX: set origin to geometry) 
- edit mode, you only model the one side
- side view -> xtray mode + wireframe -> select and model vertices to match plane body

#### square out shape
- reset scale on x (S + X + 0)
- move inwards ( G + X + mouse move)

#### TAIL
- extrude (E) + Z + Z (extrude vertically)
- tail: flatten out on Z (S + Z + 0) 
- EDGE -> g + g -> move mouse -> CLICK TO CONFIRM
- rear fins: select faces -> inset (I)

## 59 plane body / 60 MAKING THE WINGS
- Practicing G + G + slide on X and Z
- and S + S and setting x to 0

## 61 completing the plane model

### set origin on vertex
- EDIT MODE: select vertex -> SHIFT + S -> (while holding it down...) -> select cursor to selected
- add cylindar (nose of plane) -> change to 8 vertices -> rotate 90 (R + X + 90) 

#### SOLIDIFY modifier -> Thickness to shape
- to add thickness -> modifiers -> solidify
- settings: offset is the direction the thickness protrudes forward or backward
- apply the scale (CTRL + A) -> scale
- twisting propellars: select outside 3 edges of propellar -> proportional editing (on) (shortcut O) -> use mouse wheel to control the circle of influence
- then R + Z (rotate only on Z)
- ensure the propellar head is center with pivot point 
- create linked duplicate (alt + D) -> rotate 120

## 62 unwrapping the plane
- if you are using mirror modifier / auto mirror -> the uv map are ontop of each other
- so the body's mirror modifier should be applied
- the propellar should not be mirrrored
- the wings, cockpit and tail should be mirrored
- create seams and unwrap

## 64 texture the body
#### project from view
- 3d object view -> edit mode -> select all (a) -> if you unwrap (u) -> project from view
- uv's appear on uv editor and they appear same as layout on sideview

## 65 - PREPARING FOR ANIMATION

#### Grouping with "Empty"
- use an empty to group objects together for easier animation: add (shift + A -> empty -> plain axes)
- ensure its at center of plane
- put everything in plane collection
- select all (A) -> then make empty the active object (shift select the empty)
- 3d viewport -> top menu -> object -> parent -> object (CTRL + P)
- now moving the empty moves the whole plane
- children can be moved independently of the parent (empty)

#### THE propellar nose parent system
- with the nose selected, move the cursor to selected...
- create a circle empty 
- set up propelar with parent controller (empty) -> so the blandes and nose are selected, then select the propellar controller (selected last)
- object -> parent -> object (CTRL + P)
- rotate on Y axis

#### connect the propellar controller to the plane controller
- select propellar controller, then select plane controller (ORDER IMPORTANT) -> then CTRL + P 