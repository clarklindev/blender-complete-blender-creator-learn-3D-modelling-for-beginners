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
- right view menu -> material properties -> turn on backface culling so image maps are not double sided.

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
