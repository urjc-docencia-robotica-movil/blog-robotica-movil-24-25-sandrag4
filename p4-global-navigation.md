# P4 - Global Navigation

## Search algorithm
### Wave Front Algorithm
Step 1. Insert Target Node into priority queue: When a target is selected, it is added to the beginning of the priority queue.

Step 2. Pop node from priority queue: The node with the lowest cost is popped from the priority queue and its cost is added to the cost grid.

Step 3. If node_coord distance >= end_distance End: If the distance from the target to the current popped node is greater than the distance from the target to the car plus an additional cost, bfs search finish.

Step 4. If node_coord == obstacle Save to another list and goto Step2: If the node popped corresponds to the coordenate of an obstacle, the coordenate is added to the obstacle list and the next coordenate is popped from the priority queue. 

Step 5. Assign weight to neighbors of node_coord if previously unassigned: If the node popped doesn't correspond to an obstacle, the neighbours to that node are obtained. If the neighbours haven't been in the priority queue yet, the distance to the neighbour is calculated by adding the distance to the node plus the distance from the node to the neighbour.

Step 6. Insert neighbors of node_coord to priority queue: The node's neighbours are added to the priority queue.



## Cost grid
### Gradient Path
The cost of each node is normalized and converted into an integer number, the result is added to the cost grid.

### Obstacle cost
After creating the cost grid of the wave front algorithm, an extra cost is added to the cells that are near an obstacle. The extra cost depends on the distance to the obstacle. This new cost is normalized and id added to the cost grid.



## Navigation method 
Step 1. Get car's position: The car coordenates and distance to target are obtained.

Step 2. Check if target reached: If the target has been reached, the car stops and wait until a new target is selected.

Step 3. Get car neighbours: All the neighbours in an area surrounding the car are obtained.

Step 4. Choose the neighbor with the lowest cost: The car will go in the direction of the neighbor with the lowest cost.

Step 5. Calculate the distance and the angle between the neighbour and the car

Step 6. Calculate turning angle: The resulting angle will be the difference between the neighbour angle and car_world.jaw.

Step 7. Set angular and linear speed: If the turning angle is too big, the car will only turn, if not, the car will turn and move foward in the established angular and linnear speeds.



## Results
[Video](https://urjc-my.sharepoint.com/:v:/g/personal/s_gonzaleza_2022_alumnos_urjc_es/EflTZ51wlihNuxcEclqeMsgB9AhpxRib1t2z9Qs9SQnh6A?nav=eyJyZWZlcnJhbEluZm8iOnsicmVmZXJyYWxBcHAiOiJPbmVEcml2ZUZvckJ1c2luZXNzIiwicmVmZXJyYWxBcHBQbGF0Zm9ybSI6IldlYiIsInJlZmVycmFsTW9kZSI6InZpZXciLCJyZWZlcnJhbFZpZXciOiJNeUZpbGVzTGlua0NvcHkifX0&e=DDolRr)



## Difficulties
- Coordenate system and turning angles. Navigation didn't work correctly when the neighbour angle and car_world.yaw were near pi because turning angle was supposed to be small butresulted in a value near 6 or -6, I solved it by adding 2pi when the turning angle was lower than -pi and subtracting 2pi when the angle was greater that pi.

- Number of cells to add extra cost. If the number of cells near an obstacle with an added extra cost is too big, the car will get stuck in narrow streets, if the number of cells with an extra cost is too low, the car could crash with the walls. I tried different numbers of cell until I found one which didn't make the car get stuck or crash.

