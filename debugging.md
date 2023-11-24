#python extension includes debugging.
#debugging stops at the trouble spot
#recommended to use a different port to debug, so it doesn't end up confused


make sure terminal is in the right folder
close all terminals to avoid conflict
run and debug button
launch.json file, select language and file, this can be found in debug tab, gear icon
add "cwd": "${workspaceRoot/ file path}"
hit play button at top left of screen

add in args #this forces it to use a different port instead of std 8000
"--port"
"5000"

#make breakpoint to stop it running
debug console at bottom, check out local and global tabs