# Dungeon of Doom, CW2 (CM10227) 

This project was created as the second coursework for CM10227, Dungeons of Doom. The terminal-based game begins with the player spawned on a rectangualr grid (the map). This map contains gold tiles, exit tiles, empty tiles, and walls. The goal of the game is for the player to move around the grid to collect the gold, then find their way to an exit tile in order to leave the dungeon and win the game. 

## User Actions & Notes

#### 1. Configuration Instructions

The game is played via the terminal/command line. Navigate in the command line to where the source code is contained (e.g. in the src folder), and compile the java files using 'javac *.java'. Then, in order to play the game, enter 'java GameLogic' and the game will begin.

#### 2. Using a Different Map

Upon starting the game, the user is promoted to enter a map. The map text files should be placed in the root project folder.  Map file names should be of the form 'name.txt' and to find the map you only need to write 'name' into the console when asked for the map name.

Note that after three failed attempts to search for a suitable map file, a default map is used for the game, and the user plays using this map. 

#### 3. How to Play
Upon successfully running the game you will be told to enter a map name. After a map is chosen a message describing which dungeon you are in appears and the game begins. You can start straight away via the commands described below. 

Moreover, the player is able to move around and inspect the map by typing one of several commands into the console: 

1. **HELLO**: Displays amount of gold needed for the player to collect to win the game.
2. **GOLD**: Displays the current gold owned by the player. 
3. **MOVE** <direction> - Moves the player in an indicated direction. Available directions include: **N**, **S**, **E** or **W**.
4. **PICKUP** - Allows the player to pickup the gold if they are standing on it.
5. **LOOK** - Shows the player a 5x5 grid of the map around the player, with the player at the centre.
6. **QUIT** - Quits the game. If the player is standing on an exit tile and has collected the gold required to win the game then the player has won the game. Otherwise, the player has lost. 

Lastly, there is also a bot on the map, which aims to walk around the map and look for the player. If the bot moves into the same position on the map as the player (or vice versa), then the bot catches the player and the player loses.

On the map (as seen through the LOOK command): <br>
**'P'** - refers to the player <br>
**'B'** - refers to the bot <br>
**'.'** - refers to an empty tile, which are free to walk over by the player <br>
**'G'** - refers to gold, which can be picked up by the player
**'E'** - refers to an exit tile
**'#'** - refers to a wall. The player cannot move through a wall.
