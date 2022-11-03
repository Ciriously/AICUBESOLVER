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

### Implementation

The main reason behind the extremely high speed and efficiency of the solver is that it is based on a technique developed which I like to call the “Minimal Thinking” technique. This, in simplest terms, is a technique that minimizes the thought process behind solving any problem by recognizing the type of problem and using a predetermined result to jump straight to the solution. At each step of solving the puzzle, the solver recognizes the current arrangement and orientation of the individual pieces of the puzzle, and rearranges and reorients the pieces into the final state that the corresponding algorithm would have resulted in, had it been manually executed. This is just like how speedcubers, at each level of solving the Rubik’s cube, look at the arrangement of the cube and execute the corresponding algorithm, all without thinking. 


### Application

The Rubik’s cube solver is just one of the innumerable potential applications of the Minimal Thinking technique, which can be used to ease the computational part of a problem for a computer program by training it to use results that have already been established previously by human or artificial intelligence, and enabling it to jump directly to the solution without actually solving the entire problem. The result is a boost in the performance of the program both in terms of memory and speed.

However, an important point to note is that although Kociemba’s Algorithm is significantly slower than my solver, the fact that it almost always produces a solution that is much closer to the optimum solution than that produced by mine cannot be ignored. While the Fridrich method (the human method my solver is based on) produces solutions with a mean length of 50–60 moves, Kociemba’s algorithm produces one with a maximum of 29 moves and a minimum of 19. Therefore, the two solvers actually represent two different approaches to solving the same problem: whether we require a solution that is nearly the best and are willing to invest enough time and resources towards obtaining that solution, or are happy with a solution that may not be the shortest but is generated fairly quickly and at the cost of fewest possible resources, the choice is ours. With modern mechanical motors in Rubik's Cube solving robots that can execute each move in as less as 10 milliseconds, executing a handful of extra moves is an almost negligible task. In most real-life problems, an optimal solution may not always prove to be the best solution, especially when it is generated at the cost of an extremely slow and excessively memory-consuming program. Moreover, bringing down this move time of the motors to 5 milliseconds is a more achievable task in near future than developing faster and better search algorithms and reprogramming the other existing solvers to execute them.

Another significant takeaway from this particular solver is the fact that such a solver for a puzzle of a particular order can be built by adding on to the solvers of lower orders of the same category of puzzles, without having to start from scratch. This is precisely how I had built my solver for the 1x2x3 Rubik’s puzzle from my 1x2x2 puzzle solver by adding a few extra lines of code that correctly orient the middle layer pieces which are absent from a 1x2x2 puzzle.