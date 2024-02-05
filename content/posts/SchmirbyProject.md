---
title: "IVAR Project: Schmirby's Dream Land"
date: 2024-01-29T14:58:30+01:00
tags: 
- Unity3D
- XR
- 2023
- 2024
categories:
- "Portfolio"
draft: false
weight: 1
cover:
    image: SchmirbyCoverImage.png
    caption: 'Learn about the Interaction in VR and AR project I worked on this year'
---

## The Idea:

- **Description:** In my 'Interaction in VR and AR' class, I was tasked to create a locomotion and interaction system in Unity that is compatible with the Meta Quest 3. I had creative freedom to choose the type of mechanics I wanted to implement, so I chose something fun. I will be responsible for implementing Kirby's movements from the popular nintendo game and essentially create a game level Kirby to manuever through. First things first, I need to avoid copyright issues, so I am going to swap Kirby's name to Schmirby and make it blue!
- **Presentation:** 
[Here](https://docs.google.com/presentation/d/1iF5zFbb3bYlbZXEG_geaAm82yk57mykjUJOxrxhwAeY/edit?usp=sharing)
I have linked a presentation of my project above, which describes an overview of what I will need to implement for this project. I have separated my work process into 4 steps from this point forward: Locomotion -> Interaction -> Player Testing -> Polishing. I will work to implement each step in order to finalize my vision of making "Schmirby's Dream Land."

## Step 1: ***Locomotion***

- **Description:** Schmirby is a creature like no other. It takes big gulps of air that give it an upward jump boost. Schmirby is only able to suck the air a total of 4 times, before it has to release it and float down. Therefore, I need to implement a mechanic in VR to activate his jump and I need to keep track of how many jumps Schmirby has used. On top of this, I need to find a way to move around directionally, so the player can control the blue puffball's movement without relying on the VR joystick. 
- **Solution:** 
For the jump, I tracked the y-axis velocity of the left and right controller. The jump action will execute whenever the y-axis velocity of both controllers is above a certain positive threshold. This will simulate Schmirby having to move its arms up in order to get a big jump. I set a cooldown to avoid the spamming of jumps and also kept track of the amount of jumps it has taken, reseting everytime Schmirby touches the ground. Here is a snippit of the code I used:
![Jump Code](/jumpScreenshot.PNG#center)
This code takes in the left and right hand controller's velocity and sends it to the JumpCooldown function, where it will test if the y-axis postive velocity of the controllers both reach above a certain point. This if-statement also checks if Schmirby is grounded and if Schmirby has a valid jump count to continue jumping.

- For the directional movement, I decided to track that based on the downward rotational shift of the headset. This felt like the most natural type of movement, as it does not require any button presses, and it takes care of movement in 360 degrees, based on head tilt. If a player wanted to move Schmirby forward, they would need to tilt their headset forward at least 5 degrees. This works with tilting backward, left, right, and any direction in between those options. If the player wanted to stay still, they would need to keep their head upright, so that no head downward rotation is detected over 5 degrees. This method worked fairly well, and Schmirby now has a way to float around during its jumps. 
![Headset Rotation Code](/headsetScreenshot.PNG#center) 
This code tracks the Quaternion of the headset and stores it into an Euler Angle. I then use this data to track the tilt of the headset activating a directional input for Schmirby if there is more than a 5 degree tilt in a certain direction. I used ChatGPT to help me find the local Euler Angle on the x and z-axis. This helped solve the problem I was having where the directional input was only working if you faced one direction in the room. Now, the code is able to detect directional tilt input no matter which way the player is facing. 

- With my last locomotion technique, I wanted to give the player the freedom to move around on the ground, so I kept track of the left and right controllers positive velocity on the z-axis and let Schmirby move on the ground in whatever direction the player's head was tilted as long as the left or right controller detected movement in the z-axis. This will require players to move their arms in a waddle like pattern in order to make Schmirby move. 
![Waddle Code](/waddleScreenshot.PNG#center) 
I created this isWaddle() function, which checks the left and right z-axis velocity of the controllers and only returns true when both controllers are in movement. I integrated this function into the headset rotation code, so Schmirby will only be able to move if its hands are moving or if it is not grounded.

## Step 2: ***Interaction***

- **Description:** I was also tasked with designing a way to move an object in VR. I needed to create something to go along with my story of Schmirby. What are its powers? I thought long and hard on this and gave him the power to turn into the shapes it itself eats. In my game, there are 3 objective games you will need to play where Schmirby has turned into a 'T-shape' and it must find a way to orient itself to fit through the 'T' and sometimes 'I' shaped holes that are in the walls blocking its path.  
- **Solution** 
I designed rotation of this 'T-shape' object by detecting the rotation of the headset. Similar to how I detect directional movement in Schmirby, I detect the tilt the player wants to move this shape. I set the threshold to 15 degrees in order to start rotation in a certain direction, and I keep spinning the shape until the player's head reaches the upright position again. This was an intuitive way of rotating the shape based on head movement, and it creates a satisfying puzzle to solve trying the fit Schmirby's new shape through the wall. To move Schmirby toward the wall, I assigned that forward translation to activate with a right trigger press. The shape is reset if any part of Schmirby collides with the wall he is trying to fit through.
![Interaction Code](/rotationScreenshot.PNG#center)
This is the code I implemented for moving the T-shaped Schmirby character. It works similar to the headset movement implentation; however, this time it rotates the shape in the player's head tilt rotation until the player's head is upright. I used ChatGPT here to figure out why my rotations were occuring in rolation to the shape and not in relation to the world. It turned out all I needed to do was add Shape.World to the end of my Rotate() functions, and that would change to rotation to the version I wanted. 


## Step 3: ***Player Testing***

- **Description:** All good games require player testing, and this rule is especially important for VR games. I need to keep track of enjoyment in my game as well as perceived motion sickness. The movement is decently slow due to the slow nature of the falls, but it is always a good idea to check and tweak. I will also be looking for suggestions to make the game more enjoyable and immersive. As of writing this, my game is playable; however, I have not put a lot of work into polishing the sound and environment designs, so it does not feel Schmirby-esque, so to say. But I look forward to hearing what my test subjects have to say about the mechanics and ways I can improve this experience.
- **Results** 
I collected stats based on time to complete track 1/2/3, time to complete objective 1/2/3, coins collected on those tracks, and mistakes made on those objectives. For the 3 people I tested, the average speed of track 1/2/3 was 52.62/48.06/41.49 seconds respectedly. The average objective time for objective 1/2/3 was 123.99/16.41/14.17 seconds respectedly, and the coins collected for each track was 14/20/29 for tracks 1/2/3, and the mistakes made on obj 1/2/3 was 10/1/0 on average. In terms of motion sickness, the average score was a 3/10, indicating lower sickness when playing. In terms of presence, the average score was a 5/10, which can be attributed to the game still being in its early stage of development. The average score for fun had was also a 5/10, which shows there is potential in the game, but it is not the greatest experience yet for a game. My test subjects stated jumping around was fun, but it was a little confusing to move anywhere specific unless you trained a bit with the movement. I also had a comment stating the interaction task was an interesting idea, but the execution is not where it should be for controlling the shape in space. I will discuss in the next session how I plan to use this data to make better iterations of my game in the future. [Click Me For Full Data!](https://docs.google.com/spreadsheets/d/1O_tYp9dDRWMj7ryyk5Mby2kbmz56dnCKVizakVexRNY/edit?usp=sharing)

## Step 4: ***Polishing***

- **Description:** I want my game to be an immersive experience for players. I want them to feel like they have become Schmirby, and they leaving on a grand adventure. In order to bring my bare-bones project to life, I must add sound effects for Schmirby's jumps and collisions. I can even add a light-hearted copyright free soundtrack in the background to set the tone of this fun adventure. On top of all of this, I will need to fix the environment to suit the setting of Schmirby's adventure. I want the setting to be in the clouds with obstacles to jump over, so that requires some light tweaking of the environment I was given. 

- **Future Implementation:** I received comments about some bugs in my game, like Schmirby loading into the scene backwards or players clipping through the map in the end of the race. These bugs take a lot away from the presence of the game, and I would like to patch them. In addition, I was not able to work on the story component or the UI of the game as much due to time, so that is something I would definitely want implement to make the player more engaged with the world. For instance, I would like to add a cutscene where Schmirby eats the T-Shape object and transforms into the T-Shape. This will make that transition from locomotion to interaction much more seamless. 

## Final Playthrough

- **Description:** Your name is Schmirby and you are trying to set a new record in Dream Land, a racetrack like no other. It requires the runners to know how to jump really high and contort their bodies in remarkably unique shapes. There are records for fastest times, most coins collected, and least mistakes made. Your wish is to set a world record for all these stats in one race. Good Luck Schmirby!

- **Final Version Video:** 
[Click Me!](https://youtu.be/fFJNRx3Wpk4)