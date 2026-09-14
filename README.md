# animController
Animation controller library for Figura  
## how to use
``require(<path to file>)`` at the start of script  
put ``animController.startOfTick()`` at the start of the ``events.tick()`` function  
put ``animController.endOfTick()`` at the end of the ``events.tick()`` function  
put ``animController.init()`` in ``events.entity_init()`` function  
to define exceptions from controller system use ``animController.addOverride(<string: animation id>)`` in ``events.entity_init()`` function before ``animController.init()``    
to register animation keyframe use ``animController.regAnim(<string: name>, <int: duration in ticks>, <int: strength from 0 to 1>, <bool: whether the animation should be paused or stopped>, <int: blend strength vs other active animations>)``  
animations are played similar to blender shape keys, with the shape keys defined via single-keyframe blockbench animations. multiple animations may be blended together.  
## example use cases
with some math this can be used to mimic inverse kinematics for low-segment-count limbs or tails. for something like octopus tentacles it is suggested to use an actual IK library.  
adaptive crouching under blocks for avatars over vanilla player height.  
fluid transition between 'stances' such as a bipedal and quadrupedal slugcat model.
## what this cannot do
there are no pings implemented in animController, if you want to do anything with host functions send the information over pings and call the animation from there.  
if you want to play blockbench animations call the animation as usual, animController is exclusively used for 'shape key animations' and cannot play the full animation.
