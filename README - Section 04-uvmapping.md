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