# Section 05 - rigging and animation (lesson 71-86)

## 71 - intro
walk cycle - playing animation over and over when specific button pressed

## 72 basic animation
[![youtube](https://img.youtube.com/vi/GOFQtg2VLDk/0.jpg)](https://www.youtube.com/watch?v=GOFQtg2VLDk)
[![youtube](https://img.youtube.com/vi/4IPTW8OPFyc/0.jpg)](https://www.youtube.com/watch?v=4IPTW8OPFyc)

- animation workspace
- if you have keyframes (not at start) but you want to animate Y, you need to add the position keyframes on start frame too.

#### Rendering video / still frames
- output properties -> set framerate (25fps) would mean 2seconds on dope sheet viewport is 50 frames
- move to frame 50 on dope sheet
- mouse over 3d viewport and move the object
- insert keyframe (I) or Key button on dope sheet viewport
- to move keyframes, move mouse over keyframe then Grab (G) -> and drag 
- note by removing y,z location... you can change the z to move cube above floor which would adjust all frames as there is no z property

#### render properties:
1. set output folder
2. file format -> ff mpeg
3. output quality -> perceptually lossless
4. encoding speed -> slowest
5. change resolution % for tests

#### ANIMATION STEPS 
1. set timeline at correct position
2. move object
3. insert key frame (i)

## 73 record button
- dope sheet viewport -> record button: if you turn this on, making adjustments will auto add keyframes

- to record light, select light -> right panel object data properties for light -> right click on color -> insert keyframe

## 74 the graph editor

[![youtube](https://img.youtube.com/vi/-HL4m3S-lao/0.jpg)](https://www.youtube.com/watch?v=-HL4m3S-lao)

Lecture thumbnail

- use graph editor to position elements in relation to origin point
- use duplicate (shift + D) duplicate across time line  
- graph shows object origin over time (duration) in x,y,z axis 
- pivot to cursor (scale in relation to playhead)
- change graph height (CTRL + middle mouse button hold in... then move mouse button up and down)
- change interpolation (similar to ease animation functions) -> mouse select key then T
- for ball bounce, interpolation should be bezier with the arms of the bezier keyframe "brought in" so curve becomes sharp
- speed up animation: in graph editor -> move playhead to first frame (point of reference) select so keyfram is white -> then select all frames (A) -> graph editor menu -> pivot point (2d cursor) -> scale (s) + x -> scale only on X with reference to pivot 
- can adjust the duration the ball stays on top by playing with the curve (pivot point -> individual centers) -> select all -> drag out so it rounds out the graph

## 75 bone basics

- makes a worm animation
- bones requires vertices to deform
- EDIT MODE: add loop cuts (CTRL + R) -> roughly 10 cuts
- add subdivision surface modifier
#### BONES (armature)
- bones are called armature made up of one or more bones
- SHIFT + A -> armature
- right panel -> data object properties (stick man icon button) -> viewport display -> in front

#### BONE MODES
- bones have 3 modes:
1. object
2. edit (build the bone skeleton)
3. pose mode for animating

# attach a bone
- EDIT MODE: select bone (end joint) -> extrude (E)
- duplicate a selection of bones -> then select the one you want to connect -> then select the one you want to connect to last -> parent (CTRL + P) -> connected

## 76 animating bones

[![youtube](https://img.youtube.com/vi/LrpL66bbayw/0.jpg)](https://www.youtube.com/watch?v=LrpL66bbayw)

- select bone and skin and apply rotation (CTRL + A) with the objects already positioned origin center 0,0,0
- reset positions to center of world (ALT + G)
#### only bones have pose mode 
- set up animation cycle in pose mode

#### set up relationship (SNAKE TO BONES)
1. NB ORDER IMPORTANT: select snake object first then select the bones second (bones become the parent)
2. set parent to (CTRL + P) armature deform -> with automatic weights 

- then in object mode: select just the snake *(without the bones) and go into weight painting mode 

#### weight painting
- see the influence a certain bone has on the shape
- area in red is fully influenced by the bone
- area in blue is infleunced less by bone
- pinching occurs when rigging with low poly models
- FIX: more topology and more bones for smoother transition

- object mode is for moving entire object around scene
- POSE MODE is for animating animation cycles on the spot

#### animating bones
- POSE MODE
- select all bones
- dope sheet 
- keyframe at 0 for all bones (on rotation and location)
- for loop animation should start on frame 0 to not miss any frames
- use timeline to record
- move to frame (eg 25)
- animate character (snake)
- note if animation should return to starting position , you can duplicate the original keyframes and add keyframe inbetween
- to duplicate: move playhead to destination keyframe -> select all bones to animate -> duplicate (shift d) (summary - top frame for all elements)
- the animation is looped by setting the start/end frame on the timeline

## 77 subdivision surface modelling

![section05 - rigging and animation - 77-subdivision-surface-modelling.png](./section05-rigging-and-animation/section05%20-%20rigging%20and%20animation%20-%2077-subdivision-surface-modelling.png)

- add auto mirror: 3d viewport -> menu (n) -> edit -> auto mirror (turned on via preferences add-ons -> mesh:auto-mirror) -> x-axis, orientation: positive
- add subdivision surface modifier: levels view: 3, render: 3

## 78 the modifier stack

![section05 - rigging and animation - 78-modifier-stack.png](./section05-rigging-and-animation/section05%20-%20rigging%20and%20animation%20-%2078-modifier-stack.png)

### the tv screen: 
- inset (i) moves edges closer to sides 
- boundary (b) to exclude inset for mirror
- BUT is easier to separate screen from tv -> select -> right click -> separate
- stack is important, mirror should usually be first
- then subsurface modifier

## 79 blob man

![section05 - rigging and animation - 79-blob-man.png](./section05-rigging-and-animation/section05%20-%20rigging%20and%20animation%20-%2079-blob-man.png)

- select all group to new collection (M)
- move head to 4m 
- then cursor to world origin (SHIFT + S)
- create neck (cube) -> auto mirror on X

## 80 rig ready meshes

![section05 - rigging and animation - 80-rig-ready-mesh.png](./section05-rigging-and-animation/section05%20-%20rigging%20and%20animation%20-%2080-rig-ready-mesh.png)

- bevel (CTRL + B) around shoulder, arm and wrist joints then use mouse wheel to add extra loop cut
- bevel (CTRL + B) cut around knee, foot
- A shaped figure instead of T 
- move 3d cursor around shoulder joint, change pivot point (transform pivot point) -> 3d cursor

## 81 building the armature
- add armature -> select armature (bone) -> object data properties (right panel - skeleton icon) -> viewport display -> in front
- TODO: be able to disconnect a bone from its parent and reconnect to another bone
- ensure arm roll is about the same: N (menu) -> transform -> Roll -> 220degrees for arm bones
- duplicate arm bones for leg bones -> roll 270 (the roll should be adjusted so the face is flat towards the camera in front orthographic view) for all bones
- parent leg bones to base bone of the spine

#### mirroring bones
- for bone mirroring to work, you need to label bones (F2)
- so select the bone then F2 to label 
- the spline bones dont need to be mirrored but the arm and leg bones need specific labelling syntax
- NB: use separator _l eg. thigh_l
#### valid separators
1. nothing -> handLeft -> handRight
2. _ underscore -> hand_L -> hand_R / hand_l -> hand_r
3. . dot -> hand.l -> hand.r
4. - dash -> hand-l -> hand-r
5. space -> hand LEFT -> hand RIGHT

- will also work if Left/Right part are before the name
- can only use L/R shorthand syntax if you use a separator
- select all the bones to mirror -> right click -> symmetrize

## 82 IK and parenting 

![section05 - rigging and animation - 82-ik-and-parenting.png](./section05-rigging-and-animation/section05%20-%20rigging%20and%20animation%20-%2082-ik-and-parenting.png)

- inverse kinematics - setting that up with our rig
- parenting mesh to our bones
- with forward kinematics -> each bone needs to be moved into position
- with inverse kinematics -> there are extra bones (pole target and controller/target) -> way of rigging so you only need to move the base bone in the chain (eg bones of the leg)
- so moving the controller/target which always points to pole target
- TODO: create 2 new bones by extruding from joint: one at back of foot -> one at front of knee (roll -90 deg)
- TODO: clear parent the new bones
- TODO: EDITMODE: all the pole and controller/target bones -> bone object properties -> "Deform" should be turned off so mesh wont try stick to the bones
- move pole target bones infront away from the knee (this is where the controller/target will point to) 

#### setting up IK (5min54sec)
- MODE: POSE -> be in pose mode
- select 2nd bone in leg chain
- go to bone constraints panel (right panel) -> add bone constraint -> tracking -> inverse kinematics
    ##### Target
    - 1. choose target -> tell it which armature we are using -> armature
    - 2. choose bone -> target_l

    ##### pole target
    - 1. choose target -> tell it which armature we are using -> armature
    - 2. choose bone -> pole_l

- at this point the bones rotate messed up (automatically)
- FIX: chain length -> length of leg chain -> 2
- FIX: pole angle -> 180 degrees -> foot should now point towards pole target
- symetrize to other size -> all bones on left side selected (including pole and controller/target)-> go into edit mode -> rightclick -> symmetrize

#### set up mesh / bone relationship
- the pose mode animation relies on the fact that in edit mode the roll angle of the faces of the bones are pointing directly forward when in front view 
- select mesh first -> then select bones -> parent (CTRL + P) -> with automatic weights
- for the head select the tv and all its components, then select the bone (active) -> parent (CTRL + P) -> set parent to -> bone

## 83 weight painting

![section05 - rigging and animation - 83-weight-painting.png](./section05-rigging-and-animation/section05%20-%20rigging%20and%20animation%20-%2083-weight-painting.png)

- go out of pose mode -> object mode -> select character -> then weight painting
- object mode -> select armature (BONES) first -> then SHIFT + select mesh -> then go into weight painting mode -> now you can hold down control (CTRL) and click and see the weight of each section
- now you can hold ALT + click on a bone to weight paint each bone
- adjust weight and paint more (value 1)-> or adjust and paint less (value 0)
- change brush size (F)

#### resets
- RESET rotations: select all (A) -> reset (ALT + R)
- RESET movement: select all (A) -> reset (ALT + G)

## 84 animating the walk cycle

[![youtube](https://img.youtube.com/vi/rWQ4zNpXShI/0.jpg)](https://www.youtube.com/watch?v=rWQ4zNpXShI)

- animation workspace
- add plane (SHIFT + A -> geometry-> plane) 
- remove transform (ALT + G)
- open reference walk cycle image
- 24 frame animation cycle is easier to divide
- 0 and 24 are the same
- rendering our animation should start on frame 1 (blender default for walk cycles) so as not to have jitter
- 12 is the inverse (arms / legs)
- 3,6,9 is same as 15(flipped 3), 18(flipped 6), 21 (flipped 9)
- ensure all bones selected -> create the initial pose and duplicate the pose on frame 24 
- make dopesheet / timeline 24 frames

#### flipped poses
- to copy a flipped pose -> eg. frame 0 and frame 12 same -> select all (A) -> right click -> copy pose (CTRL + C)
- goto frame 12 -> paste flipped (SHIFT + CTRL + V)

#### record only location + rotation
- active keying set allows you to record only specific user decided
- timeline workspace -> keying -> active keying set -> location + rotation
- create frames 3, 6, 9 from reference pic
- dope sheet viewport -> select frame 3 
- in 3d viewport -> select all bones (a)
- create key frame for all objects (i)

#### copy and paste as "flipped keyframes"
- select frames 3, 6, 9 from dope sheet summary (top keyframe)
- in 3d viewport copy (CTRL + C)
- in dope sheet -> goto frame 15 and "paste flipped"

## 85 animated textures

[![youtube](https://img.youtube.com/vi/-G8b1kTMvLE/0.jpg)](https://www.youtube.com/watch?v=-G8b1kTMvLE)

- https://www.pexels.com/
- imported filename needs to be short 
- watch out for load errors in shader editor -> properties -> image source errors
- need to set frames (eg 150 frames)
- link video (image) to color of principled BSDF 