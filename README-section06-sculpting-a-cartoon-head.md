# section 06 - cartoon head sculpting (lesson 87-99)

## 87 - intro
- sculpt a cartoon head

## 88 - base shape
- sculpting workspace (show brush names -> drag out button panel towards right)
- viewport overlays -> show x,y axis
- viewport overlays -> show statistics
- viewport overlays -> show origins (only visible in object mode) -> CTRL + TAB (mode menu)
- add uv sphere 

#### turn on x symmetry
- sculpting workspace -> sculpt mode -> main view -> symmetry button -> turn on "x" symmetry

#### adding topology (faces) with remesh
steps:
1. sculpting workspace (CTRL + TAB -> sculpt mode)
2. set voxel size (smaller number more faces) - in sculpt mode -> press R (shows interactive grid overlay - voxel size - good size is 0.06) 
3. remesh (CTRL + R)

#### image reference
- if you want to use an image as reference, SHIFT + A -> image reference
- then right panel -> object properties -> viewport display -> in front
- then right panel -> object data properties -> empty -> opacity -> 50%

#### Grab brush
- ensure symmetry is turned on for X axis
- basic shaping with grab brush (big shapes / structure before detailed shapping)
- resize brush (F -> move mouse)

#### mask brush
- mask brush -> masks out areas not to be affected by other brushes
- clear mask (alt + M)
- invert mask (CTRL + i)

#### snake hook brush
- paints a snake like object

#### inflate brush
- inflates the shape

#### mirror
- to mirror the horn -> add modifier -> picker to select the object to use as the origin
- apply scale: CTRL + A (set scale) 

#### sculpt mode jump between objects
- jump between selecting objects (ALT + Q) while over an object (flashes red)
- draw sharp brush
- blob brush / 

#### 96 PAINT
- paint brush in sculp mode
- different to texture painting (which needs to be unwrapped) but if high quality mesh, app will crash when unwrapping
- change color of paint brush (solid mode)
- to get color from sculpting workspace (the painted) to the material workspace -> goto right panel object data properties -> color attributes -> color (new after paint)
- shift A -> input -> color attribute
- hook up the color attribute color -> to the principle BSDF (base color)
- store colors in color palette -> new
- to erase a color -> paint over (can change alpha)

#### 98 lighting
3 point light system
1. front light - area light -> top view / front right -> power 1000w -> grab yellow dot point towards character
- can soften shaddows by changing the size (scale eg. 9 the light larger to soften shadows)
2. fill light -> duplicate the first light (move to other side) -> make size really big (bigger than 1st light) -> reduce light to 200w
3. back light -> moved to back right (same height as object) -> outer glow -> power 3000w (blue color) 
3. back light 2 -> duplicate for left side