# tortoisebot_pro_max_docs
# TortoiseBot Pro Max

ROS1 Noetic and ROS2 Galactic is installed in TTB PM. By default Noetic is sourced every time a terminal is opened. 

We assume that you have a Laptop or a System that is running Ubuntu 20.04 with ROS Noetic installed.

## Master slave

We will be making the robot as a Master and the Laptop /PC as slave device:

1. First connect HDMI cable between robot and monitor screen.
2. Turn on the robot by pressing the switch at back side of robot , this will play a tune from buzzer which assures everything is turned on.


https://github.com/rigbetellabs/tortoisebot_pro_max_docs/assets/68866046/2c493ec8-bb67-4689-9b6a-07f4356fadd2




1. Once display is turned on connect to Wi-Fi.
2. Get IP address of TortoiseBot Pro Max by following command:
    
    ```bash
    hostname -I 
    ```
    
3. Same command is to be used to get IP address of your system (i.e. Laptop/PC)
4. The following is to be done in ubuntu of Laptop/PC:
    
    Lets open the ***.bashrc*** file manually.
    
    In order to do that, open the ***home directory*** of your system (Laptop /PC).Press **Ctrl + H** to unhide the files as ***.bashrc*** is a hidden file. Add the below commands at the end of ***.bashrc***
    
    ```bash
    export ROS_MASTER_URI=http://{ip of TortoiseBot Pro Max}:11311
    export ROS_HOSTNAME={ip of your system}
    
    #for example
    export ROS_MASTER_URI=http://192.168.0.166:11311
    export ROS_HOSTNAME= 192.168.0.125
    ```
    
5. For SSH
    
    ```bash
    ssh username@IP_address 
    ```
    
6. Password for all robot is same and it is 
    
    ```bash
    rbl@IISC
    ```
    

## Bring Up

It provides roslaunch scripts for starting the TortoiseBot Pro Max base functionality.

```bash
roslaunch tortoisebotpromax_firmware bringup.launch
```

By default robot will take encoder feedback during its motion . If PID is to be turned off than a  parameter pid:=false is to be passed.

```bash
roslaunch tortoisebotpromax_firmware bringup.launch pid:=false
```

## Teleoperation's

```bash
rosrun teleop_twist_keyboard teleop_twist_keyboard.py
```

## Battery charging

1. Robot is to be turned off before charging it and robot is not functional during charging.

![This is how charger is to be plugged in ](TortoiseBot%20Pro%20Max%20f0ce33822aa94f279912c5c3022acd82/IMG_5349.jpg)

This is how charger is to be plugged in 

![Green light on MAINS ON and CHARGER ON indicates that charging process is going on smoothly. ](TortoiseBot%20Pro%20Max%20f0ce33822aa94f279912c5c3022acd82/IMG_5350.jpg)

Green light on MAINS ON and CHARGER ON indicates that charging process is going on smoothly. 

When battery is low , it will show indication on universal cell indicator as well as buzzer will start beeping as show in video



https://github.com/rigbetellabs/tortoisebot_pro_max_docs/assets/68866046/8559076f-9bc4-4f4e-8a57-7fbb2fcb2fc0


