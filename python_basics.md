filename.py = make a new python file

in terminal
python3 = makes terminal ready to run python in the terminal, easy way to debug, a read-eval-print loop (REPL) mode

quit() = quit REPL mode in terminal

filename.ipynb = new jupyter notebook, choose python environment.  Jupyter will allow to run line by line

variableName = value = gives a value to a variable

print(variableName) = shows the variable, can also use variableName

variableName = input("question") = asks for an input.  Inputs will come up as pop up at command palette level

variableNameBoolean = True/False = sets variable as a boolean, must be capital for True/False

ctrl + Enter = execute particular line
crtl + Alt + Enter = execute block of code

type(variable) = will show what type the variable is

# comment = used to add comments to code or comment out code

variable.upper() = change string variable to uppercase
variable.lower() - change string variable to lowercase

variableName = [] = creates a list

variableName[indexPosition] = to access items in a list.  First item is index/position 0

variableName[-1] = gives the last item on list

variableName[nestedListIndexPosition][indexPositionInNestedList] = how to access an item in a nested list

len(listVariable) = gives the length at the first level, not nested
len(listVariable[nestedListIndexPosition]) = shows length of nested variable

variableName = [indexOne:indexTwo] = to return a section of a string variable.  String given is from indexOne to one less than indexTwo




shift + Enter = new code block

click and drag blue bar on left of each code block, can reorder blocks of code

listVariable.append(newItem) = adds item to end of list

listVariable.insert(indexPosition, newItem) = adds new item in the index position given

listVariable.pop(index) = removes and returns item at index, default is index -1/last item

variableName.sort() = sorts a list by ascending order number or alpha.  Capital letters come before lowercase. Cannot mix int and string
variableName.sort(reverse=True) = sorts decreasing number or alpha
print(sorted(variableName)) = prints a sorted list without altering the original list/variableName.  Can do reverse=True

int("string") = turns string into a number.  Must be a number to start with eg "352"
str("number") = turns number into a string
bool(value) 
print(f"string {value}") = string interpolation, value in curly brackets is forced to string

CONSTANTS = are named as capitals
from typing import Final = imports the final class.  This class will underline constants in red if they are being changed
CONSTANT:Final[type] = value = sets the constant using Final class