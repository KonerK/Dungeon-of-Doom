# Dungeon of Doom, Terminal Game

## The Project

Dungeon of Doom is a terminal game created as coursework for a module (CM10227, Principles of Programming) studied by first-year undergraduates studying Computer Science at the University of Bath. 

The game begins with the player spawned on a rectangular grid, which contains different letters corresponding to different objects that the player can interact with, including gold (represented by the letter G). Various commands will allow the user to look at and move around the map. The goal of the game is for the player to move around the grid to collect the gold while avoiding bot. After all gold has been collected, the player must find their way to an exit tile in order to leave the dungeon and win the game.

![DoDClip](https://github.com/KonerK/Dungeons-of-Doom/assets/66024237/9682a201-16ac-4f62-bb20-fcd1c5e53984)

## Downloading the Game
1) Download a ZIP of the Project (check [here](https://docs.github.com/en/repositories/working-with-files/using-files/downloading-source-code-archives) if unsure how to do this)
2) Navigate to the src directory within the command line, and compile the java files using the javac command, e.g.
   ```sh
   javac *.java
   ```
3) Finally, within the src folder you can start the game via
    ```sh
   java GameLogic
   ```

## How to Play
Upon successfully running the game you will be told to enter a map name. Enter the name of any of the following maps: 'large_example_map', 'medium_example_map', 'small_example_map'. If the name is not recognised, you will be placed in a default map entitled 'Very Small Labyrinth of Doom.' After a map is chosen a message stating which dungeon you are in appears and the game begins. 

On the map (as seen through the LOOK command) you will see the following items: <br>
**'P'** - refers to the player. <br>
**'B'** - refers to the bot. <br>
**'.'** - refers to an empty tile, which are ordinary empty tiles that the player is free to walk over. <br>
**'G'** - refers to gold, which can be picked up by the player.
**'E'** - refers to an exit tile. Reach this tile to exit the game when you have collected all of the gold.
**'#'** - refers to a wall. The player cannot move through a wall.

Be careful, the bot will continuously be attempting to find you on the map. If it reaches the tile you are currently on, you will lose the game and a losing message will appear. Finally, you are able to move around and inspect the map by entering one of the following commands: 

1. **HELLO**: Displays amount of gold needed for the player to collect to win the game.
2. **GOLD**: Displays the current gold owned by the player. 
3. **MOVE** <direction> - Moves the player in an indicated direction. Available directions include: **N**, **S**, **E** or **W**.
4. **PICKUP** - Allows the player to pickup the gold if they are standing on it.
5. **LOOK** - Shows the player a 5x5 grid of the map around the player, with the player at the centre.
6. **QUIT** - Quits the game. If the player is standing on an exit tile and has collected the gold required to win the game then the player has won the game. Otherwise, the player has lost. 

## Using & Creating A Map
Upon starting the game, the user is promoted to enter a map. The map text files should be placed in the root project folder (one level above the src folder).  Map file names should be of the form 'mapname.txt',  although to use the map you only need to write 'mapname' into the terminal when prompted for the map. 

If creating your own map, ensure the map is within a .txt file with the following format: <br>
**First Line of .txt File**: name 'mapname' <br>
**Second Line of .txt File**: win 'number of gold needed to win" <br>
**Remaining Lines of .txt File**: A rectangular nxm grid encompassed by # tiles. <br>

The following examples should give a good idea of the format. Enjoy!
<br>
<br>
![Maps](https://github.com/user-attachments/assets/9fea43f7-fb81-4ac7-8cd8-a2beacb50a96)








