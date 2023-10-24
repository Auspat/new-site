---
title: "Quick Overview of My Projects This Past Year (+ Code)"
date: 2023-10-22T16:35:05+02:00
tags: 
- Unity3D
- 2022
- 2023
categories:
- "Portfolio"
draft: false
weight: 1
cover:
    image: thumbnailDevLog.JPG
    caption: 'Click the Youtube icon below to watch my video quickly explaining the games I worked on this past year.'
---
[![Youtube Icon](/smallYoutube.png#center)](https://youtu.be/0AIlBhPH_10)
## Projects from Game Design I and II 

I learned many valuable game design skills from these projects such as ***Scripting***, creating ***Animations***, modifying in-game ***Physics***, designing ***UI/UX Designs***, ***Version Control***, creating ***Shaders***, ***Asset Management***, working with ***NavMesh*** and ***Terrain Generation***, ***Sound Design***, optimizing the game for ***Minimal Lag***, formulating a ***Design Document***, and developing a solid ***Foundation in Unity 3D***. 

![Unity Gif](https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExNm83bnVoZDQwMGM3ajQ4ajRnOWxzcTlxdWwwcWcxZnI0YXNpN2l6aSZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/sBLyUWF44XvDeOp5s1/giphy.gif#center)

## Project 1: ***Calypso's Dating Sim***

- **Description:** This was my first Unity project I worked on, and I learned all about the basics of game mechanics, timers, win/lose conditions, colliders, and UI/UX implementation. I go more into the story and gameplay in my video!
- **Code and Software:** 
![Title Screen](/5NightsTitleScreen.png#center)
The image above showcases the simple UI that I created for my first game. I was also able to incorporate a score, timer, and day counter as well as various difficulty levels into my game. More gameplay can be seen in my video.
![Code1](/5NightsCode1.png#center)
A few notable pieces of code I created used Coroutines to count time within the game since every level last a specific amount of time. I also used a Coroutine to spawn new clouds (good or bad), which players must collide into to build up their score.
![Code2](/5NightsCode2.png#center)
- **Links:** [Design Document](https://drive.google.com/file/d/1wiDwkc-ctDMuHqEkdKGQ55_R4emfkmaT/view?usp=share_link), [Play the Game](https://auspatgames.itch.io/5-nights-at-calypsos-dating-simulator) <-- This game is fairly small so I was able to get it to play on itch.io, which uses WebGL to run games on the web.

## Project 2: ***Escape From Cerce's***

- **Description:** To make this game, I experimented with Unity's built in terrain generation tools to create an island home to the troublesome witch Cerce. I designed clues that would guide the player (Odysseus) through the map and help him find the secret ingredient that would cure his lost crewmates. This game also required logic that would only activate the next clue on the map if the previous clue was found.
- **Code and Software:** 
![Terrain Generation](/CirceCode3.png#center)
The above showcases a terrain I built using Unity's 3D terrain generator tool. I learned how to create land formations and add trees, shrubs, and paths into my world. 
![Code1](/CirceCode1.png#center) 
The first set of code defines win and lose conditions that a player can have during play. I also made sure to connect these conditions to a UI that would show on the screen signaling the player's outcome. 
![Code2](/CirceCode2.png#center)
This was a simple yet effective set of code that activated a player's clue on the screen for 7 seconds. If a player entered a certain area that had a clue, they would be prompted with the clue that leads them to the next clue spot on the map.

## Project 3: ***Argos: Death has Passed***

- **Description:** This was my first group project I was a part of, and I was in charge of linking everybody's work together and designing the UI. This was an unusual task because we had not learned version control yet, so I was grabbing and combining code and assets that were not initially designed to work together. I had to be creative in my methods, so I learned how to transfer game characters from one game to the other by changing the main camera and input system to work for a specific character. I also worked with invisible colliders that would activate the next sequence in the game. Overall, I would say the story of this game was the best so far, and I geuninely enjoyed working with other talented artist and game designers on this project. 
- **Code and Software:** 
![Title Screen UI](/ArgosUI1.png#center)
This is the title screen of the game I created in a group of 5. I created the UI for the game and incorporated the beautiful assets that my team member created. 
![Code1](/ArgosCode1.png#center)
Because I did not know how to combine all the games that my team members created into one game with different scenes, I had to mess with activating and deactivating certain objects based on which game was currently being played. This required me to keep the GameManager script incredibly organized and learn how to activate and deactivate the mainCamera and player objects.
![Code2](/ArgosCode2.png#center)

- **Link:** [Design Document](https://drive.google.com/file/d/1hSJFIfPMnX2mOvqyHb5PhRPGTSRvK6oZ/view?usp=share_link) <-- Shows the plan my team and I had for creating this game

## Project 4: ***German Final***

- **Description:** This game was inspired by 4 works of German literature, and features dialogue options between the player and npcs. Different outcomes would occur in the game depending on your dialogue choices. I also learned how to traverse the Unity Asset store for free FX like fire and fireworks, as well as useful building assets like houses and castles. This enhanced the story, by making the player feel like they were a part of these books. 
- **Code and Software:** 
![Unity Editor 1](/GermanPic2.png#center)
I learned how to better use Unity's particle system from this project. This is helpful for creating my own desired particle effects to help enhance the narrative of a burning building in my story.
![Code1](/GermanPic1.png#center)
I also hard coded dialogue options that npc's would ask the player and run a specific outcome in the game depending on how the player chose to respond.

## Project 5: ***Changed***

- **Description:** This was one of my favorite projects to work on because I got to design and implement one of my favorite parts about games: powerups. _Changed_ is a game about the grotesque transformation of Daphne into a wooden chair as she is trying to escape her perpetrator Apollo. The wooden chair must now find a way to escape the house, by collecting powerups that "change" the wooden chair's form. I had a good time creating the powerups for the chair as well as creating the level design for this eerie puzzle escape room.
- **Code and Software:** 
![Unity Editor 1](/ChangedPic.png#center)
For this game, I was in charge of creating a puzzle sequence the player must solve to escape the house. I created a room consisting of three pushable inclines that players must maneuver into the correct spots to create the entire incline staircase.
![Unity Editor 1](/ChangedCode1.png#center)
The whole house had powerups that the main character Daphne, the chair, needed to collect in order to solve the puzzles. The code above is the logic for activating these powerups based on if they have been collected in the level and if a keystroke was pressed. In addition, this code changes the visuals of the chair depending if it needs to be a normal chair, sofa chair, or reclined chair. I also needed to assign a 'state' value to each powerup that would dictate type of movement in the switch-case statement below.
![Unity Editor 1](/ChangedCode2.png#center)

- **Link:** [Extensive Design Document](https://drive.google.com/file/d/10p2Z8GrlEzbboqvJASbFBGn-j74SNEDx/view?usp=sharing)

## Project 6: ***The Boss's Web***

- **Description:** This game was all about a humble office worker's attempt the break free from his dead-end job. He unlocks the metaphorical gun of creativity and must use that to fight his boss and free his coworkers! I worked on Scene Management and on the boss stage in this game, where I learned how to create a spray-paint-like weapon, a NavMesh, and work with enemy animations that trigger whenever a worker-enemy gets "freed."
- **Code and Software:** 
![Boss Fight](/BossPic1.png#center)
This above photo shows the NavMesh I generated in Unity. This is effectively the path that worker-enemies are able to run along, when chasing the player. This gives plenty of room for the player to weave in and out of certain areas to have enough time to turn and shoot his weapon of creativity. I also added the simple animation state machine for the enemies. By default, the enemies would spawn and run toward the player. If they get shot by the player's weapon, their dance animation would play instead of their run animation.
![Boss Code1](/BossCode1.png#center)
The first set of code is an OnTriggerEnter function that occurs whenever the enemy collides with the weapon blast or the player. The player's score is added if the enemy is hit by the weapon, but a life is lost if the enemy collides with the player. I also activate a new wave of enemies once a specified amount of enemies have been "freed."
![Boss Code2](/BossCode2.png#center)
This final piece of code controls the swapping of scenes within this game. I set a trigger, so when a player holds E on the object this script is attached to, the scene will swap to the next level.
- **Link:** [Extensive Design Document](https://drive.google.com/file/d/12xruYI-HIXZ3LY3m21qes45ZVLjsOOiR/view?usp=share_link)