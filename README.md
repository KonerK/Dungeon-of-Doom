# Dungeon of Doom, CW2 (CM10227) 

This project was created as the second coursework for CM10227, Dungeons of Doom. The terminal-based game begins with the player spawned on a rectangualr grid (the map). This map contains gold tiles, exit tiles, empty tiles, and walls. The goal of the game is for the player to move around the grid to collect the gold, then find their way to an exit tile in order to leave the dungeon and win the game. 

## User Actions & Notes

#### 1. Configuration Instructions

The game is played via the terminal/command line. Navigate in the command line to where the source code is contained (e.g. in the src folder), and compile the java files using 'javac *.java'. Then, in order to play the game, enter 'java GameLogic' and the game will begin.

#### 2. Using a Different Map

Upon starting the game, the user is promoted to enter a map. The map text files should be placed in the src folder with the code files.  Map file names should be of the form 'name.txt' and to find the map you only need to write 'name' into the console when asked for the map name.

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


## Developer/Marker Notes

The code has been written in Java, making use of IntelliJ. The project contains 5 classes:

### 1. GameLogic 
This class contains the main method from which the game is run. Within GameLogic, we create a Map, a BotPlayer and a HumanPlayer. We also keep track of whether the game is running or not, and whose turn it is (the bot or the player). In GameLogic, we add the players to the map, through addPlayerToMap(), and perform the actions each player specifies by calling methods such as hello(), gold(), move(). 

### 2. Map
The map class holds the current state of the map. This includes the map stored as a 2D char array, the name of the map, the gold required to be collected on the map to win the game, and the amount of rows/columns of the map, which are used in representing the map as a 2D array. Within this class, we deal with reading in the map from a file and, if this is not possible, providing a default map. We also use this class to update the position of the player/bot on the map as well as the position of items on the map.

### 3. Player
This is an abstract class, and is inherited by both BotPlayer and HumanPlayer, and contains the essential fields and behaviours of player classes. This class contains the necessary fields a player needs: the commands available to the player, the command they want to execute, their row/column position on the map (in order to move the player when they execute a move command) and the item they are standing on. Suitable accessor and mutator methods are provided for these fields. Two abstract methods are created in Player: generateCommand() and getNextAction(). These methods are abstract as how each player generates a command and how each command is processed is different depending on the player type.

### 4. HumanPlayer
HumanPlayer represents the class for the user. Two more fields are created on top of the fields provided by Player: the amount of gold the player owns and a BufferedReader Object. Within generateCommand() we gather the command the user wants to execute through asking for input in the console. This input is then processed in getNextAction(), where we look to see if the command entered by the user corresponds to any of the commands available to them. If it does, we can return the command the user wants to execute to GameLogic.

### 5. BotPlayer
BotPlayer - BotPlayer represents the computer controlled player. Within generateCommand(), a command is generated based on how many moves the bot has made, and whether the bot has seen the player through the look command. Every two directions the bot moves in, generateCommand returns the LOOK command. The boy player then stores information about the map that it can gather through this command - such as the position of the player relative to the bot. If the player can not be seen, the next two moves of the bot will be to move in a random direction, as such generateCommand() returns either MOVE N, MOVE S, MOVE E or MOVE W. If the bot sees the player, it decides which direction to move in depending on which direction will bring it closest to the player (this is decided through a separate method called getDirectionToMoveIn, which is called in generateCommand() on moves when the bot is not using the LOOK command.) In getNextAction(), we simply return the command specified by the bot from generateCommand() to GameLogic. 
