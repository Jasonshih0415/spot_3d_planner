# spot_3d_planner
3D planner with squat function,  RRL-ALeRT 


## Installation

### Dependencies

move base flex:
https://github.com/METEORITENMAX/move_base_flex
or
https://github.com/naturerobots/move_base_flex

octomapping:

https://github.com/RRL-ALeRT/octomap_mapping

webots spot mbf octo branch:
https://github.com/MASKOR/webots_ros2_spot/tree/mbf_octo_nav


### Building
Clone octo_navigation: https://github.com/RRL-ALeRT/octo_navigation
and
mbf and in one workspace and colcon build.

## Start

Start in different terminals:

`ros2 launch webots_spot spot_launch.py`

`ros2 launch webots_spot octo_nav_launch.py`

`ros2 launch octomap_server octomap_webots_launch.py`

`ros2 run bringup exe_path_node`

`ros2 run astar_octo_planner posture_manager`

`rviz`

### Send a Goal in cmd
Type `ros2 action send_goal /move_base_flex/move_base mbf_msgs/action/MoveBase "t<tab>`

The message is autocompleted when typing " and the letter of the first arg of the message.

```
$ ros2 action send_goal /move_base_flex/move_base mbf_msgs/action/MoveBase "target_pose:
  header:
    stamp:
      sec: 0
      nanosec: 0
    frame_id: ''
  pose:
    position:
      x: 3.0
      y: 0.0
      z: 0.0
    orientation:
      x: 0.0
      y: 0.0
      z: 0.0
      w: 1.0
controller: ''
planner: ''
recovery_behaviors: []"
```

### send a goal in RVIZ
send 2D nav goal in RVIZ windows

### experimental result
| 2D Navigation (A* Planner) | 3D Navigation (Crouch Algorithm) |
| :---: | :---: |
| ![2D Demo](https://github.com/Jasonshih0415/spot_3d_planner/blob/main/astar_2d_planner/docs/2Dplanner.gif) | ![3D Demo](https://github.com/Jasonshih0415/spot_3d_planner/blob/main/astar_2d_planner/docs/3Dplanner.gif)|

Based on: https://github.com/skpawar1305/easy_3D_navigation/blob/main/plan_3d_path.py