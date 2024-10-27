# P3 - Obstacle Avoidance

## Attractive force
The target absolute coordinates into coordinates relative to the car pose. The relative coordinates are divided by the relative distance to the target in order to scalate the magnitude of the attractive vector.  
  
  
## Obstacle force
The distance to the obstacle is decomposed into x and y coordinates using this formula (the angle is the index of the laser ray in radians):    
> obstacle_x = distance * sin(angle)  
> obstacle_y = -distance * cos(angle)  

For each laser ray, it is checked if there's an object near the car. The distance is scalated taking into account the distance to the car, the nearest the object is to the car, the strongest will be its repulsion. The resulting repulsive vector is calculated by calculating the media of the distances where the laser ray detected and object (after scalating the distances).  
  
  
## Average force
The sum of the attractive and repulsive vectors. The x and y coordinates of both the attractive and repulsive vectors are multiplied by some scalating factors.  
> x_average = ax * x_target + bx * x_repulsive  
> y_average = ay * y_target + by * y_repulsive  

If the repulsive x coordinate is too strong, the car won´t move forward or will move too slowly as the average x coordinate would be negative or too small to attract the car. If the repulsive y coordinate is too weak, the objects won't generate enough repulsion and the car will crash. So the x and y coordinate of both the attractive and repulsive vectors have different multiplying factors in order to allow the car to have the right angular speed to avoid the obstacles without making the car have a too slow or negative linear speed.  
  
  
## Speed
The linear speed is equal to the x coordinate of the average force vector. np.clip is used to limit the maximun speed of the car. The angular speed arctangent of the division of the y coordinate of the average vector by x coordinate of the average vector.  
  
  
## Get next target
When the car is close to a waypoint, the target is set as reached and gets a new target. The distance to decide whether or whether not the car has reached the waypoint is separated into the x and y coordinates.  
  
  
## Video
[Video](https://urjc-my.sharepoint.com/:v:/g/personal/s_gonzaleza_2022_alumnos_urjc_es/ERTERLDccN9BiunPgwLdz6wBHWHGCI6X6-775Sq3Ei0mBA?nav=eyJyZWZlcnJhbEluZm8iOnsicmVmZXJyYWxBcHAiOiJPbmVEcml2ZUZvckJ1c2luZXNzIiwicmVmZXJyYWxBcHBQbGF0Zm9ybSI6IldlYiIsInJlZmVycmFsTW9kZSI6InZpZXciLCJyZWZlcnJhbFZpZXciOiJNeUZpbGVzTGlua0NvcHkifX0&e=Q6lmDf)
