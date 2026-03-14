# so_long

A small 2D game developed as part of the 42 curriculum.
`so_long` is a small tile-based game built around map parsing, player movement and rendering with MiniLibX.

It was a good way to build solid foundations in graphical programming, event handling, map validation and basic gameplay logic in C.

## Features
- 2D tile-based rendering with MiniLibX
- Map parsing from `.ber` files
- Validation of map structure and reachable paths
- Keyboard-based player movement
- Move counter displayed during gameplay

## Project structure
- `inc/so_long.h` — main header file and game structure definition
- `src/so_long.c` — program entry point and main initialization flow
- `src/map_calc.c` — map loading and dimension calculation
- `src/map_check.c` — map content validation
- `src/check_borders.c` — border validation logic
- `src/path_check.c` — path accessibility checks
- `src/create_window.c` — window and rendering setup
- `src/images_placement.c` — tile and sprite placement
- `src/controls.c` — keyboard controls and movement handling
- `images/` — XPM textures used by the game
- `maps/` — valid and invalid test maps
- `utils/get_next_line/` — line-by-line file reading utilities
- `utils/ft_printf/` — local formatted output implementation
- `utils/mlx/` — MiniLibX sources used by the project
- `Makefile` — builds the `so_long` executable

## Mandatory part
The mandatory part focuses on the game logic required to load a valid map, display it and let the player reach the exit.

### Program
- `so_long` — takes a `.ber` map file as argument, validates it, opens a window and runs the game loop

### Core behavior
- reads and validates a map file
- checks that the map is rectangular and enclosed by walls
- verifies the presence of exactly one player start and one exit
- verifies that at least one collectible exists
- checks that all collectibles and the exit are reachable
- displays the game world in a window using MiniLibX
- allows the player to move with the keyboard
- prints the number of moves during play

### Main gameplay elements
- `1` — wall
- `0` — empty floor
- `C` — collectible
- `E` — exit
- `P` — player starting position

<p align="center">
  <img src="assets/so_long-demo.gif" alt="so_long gameplay demo">
</p>

## Build
Build the project:

```bash
make
```

Clean object files:

```bash
make clean
```

Remove object files and executable:

```bash
make fclean
```

Rebuild everything:

```bash
make re
```

## Usage
Run the program with a valid map file:

```bash
./so_long maps/map1.ber
```

## Notes
This project was developed on macOS and the repository is currently configured for the macOS version of MiniLibX.
The provided build setup therefore targets macOS first and no Linux-specific adaptation is included in this repository.

## Learning outcomes
This project was my first real introduction to small-scale graphical programming in C.
It helped build solid foundations in:
- map parsing and validation
- path verification
- event-driven input handling
- texture-based rendering
- window lifecycle management
- gameplay state tracking
