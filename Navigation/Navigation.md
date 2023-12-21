# Mapping


## GMapping

Terminal 1:

```bash
roslaunch king gmapping.launch
```

Move around the robot till you have scanned the complete room. 

Terminal 2:

```bash
rosrun teleop_twist_keyboard teleop_twist_keyboard.py cmd_vel:=/king/cmd_vel
```

![Gmapping](/media/gmapping.png)

Now in order to save the map use the following commands:

Terminal 3:
```
cd <location to save map>
rosrun map_server map_saver -f map
```

![Scan](/media/MapScan.png)

# Localization
## AMCL

Terminal 1:

```bash
roslaunch king localization.launch
```

Terminal 2:

```bash
rosrun teleop_twist_keyboard teleop_twist_keyboard.py cmd_vel:=/king/cmd_vel
```

Now after you move the robot a little you will be able to see that it is able to localize itself properly.

![Localization](/media/localization.png)

# Navigation

Terminal 1:

```bash
roslaunch king navigation.launch
```

Use RVIZ for 2D Navigation

![Give Navigation](/media/navigation1.png)
![Robot goes to point](/media/navigation2.png)
