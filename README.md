# tortoisebot_pro_max_docs
# TortoiseBot Pro Max

ROS1 Noetic and ROS2 Galactic is installed in TTB PM. By default Noetic is sourced every time a terminal is opened. 

We assume that you have a Laptop or a System that is running Ubuntu 20.04 with ROS Noetic installed.

## Master slave

We will be making the robot as a Master and the Laptop /PC as slave device:

1. First connect HDMI cable between robot and monitor screen.
2. Turn on the robot by pressing the switch at back side of robot , this will play a tune from buzzer which assures everything is turned on.


https://github.com/rigbetellabs/tortoisebot_pro_max_docs/assets/68866046/2c493ec8-bb67-4689-9b6a-07f4356fadd2




3. Once display is turned on connect to Wi-Fi.
4. Get IP address of TortoiseBot Pro Max by following command:
    
    ```bash
    hostname -I 
    ```
    
5. Same command is to be used to get IP address of your system (i.e. Laptop/PC)
6. The following is to be done in ubuntu of Laptop/PC:
    
    Lets open the ***.bashrc*** file manually.
    
    In order to do that, open the ***home directory*** of your system (Laptop /PC).Press **Ctrl + H** to unhide the files as ***.bashrc*** is a hidden file. Add the below commands at the end of ***.bashrc***
    
    ```bash
    export ROS_MASTER_URI=http://{ip of TortoiseBot Pro Max}:11311
    export ROS_HOSTNAME={ip of your system}
    
    #for example
    export ROS_MASTER_URI=http://192.168.0.166:11311
    export ROS_HOSTNAME= 192.168.0.125
    ```
    
7. For SSH
    
    ```bash
    ssh username@IP_address
    ```
    Username of TTB PM is iisc1 , iisc2 , iisc3 , iisc4 , iisc5. Username of particular robot can be found below the robot on a sticker. 
    
8. Password for all robot is same and it is 
    
    ```bash
    rbl@IISC 
    ```
    rbl is in smaller case and IISC is in upper case. 
    

## Bring Up

It provides roslaunch scripts for starting the TortoiseBot Pro Max base functionality.

```bash
roslaunch tortoisebotpromax_firmware bringup.launch
```
This is to be done in robots terminal

By default robot will take encoder feedback during its motion . If PID is to be turned off than a  parameter pid:=false is to be passed.

```bash
roslaunch tortoisebotpromax_firmware bringup.launch pid:=false
```
This is to be done in robots terminal

## Teleoperation's

```bash
rosrun teleop_twist_keyboard teleop_twist_keyboard.py
```
This is to be done in robots terminal. Max linear speed is to be kept  0.2 m/s and max angular speed 1.0 rad/sec 

## Battery charging

1. Robot is to be turned off before charging it and robot is not functional during charging.


![IMG_5349](https://github.com/rigbetellabs/tortoisebot_pro_max_docs/assets/68866046/75f57d17-3f63-4695-8b93-144b57174b1f)
This is how charger is to be plugged in 

![IMG_5350](https://github.com/rigbetellabs/tortoisebot_pro_max_docs/assets/68866046/f0574e65-3252-468c-b316-51d31e6083b5)
Green light on MAINS ON and CHARGER ON indicates that charging process is going on smoothly. 

When battery is low , it will show indication on universal cell indicator as well as buzzer will start beeping as show in video



https://github.com/rigbetellabs/tortoisebot_pro_max_docs/assets/68866046/8559076f-9bc4-4f4e-8a57-7fbb2fcb2fc0


