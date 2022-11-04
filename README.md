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
###  WORKING
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

 ### revrotate(side):
It is identical to rotate(side)
Note: It looks same but there is major difference in updating each side
Example:
■ If we do revrotate('Front')
• Then, 7th, 8th 9th square of front will move to left but in reverse
order
• Left[3]= Up[9]
• Left [6]= Up[8]
• Left[9]= Up[7]
• Likewise, we need to do for each rotation. 

### solve(state)
o This function is to apply kocembia algorithm to fetch the solved string.
o Here we will have input as 'Green' or 'other names'
o We need to convert them into 'F', 'U','R' likewise.
o Then with cube.solve(), we will retrieve the output
 ### color_detect(h,s,v):

o This function is most important.
o Here we will have three inputs (H,S,V)
o Note: There are number of methods available to detect the colours though not
working efficiently. So I tried by my own, there are certain possibilities that you
may cannot detect the colour of your cube because outer brightness and shade
of cube matter the most.

### draw_stickers (frame,stickers,name):
 This function will create rectangles on given frame to detect square.
·
### draw_preview_stickers(frame,stickers): 
 This will do the same as draw_stickers but on other frame where we will show our output.


### texton_preview_stickers(frame,stickers):
 In this function, we will put the latter of each side in the middle square of the side.

### fill_stickers(frame,stickers,sides):
o This function will be called each time we scan the side.
### process(operation):
o here, we will have dict called replace.
o In which, we have added each side as key and in value, we have function name
and passing arguments.
o We will use these when we will have the solved string then we can show
graphically what is happening in solution.
Main function:
o Create frames: frame to detect and preview frame
o Draw stickers
o Fill stickers, once you detect the colour.