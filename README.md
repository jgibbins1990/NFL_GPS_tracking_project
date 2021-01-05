# DSI_Capstone

## README: James Gibbins DSI Capstone - V1.1

### INTRODUCTION

Hello!

This project aims to use GPS tracking data of NFL players to predict the outcome of passing plays after 1 second of movement. The 

The project on this notebook uses data sourced from the 2021 NFL Big Data Bowl hosted by kaggle:
https://www.kaggle.com/c/nfl-big-data-bowl-2021/overview




### GLOSSARY OF TERMS (for the unfamiliar with NFL):

Field: The NFL field is 120 yards by 53.3 yards - with the 10 yards at each end being the scoring zones

Offense: the team which is attempting to progress the ball down the field and ultimately score

Defense: conversely the team attempting to prevent the offense from progressing

Line of Scrimmage: The imaginary line that represents the offense’s progress prior to the play, it is the line on which the ball is positioned at the start of each play.

Ball Snap: This is the first moment the play is live and the ball is moved by the offence team

Pass Forward: On each play the offensive team is allowed to pass the ball forward only one time

QuarterBack (QB): The specialist passer - the player on each team who almost always passes the ball forward

Receiver (Rec): Each offense has a number of receivers who try to get open (in space away from the defenders) in order to catch a pass from the QB

Down: The offensive team has 4 attempts (or downs) to progress the ball 10 yards closer to the defending team’s end zone

### DATA:

The data provided is GPS tracking of players on passing plays. The data covers all 32 teams from the 17 weeks of the 2018 season. 

Each play is broken down in to frames of 0.1 second time increments. 

The tracking data includes x and y coordinates for each player relative to the field yardage (x= 0 - 120 , y = 0 - 53.3). Also speed, acceleration and distance measurements.

Data also includes player orientation and direction of travel as a bearing where 0 degrees is parallel to the y axis. 

![alt text]()






FEATURE ENGINEERING / DATA SELECTION:

In order to reduce the complexity I have limited my analysis to only frames relating to the ball snap, pass_forward, pass_forward + 0.5 seconds (p5 in the notebook) and pass_forward + 1.0 seconds (p10 in the notebook)

I am using featuring engineering to extract players movements relative to each other for each of these frames and changes between the frames.
 
MODELLING:

I use a metric known as EPA (expected points added) to measure the success of the play.

I have binarised this metric based on the median, so that if the epa is greater than the median the play is considered successful for the offense and vice versa for the defense.

I complete binary classification modelling on features I have engineered from selected frames of each play to predict the outcome of the play and whether the offense or defense has been successful.

CONCLUSIONS:

Thanks for reading!
