# P2 - Follow Line


## Type of controller 
The angular speed is controlled by a PD controller. The P (proportional) component of the controller is proportional to the error, when the error increases, the angular speed will increase and when the error decreases, the angular speed will decrease. The D (derivative) component of the controller is the difference between the error and the previous error, when the error is greater than the previous error, the angular speed will increase and when the error is lesser than the previous error, the angular speed will decrease. The derivative component reduces oscillations.

The linear speed is controlled by a P controller, when the error increases, the output of the P controller increases, and when the error decreases, the output of the P controller decreases, this output is subtracted from a maximum linear speed and the result will be the carś linear speed.


## Trials
First, I got the image and i made the car move.
Then, I adjusted the proportional component of the PD controller so that the car didn´t crash at the turns.
After adjusting the proportional component, I adjusted the derivative component of the PD controller in order to reduce oscillations.
Then, I decided to look for red pixels in more than just one row, so the car doesn´t crash if doesn´t find a red pixel in one row.
After that, I changed the color filter to hsv because I had problems with white walls.
Then, I adjusted the PD values for the ackermann circuit.
Finally, I created a P controller for linear speed.



## Videos
Simple (67 seconds):
[Video Follow Line Simple](https://urjc-my.sharepoint.com/:v:/g/personal/s_gonzaleza_2022_alumnos_urjc_es/EYLZFPliDcBChcbPTkojzsYBskt69Z4Xi5aZDprr_Dwu9w?nav=eyJyZWZlcnJhbEluZm8iOnsicmVmZXJyYWxBcHAiOiJPbmVEcml2ZUZvckJ1c2luZXNzIiwicmVmZXJyYWxBcHBQbGF0Zm9ybSI6IldlYiIsInJlZmVycmFsTW9kZSI6InZpZXciLCJyZWZlcnJhbFZpZXciOiJNeUZpbGVzTGlua0NvcHkifX0&e=uczLS3)


Simple Ackermann (183 seconds):
[Video Follow Line Simple Ackermann](https://urjc-my.sharepoint.com/:v:/g/personal/s_gonzaleza_2022_alumnos_urjc_es/EcFjIiM-IRtHphgd-5dimJgB09wRic83je6FpcJ1t8Yx0Q?nav=eyJyZWZlcnJhbEluZm8iOnsicmVmZXJyYWxBcHAiOiJPbmVEcml2ZUZvckJ1c2luZXNzIiwicmVmZXJyYWxBcHBQbGF0Zm9ybSI6IldlYiIsInJlZmVycmFsTW9kZSI6InZpZXciLCJyZWZlcnJhbFZpZXciOiJNeUZpbGVzTGlua0NvcHkifX0&e=ClRodh)


Montmelo (127 seconds):
[Video Follow Line Montmelo](https://urjc-my.sharepoint.com/:v:/g/personal/s_gonzaleza_2022_alumnos_urjc_es/EQuNysvADqVJuSljjH7loCkBJPtM6C4u73AMhHAIHhq7fw?nav=eyJyZWZlcnJhbEluZm8iOnsicmVmZXJyYWxBcHAiOiJPbmVEcml2ZUZvckJ1c2luZXNzIiwicmVmZXJyYWxBcHBQbGF0Zm9ybSI6IldlYiIsInJlZmVycmFsTW9kZSI6InZpZXciLCJyZWZlcnJhbFZpZXciOiJNeUZpbGVzTGlua0NvcHkifX0&e=ppIEw1)


Montmelo Ackermann (437 seconds):
[Video Follow Line Montmelo Ackermann](https://urjc-my.sharepoint.com/:v:/g/personal/s_gonzaleza_2022_alumnos_urjc_es/EQQ6Jhtny1dMrR2cJabpvw0B3w6YYL_2mM6BTSx95wJG0g?nav=eyJyZWZlcnJhbEluZm8iOnsicmVmZXJyYWxBcHAiOiJPbmVEcml2ZUZvckJ1c2luZXNzIiwicmVmZXJyYWxBcHBQbGF0Zm9ybSI6IldlYiIsInJlZmVycmFsTW9kZSI6InZpZXciLCJyZWZlcnJhbFZpZXciOiJNeUZpbGVzTGlua0NvcHkifX0&e=OzSZnd)



## Difficulties
I had problems with the color filter because the white wall was detected as red, i solved this problem by changing the color filter to hsv.

Another problem was that when the car reached the left turn, it crashed because it didn´t find any red pixels in the row in which it was searching, so I solved this by making the car search for red pixels in other rows until it finds one.

