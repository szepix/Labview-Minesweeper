# Labview-Minesweeper

1. Project Description.
1 Project Objective:
To make a functional version of the Minesweeper game in the LabView environment.
2 Project Details:
1. Before starting the game in LabView, the user sets the board size (width
and height of the board) and number of mines. Based on the above data a
board is created. 2.
If the exposed field has a mine the game is over. In this case
If there is a mine around the screened field the game is over. 3,
3. if there is at least one mine around the screened area, in the place of the screened area
we display information about the number of adjacent mines,
4. if there are no mines around the uncovered square (i.e. adjacent squares have no mines)
we expose the appropriate fields (i.e. fields that also do not have mines around them). 5,
5. if all the squares without mines are revealed, or if all the mines are
5. If all the squares without mines are revealed or if all the mines are correctly revealed, the game is over. In this situation the following information should be displayed
information about the success. 2.
2 Divide the project into tasks:
1. creating the game board:
1.1 Be able to set the board size and handle errors related to this.
1.2 Adding mines and spreading them on the board.
1.3 Calculating the number of mines around a field for each field.
1.4 Graphical representation of each possible field.
2 Gameplay:
2.1 Recognize left and right mouse button clicks on the game board.
2.2 Execution of the player's actions by the program and displaying the relevant data (information about the
about the clicked field).
2.3 Exposing appropriate fields around the clicked field.
2.4 Displaying information about success, loss. (In case of a loss it displays
positions of all mines)
3 Implementation:
1. creating the board:
1.1 Ability to set the size of the board and handle errors related to this
This task was accomplished by using "Numeric control" buttons
allowing the user to select corresponding board sizes.
The supported errors are:
1. negative board dimensions
2. no board dimensions
3. number of mines greater than board size
1.2 Adding mines and spreading them on the board.
A one-dimensional "array" is created, which contains a user-specified
number of mines (marked as "-1"), then the dimensions are changed to those given
numeric controls, the values of the resulting array are scattered
by means of the "Shuffle Array" function
1.3Calculation of the number of mines around a given field for each field.
For each field on the board its surroundings are checked (by default - eight fields around it;
for edge fields only existing fields are taken into account). If none of the
If none of the surrounding fields is a mine, the value of the field is 0 by default. If some of the fields are
mines, 1 is added to the value of the field for each mine. When the checked field is
mine its value does not change.
1.4 Graphical representation of each possible field.
For the graphical representation "picture rings" are used
Each field takes values from zero to eleven, with zero being the
a zero is a marked field, a one is a field with the value one, and so on, a flag is marked with the value nine,
a box containing a zero min around it with the value ten, a min with the value 11.
2 Gameplay:
2.1Recognition of left and right mouse button clicks on the game face.
The mouse is initialized and the clicked field is recognized taking into account the position of the
LabView on the monitor and the game shield in the Labview window (obtained using the "Property Node")
and assuming a fixed shield field size. The exact coordinates of the
of the clicked field in the 2d array, taking into account the right and left mouse buttons.
Getting rid of the menu when right-clicking while the
program has been implemented with an "Event Structure" that captures
all menu activations and removes them.
2.2 Execution by the program of the player's actions and displaying the relevant data (information
about the clicked field).
This objective was achieved using the user click data, for the "array"
images assigns the corresponding values from the numeric "array". The
"Case Structure" are used for this, determining the type of click. Implemented by means of a
separate nested VI (Untitled-1SubVI.vi)
When the right mouse button is clicked, a
flag appears to prevent accidental left clicks.
Right-clicking on the flag again changes that field to an
inactive
When the left mouse button is clicked on inactive fields
that contain the number 1-8 change their value to the value corresponding to the number of min
of the surrounding number of min, assigned on the basis of the 'array' from point 1.3, with the exception of
zero, which takes the value 10 in the picture ring. If an empty
field (value 0) - see 2.3
In case of clicking on a mine the game is terminated by checking whether the field
if the field you clicked on contains a mine - see 2.4
2.3 Exposing the corresponding fields around the clicked field.
Implemented using a separate nested VI (Un

Translated with www.DeepL.com/Translator (free version)
