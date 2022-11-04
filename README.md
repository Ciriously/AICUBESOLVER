# CubeSolvingScript

Firstly let me tell you that i haven't used cv2.inrange() method for color detection.

To scan sides you can use keys:
U=UP
D=DOWN
R=RIGHT
L=LEFT
F=FRONT
B=BACK

color symbols are mentioned in each center of side in preview window.

as you may see GREEN will be in CENTRE.

Once you get the solution window press any key to continue.

Add All modules
then download kociemba from GitHub and put it with python library file where it is accessible. then restart vscode it will work , you can also find tutorial for placing files in library folder.
 
To Install Kociemba -pip install kociemba --
Install VSCODE installer to update image.png
///// Update Readmeeeeeeee

# 181 line Coloe detection

### Rotate(side)
- A clockwise rotation
- 2 steps
- first initialization of all sides of cue along with the main sides that we have to rotate
- second we need to update the all sides that should be after countercloclkwise rotated
## for example -  
                    - if we are rotating('front') then
                        - 3rd 6th and 9th square of the left sidewill move upt th 7 8 9 
                        - likewise we need to do for all rotation

                        ## NOTE: this is not for solving Cube but for presenting the solution graphically