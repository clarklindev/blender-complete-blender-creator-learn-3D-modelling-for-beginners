# Section 05 - rigging and animation (lesson 71-86)

## 71 - intro
walk cycle - playing animation over and over when specific button pressed

## 72 basic animation
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
## 78 the modifier stack
## 79 blob man
## 80 rig ready meshes
## 81 building the armature
## 82 IK and parenting
## 83 weight painting
## 84 animating the walk cycle
## 85 animated textures
