# CPPND: Capstone Snake Game

This is a project built off of a starter repo for the Capstone project in the [Udacity C++ Nanodegree Program](https://www.udacity.com/course/c-plus-plus-nanodegree--nd213). The code for this repo was inspired by [this](https://codereview.stackexchange.com/questions/212296/snake-game-in-c-with-sdl) excellent StackOverflow post and set of responses.

<img src="snake_game.gif"/>

This project features a classic snake game program, with the added feature of a Score Board class that keeps track of score history.


## Files and Class Structure


1. main.cpp : This is the entrypoint for the program. The main function in this file sets variables such as the window height and width and the number of frames per second at which the game will be played. The main also creates Renderer, Controller, and Game objects, and calls the Game::Run method to start the game loop.

2. snake.h and snake.cpp : These files define the Snake class which contains attributes to keep track of the Snake speed, size, and location. Additionally, there are methods to update the snake state, which are called from the Game::Update method. The Snake head and body are treated separately; the head is stored using float coordinates, and the body is stored using a vector of int cell coordinates. The Snake::UpdateHead method updates the head location using the snake's speed. If the head has passed into a new cell, then the body is updated with the Snake::UpdateBody

3. game.h and game.cpp : These files define the Game class and the game loop: Game::Run. The Game class stores the state of the game, including an instance of a Snake object, the game score, and the location of "food" in the game. Aside from the game loop, the Game class also contains methods to update the state of the game (Game::Update), get the size of the snake, get the total score in the game, and place new food in the game if the food has been eaten by the snake.

4. render.h and render.cpp : These files define the Renderer class which uses the SDL library to render the game to the screen. The Renderer class constructor creates the SDL window and an SDL renderer object that can draw in the window. The Renderer::Render method draws the food and the snake in the window using the SDL renderer.

5. controller.h and controller.cpp : These files define the Controller class. This class handles keyboard input using the SDL libary, and it sets the snake's direction based on the input.

6. scoreboard.h and scoreboard.cpp : These files define the ScoreBoard class which creates and reads a text file where previous score entries are stored. The ScoreBoard class uses the enum ScoreEntry in order to parse previously recorded data and return the top three highest scores upon ending the snake game.


## Rubric Points Addressed




## Dependencies for Running Locally


* cmake >= 3.7
  * All OSes: [click here for installation instructions](https://cmake.org/install/)
* make >= 4.1 (Linux, Mac), 3.81 (Windows)
  * Linux: make is installed by default on most Linux distros
  * Mac: [install Xcode command line tools to get make](https://developer.apple.com/xcode/features/)
  * Windows: [Click here for installation instructions](http://gnuwin32.sourceforge.net/packages/make.htm)
* SDL2 >= 2.0
  * All installation instructions can be found [here](https://wiki.libsdl.org/Installation)
  >Note that for Linux, an `apt` or `apt-get` installation is preferred to building from source. 
* gcc/g++ >= 5.4
  * Linux: gcc / g++ is installed by default on most Linux distros
  * Mac: same deal as make - [install Xcode command line tools](https://developer.apple.com/xcode/features/)
  * Windows: recommend using [MinGW](http://www.mingw.org/)

## Basic Build Instructions

1. Clone this repo.
2. Make a build directory in the top level directory: `mkdir build && cd build`
3. Compile: `cmake .. && make`
4. Run it: `./SnakeGame`.


## CC Attribution-ShareAlike 4.0 International


Shield: [![CC BY-SA 4.0][cc-by-sa-shield]][cc-by-sa]

This work is licensed under a
[Creative Commons Attribution-ShareAlike 4.0 International License][cc-by-sa].

[![CC BY-SA 4.0][cc-by-sa-image]][cc-by-sa]

[cc-by-sa]: http://creativecommons.org/licenses/by-sa/4.0/
[cc-by-sa-image]: https://licensebuttons.net/l/by-sa/4.0/88x31.png
[cc-by-sa-shield]: https://img.shields.io/badge/License-CC%20BY--SA%204.0-lightgrey.svg
