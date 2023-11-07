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







07 Nov

transferred

tuples are initialized and can not be changed

setName = {"setItem1", "setItem2", ...} #creates a set

setName.union(setName2) #joins two sets together, removing duplicates

setName.intersection(setName2) #finds the set items that are the same

setName.difference(setName2) #finds items that are different to the set compared to 

sorted(list(setName)) #changes a set into a list, then sorts it

to compare two files, using hash of file and compare set

myDict = {"key1":"value1", "key2":"value2", .....} #creates a new dictionary using key value pairs.  key can be int/str
myDict = {} #alternative way to create a new dictionary
myDict = dict() #alternative way

myDict["keyName"] #returns the value associated with the keyName

myDict["keyName"] = myDictionary["keyName"] modified #to change the value associated with the keyName

myDict["keyName"] = value #gives new value to new keyName




afternoon

integration = know how to configure level 7/application level traffic
              access messaging queues/bursts
              file based sharing, read/write

click drag name of file to the right side of workspace to split screen.  Can be split vertical/horizontal

variableName = open("fileName", "r") #to read a file in the same place as current file.  can use path name eg: C:/folder/folder/filename.etc

variableName.read() #to read the contents of the file

variableName.readline() #to read a line in a file.  Using this a second time immediately after the first, will give the second line. Can go through the lines of your file.  Inserting value in () will give that many characters in the line

for iterationVariable in variable:
    statement using iterationVariable
#creates a for loop, useful for going through a list

if condition:
    statement
elif condition:
    statement
else:
    statement
#creates a if/elif statement.  if condition is true then run statement indented

operations for conditions
== equal to
!= not equal to 
>/< greater/less than
>=/<= greater/less than or equal to
is is the same including type
is not is not the same including type

logical conditions
and #true if BOTH conditions are true
or #true if EITHER condition is true
not #makes it opposite boolean

while condition:
    statement
#creates a while loop. Loops until the conditions are false

#example while loop asking for certain input (dogs/cats)
dogCat = None
while dogCat != "dogs" and dogCat != "cats":
    dogCat = input("Do you like dogs or cats?")

