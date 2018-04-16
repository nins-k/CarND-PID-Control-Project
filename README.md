## Udacity SDCND - Term 2, Project 4

### **PID Controller** ###
---

#### 1. Describe the effect each of the P, I, D components had in your implementation.

**Proportional Term:** This term indicates by what degree the vehicle should move towards the center. Higher the value, sharper will be the turn towards the desired location. To make the transition natural and evenly paced, the proportional factor for this term has been set to `-0.25`. This results in a relatively smooth curve towards the center.

**Integral Term:** This term is used to offset any systemic bias in the vehicle. However, for this project, I found that using an integral term is detrimental to the performance of the controller. This could be because there is no systemic bias or because it is too small. So, for my implementation the proportional factor for the integral term is set to `0.0`.

**Derivative Term:** This term helps to reduce the oscillatory movement of the vehicle as it over-shoots the desired location. By setting it to the correct value, the error converges and stays close to 0 instead of over-shooting. For my implementation, the proportional factor of the derivative term is set to `-0.45`.

#### 2. Describe how the final hyperparameters were chosen.

The hyperparameters were chosen purely through experimentation.

Initially, the proportial parameter (Kp) was found to be optimal at a range of **[-0.5, -0.25]**. Next, the derivative term parameter (Kd) was experimented with in a range of **[-1, -0.5]**. Using the integral parameter (Ki) resulted in very unstable driving and it was finally set to **0**.

Lastly, tuning the Kd term further and making a slight adjustment to **-0.45** gave the best results.