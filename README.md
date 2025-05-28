
# CPong

CPong is a recreation of the classic pong video game. Implemented in the C
programming language, using SDL2 library to display graphics on the screen.

## Features

- **Classic Pong Gameplay**: Player vs Computer with realistic ball physics
- **Intelligent AI**: Computer opponent that adapts to ball movement
- **Pause System**: In-game pause menu with resume, restart, and exit options
- **Resizable Window**: Dynamic scaling that maintains aspect ratio
- **Score Tracking**: Visual score display using bitmap fonts
- **Game States**: Main menu, gameplay, pause menu, and game over screens
- **Smooth Controls**: Responsive paddle movement with 60 FPS gameplay

## Requirements

### System Requirements
- C compiler (GCC, Clang, or Visual Studio)
- SDL2 development libraries
- Operating System: Windows, Linux, or macOS

### Dependencies
- SDL2 (libSDL2-dev on Ubuntu/Debian)
- Standard C library

## Installation

### Linux (Ubuntu/Debian)
```bash
# Install SDL2 development libraries
sudo apt-get install libsdl2-dev

# Compile the game
gcc -o pong pong3.c -lSDL2 -lSDL2main

# Run the game
./pong
```

### Windows (MinGW)
```bash
# Install SDL2 development libraries for MinGW
# Download SDL2 development libraries from libsdl.org

# Compile (adjust paths as needed)
gcc -o pong.exe pong3.c -lSDL2 -lSDL2main -lmingw32

# Run the game
pong.exe
```

### macOS
```bash
# Install SDL2 using Homebrew
brew install sdl2

# Compile the game
gcc -o pong pong3.c -lSDL2 -lSDL2main

# Run the game
./pong
```

## Required Assets

The game requires the following bitmap (.bmp) files in the same directory as the executable:

### Essential Files
- `title.bmp` - Main menu background image
- `player_win.bmp` - Player victory screen
- `ai_win.bmp` - AI victory screen

### Digit Images (for score display)
Create a `digits/` folder with:
- `digits/0.bmp` through `digits/10.bmp` - Number sprites for score display

### Pause Menu Images
- `resume.bmp` - Resume option image
- `restart.bmp` - Restart option image  
- `exit.bmp` - Exit option image

## Controls

### Main Menu
- `SPACE` - Start game
- `ESC` - Exit application

### Gameplay
- `UP Arrow` - Move player paddle up
- `DOWN Arrow` - Move player paddle down
- `Mouse Click` - Click pause button (top-right corner)
- `ESC` - Exit to desktop

### Pause Menu
- `UP/DOWN Arrows` - Navigate menu options
- `ENTER` or `SPACE` - Select highlighted option
- Options: Resume, Restart, Exit to Main Menu

### Game Over Screen
- `SPACE` - Return to main menu
- `ESC` - Exit application

## Gameplay Rules

- **Objective**: First player to reach 10 points wins
- **Scoring**: Ball exits the screen on opponent's side
- **Ball Physics**: Speed increases slightly after each paddle hit
- **Paddle Physics**: Ball angle changes based on where it hits the paddle
- **AI Behavior**: Computer paddle follows ball movement intelligently
