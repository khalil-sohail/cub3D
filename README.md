# cub3D

`cub3D` is a 42 School ray-casting project that recreates the feeling of moving through a 3D maze from a classic 2D map. Using MiniLibX and a first-person rendering pipeline, the program transforms a parsed map into a dynamic, textured environment with real-time movement, collision handling, and interactive gameplay elements.

## Features

### Core Features

- Ray-casting based 3D rendering.
- Textured walls for the different map directions.
- Dynamic camera projection from a 2D grid map.
- Player movement with basic collision detection.
- Map parsing and validation from a `.cub` configuration file.
- Error handling for malformed maps, invalid identifiers, and missing assets.
- Real-time rendering with MiniLibX on Linux.

### Bonus Features

- Minimap display for player orientation and map awareness.
- Mouse-controlled camera view.
- Opening and closing doors during gameplay.
- Animated sprites for a more dynamic scene.

## Project Structure

The root directory is organized as follows:

```text
cub3D/
├── error/
│   ├── *.c
├── file.cub
├── Get-Next-Line/
│   ├── *.c
│   └── *.h
├── graphic_management/
│   └── *.c
├── include/
│   └── *.h
├── Libft/
│   ├── *.h
│   └── *.c
├── main/
│   └── main.c
├── Makefile
├── map_checker/
│   ├── *.c
├── minilibx-linux/
│   ├── mlx_*.c
│   ├── mlx.h
│   └── README.md
└── Textures/
    └── xpm/
        └── ...
```

### Directory and File Overview

- `error/`: Centralized error reporting and cleanup helpers.
- `file.cub`: Example or working map configuration used to launch the game.
- `Get-Next-Line/`: Line-by-line file reading utilities used while parsing the map file.
- `graphic_management/`: Rendering, ray-casting, movement, minimap, and gameplay interaction logic.
- `include/`: Shared project headers and structure definitions.
- `Libft/`: Custom 42 support library used across parsing, rendering, and utility code.
- `main/`: Program entry point and application startup logic.
- `Makefile`: Build rules for compiling the entire project into the `cub3D` executable.
- `map_checker/`: Map validation, borders, reachability checks, and parsing rules.
- `minilibx-linux/`: MiniLibX graphics library source used to create the window and draw the scene.
- `Textures/`: Texture assets and XPM resources used for walls, sprites, and environment elements.

## Prerequisites

Before compiling, make sure the following tools and libraries are available on your Linux system:

- `gcc` or a compatible C compiler.
- `make`.
- X11 development libraries required by MiniLibX.
- Xext development libraries required by MiniLibX.
- Standard Linux build tools and headers.

On Debian/Ubuntu-based systems, a typical setup is:

```bash
sudo apt update
sudo apt install gcc make xorg libx11-dev libxext-dev
```

## Installation & Compilation

1. Clone the repository and move into the project directory.
2. Ensure the MiniLibX dependencies are installed on your system.
3. Compile the project with:

```bash
make
```

The default `make` command builds the complete project and produces a single executable named `cub3D`. In this repository, the mandatory and bonus requirements are compiled together into that same executable.

Useful clean targets:

```bash
make clean
make fclean
make re
```

## Usage

Run the program by passing a valid `.cub` map file:

```bash
./cub3D file.cub
```

You can replace `file.cub` with any other valid map configuration that follows the project format.

## Controls

- `W`: Move forward.
- `S`: Move backward.
- `A`: Strafe left.
- `D`: Strafe right.
- `Left Arrow`: Rotate camera to the left.
- `Right Arrow`: Rotate camera to the right.
- Mouse movement: Control the camera view.
- `Spacebar`: Interact with doors.
- `ESC`: Quit the application.
- Window close button: Exit the game.

## Notes

- The project relies on a valid map layout, proper texture references, and fully enclosed walls.
- Map parsing and validation are handled before the rendering loop starts, so invalid input should be reported early.
- Textures and bonus gameplay elements are loaded and rendered through the same executable built by the default `make` target.