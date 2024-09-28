# P1 - Vacuum Cleaner

## States
- SPIRAL
- FORWARD
- BACK
- RIGHT
- LEFT


## Algorithm
The vacuum cleaner starts in the "SPIRAL" state doing a spiral, and remains in the spiral state until de laser detects an obstacle at a distance less than 0.2 or the bumper detects a collision. The next state depends on the location of the obstacle:
- if the obstacle is in front of the vacuum cleaner the state changes to "BACK", in which the robot goes backwards while turning left.
- if the obstacle is on the right the state changes to "LEFT", in which the robot goes backwards while turning left.
- if the obstacle is on the left the state changes to "RIGHT", in which the robot goes backwards while turning right.

The vacuum cleaner keeps on the "BACK", "LEFT" or "RIGHT" state for one second and then the state changes to "FORWARD".

The vacuum cleaner keeps on the "FORWARD" state for three seconds or until either the laser or the bumper detects an obstacle.


## Exploration
Vacuum cleaner exploration's image after 10 minutes:

![Vacuum cleaner image](https://github.com/urjc-docencia-robotica-movil/blog-robotica-movil-24-25-sandrag4/blob/main/files/Image-p1.jpeg "Vacuum cleaner image")


Video:

![Vacuum cleaner video](https://github.com/urjc-docencia-robotica-movil/blog-robotica-movil-24-25-sandrag4/blob/main/files/Video-p1.webm "Vacuum cleaner video")


## Practise difficulties
The robot gotas trapped next to the table and in a room. I solved this problem changing the angular and linear speeds, modifing the duration of algorithm's states and making the robot go backwards when it detected an object close to it.


