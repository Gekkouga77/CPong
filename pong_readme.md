# Pong Game

A classic Pong game implementation in C using SDL2, featuring AI opponent, pause functionality, and resizable window support.

## Features

- **Classic Pong Gameplay**: Player vs AI with realistic ball physics
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
- `digits/0.bmp` through `digits/9.bmp` - Number sprites for score display

### Pause Menu Images
- `resume.bmp` - Resume option image
- `restart.bmp` - Restart option image  
- `exit.bmp` - Exit option image

**Note**: The game will run without pause menu images but display warnings.

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

- **Objective**: First player to reach 2 points wins
- **Scoring**: Ball exits the screen on opponent's side
- **Ball Physics**: Speed increases slightly after each paddle hit
- **Paddle Physics**: Ball angle changes based on where it hits the paddle
- **AI Behavior**: Computer paddle follows ball movement intelligently

## Command Line Options

```bash
# Normal windowed mode
./pong

# Fullscreen mode (if -f flag is properly implemented)
./pong -f
```

## Technical Details

### Architecture
- **Language**: C (C99 standard)
- **Graphics Library**: SDL2
- **Rendering**: Software rendering with hardware-accelerated presentation
- **Frame Rate**: 60 FPS fixed timestep
- **Resolution**: 800x600 default (resizable)

### Code Structure
- **State Management**: Three main states (Menu, Gameplay, Game Over)
- **Pause System**: Overlay system with sub-state management
- **Scaling System**: Dynamic element scaling for window resizing
- **Collision Detection**: AABB (Axis-Aligned Bounding Box) collision system

### Memory Management
- Proper SDL surface and texture cleanup
- No memory leaks in normal operation
- Error handling for failed resource loading

## Development

### Building from Source
1. Clone or download the source code
2. Ensure SDL2 development libraries are installed
3. Compile using the provided commands above
4. Create required asset files or use placeholder images

### Asset Creation Guidelines
- **Format**: 24-bit or 32-bit BMP files
- **Transparency**: Not supported (use solid backgrounds)
- **Digit Images**: Recommended size 32x48 pixels
- **Menu Images**: Recommended size 150x40 pixels for text options

## Troubleshooting

### Common Issues

**"Failed to load [filename].bmp"**
- Ensure all required BMP files are in the correct directory
- Check file permissions and file format (must be BMP)

**Window doesn't resize properly**
- This is expected behavior; game elements scale to maintain aspect ratio
- Use fullscreen mode if needed

**Poor AI performance**
- AI difficulty is fixed in current version
- Modify `move_paddle_ai()` function to adjust difficulty

**Compilation errors**
- Ensure SDL2 development libraries are properly installed
- Check compiler flags and library linking
- Verify C compiler is installed and accessible

### Performance Issues
- Game targets 60 FPS; lower performance may indicate system limitations
- Close other applications if experiencing frame drops
- Consider reducing window size for better performance on older hardware

## License

This project is provided as-is for educational and entertainment purposes. SDL2 is used under its zlib license.

## Contributing

Feel free to fork this project and add improvements such as:
- Sound effects and music
- Better graphics and animations
- Network multiplayer support
- Additional game modes
- Mobile platform support

## Changelog

### Current Version
- Cross-platform SDL2 implementation
- Resizable window support
- Pause menu system
- AI opponent
- Score tracking with bitmap fonts
- Game state management