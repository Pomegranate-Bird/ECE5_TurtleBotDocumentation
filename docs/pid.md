## Controlling a TurtleBot
---

### PID Controllers & TurtleBot Kinematics:

**Control Theory Background:**

PID controllers, otherwise known as Proportional–Integral–Derivative controllers, are tools used to regulate the behavior of a system. They originate from a field called control theory, which focuses on creating mathematical models of systems. By developing a mathematical model, engineers can design control functions that produce desired outcomes and ensure the system behaves in a stable and predictable way.

---
## Differential Drive Model:

Our TurtleBot is an example of a control system. The kinematics of the TurtleBot can be described by the differential drive model. Unlike a car, which uses a steering joint to turn its front wheels, our TurtleBot turns by varying the speeds of its two wheels. By increasing the speed of one wheel and decreasing the speed of the other, the robot can rotate left or right.

![Differential Drive Robot: TurtleBot](pictures/kinematicsv2.png)

---

## Proportional Intergral Derivitave Controller:

![Block Diagram Of A PID Controller ](pictures/pid.png)

---

**Explaining each term of the controller:**


![The PID Equation ](pictures/pid_equation.png)


**P:** 
    Proprotional term of the controller measures the current error of the system. 

The proprotional term of the controller calculates how off the robot is from the black line. That error is then mutliplied by a gain which is used to steer the robot  back onto the black line. 

**I:** 
    Integral term of the controller occumulates past-errors over time. 

The Integral portion of the controller is useful in reducing steady state error. It allows the robot to stay some threshold within the objective. By measuing that the accumulation of previous errors is decreaing it allows the robot to stay within proximity of the line even if it's not exactly spot on.


**D:** 
    Derivitave term of the controller measures the rate of change of the system. 

The Derivitave portion of the controller is useful in reducing oscilations. By measuring the rate at which the error is changing the derivitave portion of the controller reduces how much the robot overshoots the line.

**K Terms:**
    All of the K terms are constant-terms decided by the user, they're not random, they're discoevered by trial and error in a process called tunning. The K terms decide how aggressively the PID components will contribute to the outcome. We tune these values using the potentiometer onboard the robot.

**Sp:**
    The nomial speed of the robot, the base the speed will move without the PID's influence. 
---

## Competition PID Values: Theory In Action

*Track 1:*

![Drag Race:](pictures/drag_race.png)


**Sp: 65** 

**P: 50** 

**I: 0** 

**D: 0** 

The track was relatively simple, it didn't have big turns or strange geometry. Allowing us to focus simply on speed

*Track 2:*

![Loop:](pictures/pear_track.png)

The Loop track was simple enough that we didn't have to modify  our PID values to drastically. The geometry was also realtively simple.

**Sp:55** 

**P:50** 

**I:** 

**D:** 


*Track 3:*
![Frequency Race:](pictures/frequency_race.png)

The frequncy track's geometry was rather complex, full of turns and sharp corners. To avoid overshooting and having a spiriling error, we decided that a lower speed would be best. The lower speed allowed us to complete a good portion of the track. Given more time, could've better tuned for the frequency track. 

**Sp:25** 

**P:30** 

**I:** 

**D:** 



