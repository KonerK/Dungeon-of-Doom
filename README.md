# Dungeon of Doom, Terminal Game

## The Project

Dungeon of Doom is a terminal game created as coursework for a module (CM10227, Principles of Programming) studied by first-year undergraduates studying Computer Science at the University of Bath, which received a mark of 95%. 

The game begins with the player spawned on a rectangular grid, which contains different letters corresponding to different objects that the player can interact with, such as gold (represented by the letter G). Various commands will allow the user to look at and move around the map. The goal of the game is for the player to move around the grid to collect the gold while avoiding bot. After all gold has been collected, the player must find their way to an exit tile in order to leave the dungeon and win the game.

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

## Technologies
<p>
  <img alt="Java" src="https://img.shields.io/badge/Java-9cf?logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyBmaWxsPSIjMUExQTFBIiB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciICB2aWV3Qm94PSIwIDAgNTAgNTAiIHdpZHRoPSI1MHB4IiBoZWlnaHQ9IjUwcHgiPjxwYXRoIGQ9Ik0gMjguMTg3NSAwIEMgMzAuOTM3NSA2LjM2MzI4MSAxOC4zMjgxMjUgMTAuMjkyOTY5IDE3LjE1NjI1IDE1LjU5Mzc1IEMgMTYuMDgyMDMxIDIwLjQ2NDg0NCAyNC42NDg0MzggMjYuMTI1IDI0LjY1NjI1IDI2LjEyNSBDIDIzLjM1NTQ2OSAyNC4xMDkzNzUgMjIuMzk4NDM4IDIyLjQ0OTIxOSAyMS4wOTM3NSAxOS4zMTI1IEMgMTguODg2NzE5IDE0LjAwNzgxMyAzNC41MzUxNTYgOS4yMDcwMzEgMjguMTg3NSAwIFogTSAzNi41NjI1IDguODEyNSBDIDM2LjU2MjUgOC44MTI1IDI1LjUgOS41MjM0MzggMjQuOTM3NSAxNi41OTM3NSBDIDI0LjY4NzUgMTkuNzQyMTg4IDI3Ljg0NzY1NiAyMS4zOTg0MzggMjcuOTM3NSAyMy42ODc1IEMgMjguMDExNzE5IDI1LjU1ODU5NCAyNi4wNjI1IDI3LjEyNSAyNi4wNjI1IDI3LjEyNSBDIDI2LjA2MjUgMjcuMTI1IDI5LjYwOTM3NSAyNi40NDkyMTkgMzAuNzE4NzUgMjMuNTkzNzUgQyAzMS45NDkyMTkgMjAuNDI1NzgxIDI4LjMyMDMxMyAxOC4yODUxNTYgMjguNjg3NSAxNS43NSBDIDI5LjAzOTA2MyAxMy4zMjQyMTkgMzYuNTYyNSA4LjgxMjUgMzYuNTYyNSA4LjgxMjUgWiBNIDE5LjE4NzUgMjUuMTU2MjUgQyAxOS4xODc1IDI1LjE1NjI1IDkuMDYyNSAyNS4wMTE3MTkgOS4wNjI1IDI3Ljg3NSBDIDkuMDYyNSAzMC44NjcxODggMjIuMzE2NDA2IDMxLjA4OTg0NCAzMS43ODEyNSAyOS4yNSBDIDMxLjc4MTI1IDI5LjI1IDM0LjI5Njg3NSAyNy41MTk1MzEgMzQuOTY4NzUgMjYuODc1IEMgMjguNzY1NjI1IDI4LjE0MDYyNSAxNC42MjUgMjguMjgxMjUgMTQuNjI1IDI3LjE4NzUgQyAxNC42MjUgMjYuMTc5Njg4IDE5LjE4NzUgMjUuMTU2MjUgMTkuMTg3NSAyNS4xNTYyNSBaIE0gMzguNjU2MjUgMjUuMTU2MjUgQyAzNy42NjQwNjMgMjUuMjM0Mzc1IDM2LjU5Mzc1IDI1LjYxNzE4OCAzNS42MjUgMjYuMzEyNSBDIDM3LjkwNjI1IDI1LjgyMDMxMyAzOS44NDM3NSAyNy4yMzQzNzUgMzkuODQzNzUgMjguODQzNzUgQyAzOS44NDM3NSAzMi40Njg3NSAzNC41OTM3NSAzNS44NzUgMzQuNTkzNzUgMzUuODc1IEMgMzQuNTkzNzUgMzUuODc1IDQyLjcxODc1IDM0Ljk1MzEyNSA0Mi43MTg3NSAyOSBDIDQyLjcxODc1IDI2LjI5Njg3NSA0MC44Mzk4NDQgMjQuOTg0Mzc1IDM4LjY1NjI1IDI1LjE1NjI1IFogTSAxNi43NSAzMC43MTg3NSBDIDE1LjE5NTMxMyAzMC43MTg3NSAxMi44NzUgMzEuOTM3NSAxMi44NzUgMzMuMDkzNzUgQyAxMi44NzUgMzUuNDE3OTY5IDI0LjU2MjUgMzcuMjA3MDMxIDMzLjIxODc1IDMzLjgxMjUgTCAzMC4yMTg3NSAzMS45Njg3NSBDIDI0LjM1MTU2MyAzMy44NDc2NTYgMTMuNTQ2ODc1IDMzLjIzNDM3NSAxNi43NSAzMC43MTg3NSBaIE0gMTguMTg3NSAzNS45Mzc1IEMgMTYuMDU4NTk0IDM1LjkzNzUgMTQuNjU2MjUgMzcuMjIyNjU2IDE0LjY1NjI1IDM4LjE4NzUgQyAxNC42NTYyNSA0MS4xNzE4NzUgMjcuMzcxMDk0IDQxLjQ3MjY1NiAzMi40MDYyNSAzOC40Mzc1IEwgMjkuMjE4NzUgMzYuNDA2MjUgQyAyNS40NTcwMzEgMzcuOTk2MDk0IDE2LjAxNTYyNSAzOC4yMzgyODEgMTguMTg3NSAzNS45Mzc1IFogTSAxMS4wOTM3NSAzOC42MjUgQyA3LjYyNSAzOC41NTQ2ODggNS4zNzUgNDAuMTEzMjgxIDUuMzc1IDQxLjQwNjI1IEMgNS4zNzUgNDguMjgxMjUgNDAuODc1IDQ3Ljk2NDg0NCA0MC44NzUgNDAuOTM3NSBDIDQwLjg3NSAzOS43Njk1MzEgMzkuNTI3MzQ0IDM5LjIwMzEyNSAzOS4wMzEyNSAzOC45Mzc1IEMgNDEuOTMzNTk0IDQ1LjY1NjI1IDkuOTY4NzUgNDUuMTIxMDk0IDkuOTY4NzUgNDEuMTU2MjUgQyA5Ljk2ODc1IDQwLjI1MzkwNiAxMi4zMjAzMTMgMzkuMzkwNjI1IDE0LjUgMzkuODEyNSBMIDEyLjY1NjI1IDM4Ljc1IEMgMTIuMTEzMjgxIDM4LjY2Nzk2OSAxMS41ODk4NDQgMzguNjM2NzE5IDExLjA5Mzc1IDM4LjYyNSBaIE0gNDQuNjI1IDQzLjI1IEMgMzkuMjI2NTYzIDQ4LjM2NzE4OCAyNS41NDY4NzUgNTAuMjIyNjU2IDExLjc4MTI1IDQ3LjA2MjUgQyAyNS41NDI5NjkgNTIuNjk1MzEzIDQ0LjU1ODU5NCA0OS41MzUxNTYgNDQuNjI1IDQzLjI1IFoiLz48L3N2Zz4%3D"/>
</p>







