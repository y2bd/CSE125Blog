---
layout: post
title:  "Project Specification"
categories:
- design
- planning
permalink: project-spec
description: The specification of our CSE 125 project
---

## Table of Contents

1. [What kind of game?](#what-kind-of-game)
1. [What are the goals?](#what-are-the-goals)
1. [How is it unique?](#how-is-it-unique)
1. [Features](#features)
1. [Who We Are](#who-we-are)
1. [Communication](#communication)
1. [Development](#development)
1. [Schedule](#schedule)

## What kind of game?

The game we have in mind is a multiplayer puzzle-platformer with a mix of both cooperative and competitive elements. Set on a Space Prison set to crash, four robot inmates have to work together and escape before time runs out. However, there's a reason the robots are in prison, and they might have ulterior motives that prevent them all from making it out.

## What are the goals?

The primary goal is to escape the ship before it explodes. There will be an assortment of puzzles throughout the ship that the players have to find and solve (some solo, some cooperative) if they want to successfully escape. However, the players will be individually given a secret mission of their own that they have to complete in order to escape--even if the escape pods are primed and ready to go, a player cannot leave (and therefore win) unless they've completed their secret mission.

The secret missions can be completely benign, such as extracting some data from the Space Prison via a terminal, or maybe *destroying* that data so it cannot be extracted by a salvage crew. It can also be insidious, such as preventing another player from escaping by any means necessary. Regardless, secret missions will be antagonistically designed--players' missions should work against each other such that it's not realistically possible for all players to escape.

To accomplish this, there will be traps throughout the ship that players can secretly trigger. Be careful, as you cannot escape the ship by yourself--cooperation is necessary.

## How is it unique?

Our game blends cooperation and competition. The puzzles will require multiple players to work together if they wish to solve them, so no single player can go rogue at the beginning in an attempt to save everyone else. The threat of the secret missions is constantly looming over the players though, which means you can never fully trust your fellow escapee.

The nature of the game also lends itself towards some form of randomness and procedural generation, whether that be in the secret missions given at the start, or the puzzles that players have to solve, which means that every round of the game will be a different experience.

## Features

### The Bare Minimum

* First-Person controls (mouse and keyboard)
* Different colored boxes for each player
* Players can move and jump around
* A basic cooperative puzzle (i.e. having everyone stand on different pressure plates)
* A simple trap (i.e. being able to trigger a trap door)
* An "exit" area that if everyone reaches ends the game in a win
* A timer that ends the game in a loss if it runs out
* Joining a game hosted by a fixed server instance

### Must Have

* A singular robot model that has different textures for each player
* Some basic prison-esque hallway environment for players to navigate
* Collision with walls
* Lighting
* At least three puzzles that need to be solved in order to escape (we want rounds to last 10-15 minutes at the minimum)
* At least three traps that can be triggered
* A basic "don't let player X escape" goal given to each player
* Beginning screen that explains rules
* Persistent UI displaying timer

### Would Be Awesome

* Shadows and other more detailed lighting effects
* Some non-linearity in prison environment (not just a straight path to end)
* Modeled prison cell for start room
* Modeled escape pods for exit room
* Controller support
* Player collision (cannot walk through other players, possibly can jump on top of other players)
* At least six different puzzles present with varying difficulty
* At least six different traps present throughout
* "Interactable" props, such as Computer Terminals or Storage Containers
* More complex secret missions (such as "retrieve data from Terminal" or "destroy files in Container")
* Persistent UI for displaying secret objective
* Respawn mechanism (you don't die, you just get delayed)
* Ambient spaceship sounds (machinery, air vents, that kind of stuff)
* Lore-friendly way of displaying countdown timer (can be on an electronic sign, or displayed on computer terminals)
* Voice-over for introduction

### If We Have The Time

* Works on Windows, Mac, and Linux
* Separate models for each robot
* Walking and interaction animations for robots
* Large non-linear prison environment (easier to get separated and launch traps)
* Detailed environments with non-essential props (for design and world-building)
* At least ten different puzzles present
* At least ten different traps present
* Interactive computer terminals that let you access security cameras, disable lighting, trigger traps
* Can host and join games (rather than hard-coded server IP)
* Random missions assigned each round of the game
* Some procedural generation in map design (perhaps pre-designed rooms that are randomly connected) 
* Background music and interaction sound effects (i.e. walking, traps being activated, buttons being pressed)
* Awesome Main Menu

## Who We Are

Our team features

* Bert, our gameplay programmer and artisan
* Dexter, our other gameplay programmer and touring voice talent
* Elton, the first networking expert (both client *and* server!)
* Jason, yet another gameplay programmer, possible composer, and chief blogger of the blogosphere
* Jeffrey, our graphical guru and 3D modeler
* Pavan, the second expert in networking (both TCP *and* UDP!)

We're working on a consensus--we vote for all decisions, but give credence to those working in the particular field being discussed. In the event of a catastrophic tie, Dexter is tall and imposing and therefore probably will be the tie-breaker.

## Communication

We have a Slack room set up for all communication. Besides normal class meetings, we're also currently planning a meeting on Monday (full details to be decided by an outgoing Doodle poll). Jason and Jeff are also coincidentally roommates, which means the drama of 125 will never truly escape them.

We'll be using Slack for communication and GitHub for collaboration, so anyone who needs to disappear will alert us on Slack, and perhaps file an issue on GitHub if there's a problem that they cannot finish on their own time.

We'll be following our schedule as tightly as possible. As we already have a general consensus on must/should/hopefully features, we'll be trimming features in that order if time doesn't permit us to finish absolutely everything.

As chief blogger, Jason is in charge of writing these lovely and lengthy status reports.

## Development

Our specific development roles are mentioned above under [Who We Are](#who-we-are).

Our project will be developed in C++ using the OpenGL graphics library (and the latest-and-greatest at that). Specifically, our graphics expert Jeffrey has a really nice graphical engine that he developed during the course of CSE167. Not only does it have very pretty (and performant) visual effects, it was also designed to be modular, which means that it hopefully won't be terribly difficult to use it for our project. 

For programming our Windows developers will be using Visual Studio, and our Mac developers XCode. Thanks to the power of OpenGL, we hope to have our game running on multiple platforms.

We'll be using some common libraries in our development, such as GLFW for windowing and input, SOIL for texture loading, ASSIMP for mesh loading, GLM for math, and FMOD for sound.

## Schedule

|            | Design                | Graphics                   | Art                                                      | Networking                                | Physics                          | Gameplay                                                                                        | Extras                       |
|------------|-----------------------|----------------------------|----------------------------------------------------------|-------------------------------------------|----------------------------------|-------------------------------------------------------------------------------------------------|------------------------------|
|   Week One | General Idea/Concept  | Modularize Graphics Engine | Art-Style Research                                       | CSE124 Review                             |                                  | Gameplay Research                                                                               |                              |
|   Week Two | Puzzles               | Asset Loading              | Environment Art, Basic Character Model                   | Basic Client/Server TCP Architecture      | Acceleration Structures          | Local Movement                                                                                  | Configuration-based Setup    |
| Week Three | Puzzles, Level Design | Environment Rendering      | Environment Art                                          | Design Framing (General Packet Structure) | Naive Collision                  | Local Basic Puzzle                                                                              |                              |
|  Week Four | Puzzles, Level Design | Point-Light Shadows        | Character Design                                         | Game Engine Networking Integration        | Better Collision                 | Multiplayer Movement                                                                            | Basic UI                     |
|  Week Five | Puzzles, Level Design | Lighting Enhancements      | Character Design, Prop Design                            | Debugging Networking Integration          | Debugging Multiplayer Collisions | Multiplayer Basic Puzzle                                                                        | Controller Support           |
|   Week Six | Puzzles, Level Design | Particle Systems           | Environment Polish, Music Composition                    | Implementing Extra Messages As Required   | Debugging Multiplayer Collisions | Environment Implementation (Keylocked Doors, Passworded Terminals, etc.), Puzzle Implementation |                              |
| Week Seven | Puzzles, Level Design | Graphical Effects Polish   | Environment Polish, Music Composition                    | Implementing Extra Messages As Required   |                                  | Puzzle Implementation, Trap Implementation                                                      | UI Polish                    |
| Week Eight | Game Balance, Testing | SSAO                       | Character/Prop Polish, Music Composition, Sound Design   | Debugging Full Networking                 |                                  | Puzzle Implementation, Trap Implementation                                                      |                              |
|  Week Nine | Game Balance, Testing | SSAO                       | Character/Prop Polish, Character Animation, Sound Design | Debugging Full Networking                 |                                  | Random Puzzle Selection (Procedural Generation), Puzzle Testing                                 | Cross-Platform Compatibility |
|   Week Ten | Game Balance, Testing | Configurable Graphics      | Character/Prop Polish, Character Animation, Sound Design | Hostable Servers                          |                                  | Random Puzzle Selection (Procedural Generation), Puzzle Testing                                 |                              |
