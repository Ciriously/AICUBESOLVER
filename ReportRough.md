#  Rubik’s Cube Solver – Python Project
## _Abstraction_

This project concentrates on solving a unsolved Rubik's Cube. The program contains OpenCV libraries and when executed will show a live video from the webcam. When a unsolved Rubik's cube is shown in front of a camera, it will scan the faces of the Rubik's cube. These instructions will be displayed along with the live video in a text format. After a successful scan the program will start to give the instructions on the moves to be made using Augmented arrow on the cube in the live video. When these moves are followed we get the end product of a solved Rubik's Cube within 30 moves.


![PyPI](https://img.shields.io/pypi/v/rubik-cube)
![PyPI - Python Version](https://img.shields.io/pypi/pyversions/rubik-cube)

# Overview

This is a Python 3 implementation of a (3x3) Rubik's Cube solver.

It contains:

- A simple implementation of the cube
- A solver that follows a fixed algorithm
- An unintelligent solution sequence optimizer
- A decent set of test cases

## intrdocs

pytwisty is an extremely fast and efficient Python 3 implementation of a solver for a number of twisty puzzles including the 1x2x2, 1x2x3, and 2x2x2 Rubik’s cube puzzles.

Modern speedcubers solve the Rubik’s cube using memorized sequences of moves, called algorithms, which they deploy to solve the cube section by section. Each algorithm corresponds to a different arrangement of colored stickers on the cube. When a speedcuber spots an arrangement he recognizes, he performs the corresponding algorithm, bringing the cube one step closer to solving.  

However, conventional computerized solvers simply look for an optimal solution from subsets of all possible positions of the pieces on the cube using complex search techniques. The fastest one of these is Kociemba’s algorithm which identifies a subset of 20 billion positions. This algorithm was in fact also used to calculate the solution in the robot that holds the current Guinness World Record for the fastest solve by a robot. For experimentation, we have compared the 2x2x2 solver developed by Herbert Kociemba himself on my machine with two other implementations of Korf’s Algorithm and the 2-way BFS method of solving the cube, both of which are also among the fastest solving methods out there. Upon measuring their average solving times, Kociemba’s solver indeed proved to be the fastest among them.

By contrast, we will develop a solver that uses the “human approach” to solve the puzzle. Specifically, it runs a combination of a slightly altered version of the layer-by-layer (LBL) and the CFOP method. When we ran a 2x2x2 solver on the same set of random scrambles, it solve time on average was about 350 times faster than the solves times of the Herbert Kociemba solver mentioned above. We used the timeit module to measure the solve times of the solver and the mean solves time in seconds turned out to be of the order 10^-5 sec whereas the time taken by the Kociemba’s solver in seconds was of the order 10^-2 sec on my machine on CPython.