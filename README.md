# animController
Animation controller library for Figura  
## how to use
``require(<path to file>)`` at the start of script  
put ``animController.startOfTick()`` at the start of the ``events.tick()`` function  
put ``animController.endOfTick()`` at the end of the ``events.tick()`` function  
put ``animController.init()`` in ``events.entity_init()`` function  
to define exceptions from controller system use ``animController.addOverride(<string: animation id>)`` in ``events.entity_init()`` function before ``animController.init()``    
to register animation keyframe use ``animController.regAnim(<string: name>, <int: duration in ticks>, <int: strength from 0 to 1>, <bool: whether the animation should be paused or stopped>, <int: blend strength>)``  
animations are played similar to blender shape keys, with the shape keys defined via single-keyframe blockbench animations. multiple animations may be blended together.  
## example use cases
with some math this can be used to mimic inverse kinematics for low-segment-count limbs or tails. for something like octopus tentacles it is suggested to use an actual IK library.
