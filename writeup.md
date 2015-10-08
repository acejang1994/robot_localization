# robot_localization

## What was the goal of your project?
The goal of the project was to use a preloaded “map” of an area outside AC328 and have our robot localize itself in the space using particle filter.	
## How did you solve the problem? (Note: this doesn't have to be super-detailed, you should try to explain what you did at a high-level so that others in the class could reasonably understand what you did).
First we have collected a scanned data for a map, saved it as a file. A set of particle cloud was put in a map, and by using a particle filter and laser scan, we were able to update the location of the particle. For incorporating the laser scan data, the closest distance laser data was used to redistribute (re-weight) the particles that were spread out near the position of a robot. 
## Describe a design decision you had to make when working on your project and what you ultimately did (and why)? These design decisions could be particular choices for how you implemented some part of an algorithm or perhaps a decision regarding which of two external packages to use in your project.
We used the robot’s lidar data to update the particle weights. If the robot’s lidar data did not match up with the particles, then the weights were readjusted to a low number. We decided to incorporate the lidar measurements of all angles to make the function more accurate. Even though 360 measurements for each particle may be computationally tolling, thanks to Paul’s pre written function, it was not that bad.
## What if any challenges did you face along the way?
Updating the position of the particles based on the odom coordinate system. Calculating the new position and angle with respect to the world took as some time to figure out with math on the board. 
## What would you do to improve your project if you had more time?
If we had more time we would wish to improve the project by making the filter more robust, since the particle cloud was sometimes fuzzy. Also possibly adding a feature to reset the particle filters once the filters get lost would have been more helpful. Once the particles “lose” the robot’s location, it is hard to recover.
## Did you learn any interesting lessons for future robotic programming projects? These could relate to working on robotics projects in teams, working on more open-ended (and longer term) problems, or any other relevant topic.
We found using the particle filter and the math behind it very interesting. Particle filters are very well known and sometimes being at Olin, we don’t get many chance to deal with theoretical methods. It was great using the filter for a lab and understanding it thoroughly. 
