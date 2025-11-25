# Ping Pong (Pong) — Java Swing Game

A simple 2-player Pong-style game implemented in Java using Swing and AWT. This is a clean, lightweight implementation featuring a ball, two paddles, scoring, and physics-based collision detection.

## Project structure

- `Ball.java` — Ball logic (movement, velocity, drawing).
- `Paddle.java` — Paddle logic, keyboard handling (W/S for player 1, Up/Down for player 2) and drawing.
- `GamePanel.java` — Main game loop, collision detection, painting, and game objects orchestration.
- `GameFrame.java` — Window (JFrame) that hosts the `GamePanel`.
- `PingPongGame.java` — Entry point (contains `main`) that starts the game.
- `Score.java` — Score tracking and drawing.

All classes use the default package and are organized as single-file classes for simplicity and easy compilation.

## Requirements

- Java Development Kit (JDK) 8 or newer installed and `javac`/`java` available on your PATH.
- A display that can accommodate the game window size (the game uses GAME_WIDTH = 1500 by default).

## How to compile and run (Windows, cmd.exe)

Open a Command Prompt in the project directory (the directory containing the `.java` files) and run:

```cmd
javac *.java
java PingPongGame
```

Notes:
- Because the code uses the default package, run `java PingPongGame` from the same directory where the `.class` files were produced.
- If you see "Could not find or load main class PingPongGame", ensure you're in the correct directory and that compilation succeeded. You can also run with an explicit classpath:

```cmd
java -cp . PingPongGame
```

## Controls

- Player 1 (left paddle): W = move up, S = move down
- Player 2 (right paddle): Up Arrow = move up, Down Arrow = move down

## Gameplay summary

- The ball starts at the horizontal center and a random vertical position.
- When the ball passes the left or right edge, the opposing player scores one point and the ball / paddles reset.
- The ball speeds up slightly on paddle collisions to increase difficulty.

## Class responsibilities (short)

- `Ball` — Holds position/velocity, moves each tick, draws itself.
- `Paddle` — Handles key events to set vertical velocity, moves and draws itself.
- `GamePanel` — Runs the game loop at ~60 ticks/sec, manages objects, collision detection, and rendering to an off-screen image.
- `GameFrame` — Builds the window and adds the `GamePanel`.
- `PingPongGame` — `main` method; starts the game.
- `Score` — Tracks and renders player scores.

## Troubleshooting

- If the window is too large for your display, edit `GAME_WIDTH` in `GamePanel.java` to a smaller value (for example 800). `GAME_HEIGHT` is computed from `GAME_WIDTH` so the aspect ratio is preserved.
- If keyboard input doesn't work, make sure the `GamePanel` window has focus (click the game window) and that no other application is intercepting keys.

## Possible improvements

- Add a start/menu screen and pause support.
- Add sound effects for paddle hits and scoring.
- Add AI for single-player mode.
- Make window size configurable and add fullscreen scaling.
- Package as an executable JAR for easier distribution.

## License & Attribution

This is a personal project. No specific license is provided, but you're welcome to use and modify the code for learning or personal purposes. If you plan to redistribute or use in commercial projects, consider adding an appropriate open-source license (MIT/Apache/BSD).

## Author / Contact

Created as a personal Java game development project. Feel free to fork, modify, or extend the codebase. To make changes, edit the `.java` files and recompile as shown above.

---

If you'd like, I can:

- produce a small `build.bat` to compile/run on Windows,
- create an executable JAR,
- or add small improvements (pause, start screen, or AI). Tell me which and I'll implement it.
