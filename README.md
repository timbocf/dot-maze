# Dot Maze

A small Godot maze project made to practice 2D movement, collision and scene composition. Move a dot-like player through a maze using the keyboard.

## Requirements

The project configuration records **Godot 4.7** and the **Mobile** renderer. Use a compatible Godot 4 editor; opening the project in an older editor may require migration or renderer adjustments. Xogot/iOS virtual-controller configuration is also present, but the movement script reads the configured directional actions.

No external packages or build scripts are included.

## Open and play

1. Clone or download the complete repository.
2. In Godot's project manager, choose **Import** and select **project.godot**.
3. Allow the editor to import the image assets.
4. Run the project with **F6/F5 as appropriate**: F5 runs the configured main game, while F6 runs the currently open scene. Use F5 for the complete maze.

The configured main scene is **game.tscn**, and the viewport is 480 × 480.

## Controls

| Action | Keyboard |
| --- | --- |
| Move up | W or Up Arrow |
| Move down | S or Down Arrow |
| Move left | A or Left Arrow |
| Move right | D or Right Arrow |

## Files and scenes

| Path | Purpose |
| --- | --- |
| [project.godot](project.godot) | Main scene, renderer, viewport and input mappings |
| [game.tscn](game.tscn) | Combines the maze map and player |
| [map.tscn](map.tscn) | Maze layout |
| [player.tscn](player.tscn) | Player scene |
| [player.gd](player.gd) | Direction input, velocity and sliding collision movement |
| [brick.tscn](brick.tscn) | Reusable brick scene |
| [level_2.tscn](level_2.tscn) | Placeholder second-level scene |
| Dot.png / dot-player.png | Small player-related image assets |

## Movement implementation

The player extends **CharacterBody2D**. Each physics update reads a directional vector with **Input.get_vector()**, multiplies it by a speed of 100 and calls **move_and_slide()**.

This is continuous directional movement rather than tile-by-tile stepping.

## Current scope

The project is a learning prototype. The second-level scene is currently an empty Node2D; do not expect a complete level progression system. A timer, scoring system and win-state controller are not included in the movement implementation.

## Development checks

Move in every direction, try diagonal movement and test the maze walls for unwanted gaps. If the project cannot start, check the main-scene setting and imported resource errors. If controls do not respond, compare the Input Map action names with those used in **player.gd**.
