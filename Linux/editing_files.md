# up to lesson 3
# open vimtutor, if this doesnt work use sudo yum install vim
vimtutor

# to move cursor
^ k
> l
v j
< h

# quit vimtutor and not save
:q!

# delete character under the cursor
x

# to exit modes 
esc

# insert text before the cursor
i

# append text
A

# save a file and exit, to save only :w
:wq

# in the shell prompt, vim starts the Vim editor, filename is the file to change
vim filename

# delete a word, move cursor to first letter
dw

# delete to end of the line from cursor
d$

# operators and motion
# format for delete is d motion
# some motions are:
# w - until the start of the next word, excluding it's first character
# e - to the end of the current word, including the last character
# $ - to the end of the line, including the last character

# using a count for a motion
# typing a number before a motion, repeats it that many times

# the start of a line 
0

# typing a number with an operator repeats it that many times eg: d number motion = d3w deletes next 3 words

# delete while line
dd

# undo last command
u

# to fix a whole line
U

# redo
ctrl + r

# to put previously deleted text after the cursor
p

# replace the character at the cursor with x, x can be any character
rx

# to change until the end of a word, this can be used the same way as delete, just use c instead
ce -then type replacement word
cc - for whole line

# using nano to create a file
nano filename

# to save changes, then save filename
ctrl + o

# exit nano mode
ctrl + x

upto lesson 3 of vimtutor