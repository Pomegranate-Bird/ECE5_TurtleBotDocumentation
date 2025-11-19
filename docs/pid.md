## Controlling a TurtleBot
---

### PID Controllers

**Background on Control Theory**

PID controllers otherwise known as Proportional Integral Controllers are a type of tool utilized to control the behavior of a system. PID controllers originate from a field called control theory, control theory specializes in creating mathematical models of systems. By creating a mathematical model of a system, it allows you to design functions which produce desired outcomes.

**Example:**

Our TurtleBot is an example of a system. The kinmatics of our TurtleBot can be described by the Differential Drive model. Since our TurtleBot dosen't have a steering joint between the two front wheels like a regular car, it turns by varing the speeds of both it's wheels. 

![Differential Drive Robot: TurtleBot](pictures/kinematicsv2.png)


## The Differential Drive Model


**Proportional Intergral Derivitave Controller:**

![Block Diagram Of A PID Controller ](pictures/pid.png)


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
    All of the K terms are constant-terms decided by the user, they're not random, they're discoevered by trial and error in a process called tunning. The K terms decide how aggressively the PID components will contribute to the outcome.





