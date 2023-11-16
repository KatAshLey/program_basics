++++++++++++++++++++++++++++++++++++++++++


06 Nov

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



++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++



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



+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++



08 Nov

break #stops while loops

match variable:            #match case used to filter out variable values,
    case variableValue:    #more complicated pattern matching than if
        statement          #more readable than if statements
    case variableValue:
        statement
    case _:                #default case, like else in if statements
        statement          #use _ or other



enum used to only use acceptable answers amd make it readable
from enum import Enum  #to import enum into file

class className(Enum):    #define allowable options, use capitals
    OPTION = 1
    OPTION = 2

variable = className.OPTION

match variable:
    case className.OPTION
        statement
    case className.OPTION
        statement



range(value) #value is a number, iterable

#for alternative spacing, list comprehension
newList = [statement for i in oldList]  #can use eg i.upper() as statement

#enumerate shows the index of the list items
myNums = [0,2,4,6]                      
for index, item in enumerate(myNums):
    print(f"{index}.item")


myDict = {key1 : value1, key2 : value2}   #prints dict key and value, iterate dict
for key, value in myDict.items():
    print(f"{key}, {value}")


when using lists, items are first in, first out.
use a queue, append() lines one after another to add
when using pop(index) make sure to put in a index




afternoon

#defining a function. Return will end a function and hand back a value.  if there is no return, function will run till the end
def functionName(inputArgument):
    return statement


#scope, variables defined/modified in a function, only exist/change within that function



+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++



09 Nov

Error messages
red shows the type of error, white explains the problem

assert booleanTest, "stringReturnedIfFalse"
eg assert 1 == 0, "expect 1 and 0 to be different"
AssertionError # when you give the assertion a false outcome, there will be an error, only stops at first assertion problem.  String is returned when false, explain what you are trying to test.  ALternative to using print() to test.  Can use this to test many input/output, using test case tables


#will print out the kind of error that's happening 
try:
    print(u)
except Exception as e:
    print(e)
print("program is still operating normally")

output: name 'u' is not defined
        program is still operating normally


#ZeroDivisionError, code stops at this level
try:
    print(1/0)
except ZeroDivisionError as zde:
    print("I caught zero division error")
except Exception as e:
    print(e)
print("program is still operating normally")


#try, except, exception error, else(if it all runs)
try:
    statement
except particularError as errorVariableName:
    statement/print
except Exception as errorVariableName:
    statement/print
else:
    statement if everything runs
    return variableName



+++++++++++++++++++++++++++++++++++++++++++++++++



10 Nov

OOP = object orientated programming.  If you like this go into dev ops
Functional programming = only use functions to program, can be painful to write fully functional programs. benefit: less prone to error, less side effects


#defining a class, must use capital for name, must have something in the statement(if not use pass)
class ClassName:
    pass

#initialize a class
class ClassName:
    def __init__(self, attribute1, attribute2):
        self.attribute1 = attribute1
        self.attribute2 = attribute2

#create variable using class
variableName = className(attribute1, attribute 2)

#to call a class
className.attribute

#can create functions in classes to do actions
#to call
variableClassName.function(value)

#calls the attributes of the className as a dictionary
variableNameOfClass.__dict__


#child class initialized
#can use ParentClassName or super() -automatically inherit methods and attributes from parent class, but remove self from attribute list eg super().__init__(attri1, attri2)r

class ChildClassName(ParentClassName):
    def __init__ (self, attribute1, attribute2, attribute3)
        ParentClassName.__init__(self,attribute1, attribute2)    #match parentclass
        self.attribute3 = attribute3



++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++



13 Nov

 #create file
 folder > library > libraryName.py
 #create file - this folder used to import 
 __init__.py in library folder
 #create file for main code
 main.py in folder

# to confirm running main function
#test It Allows You to Execute Code When the File Runs as a Script, but Not When It’s Imported as a Module
if __name__ == "__main__":
    main()

#python conventions 
variable_name
ClassName
method_name()

#in __init__.py folder to use library, exports library methods
from .libraryName import method/class

#in child class file, to call parent class from child class.  parent class file is named the same as parent class
from .ParentClassLibraryName import ParentClass

#call two classes from classes folder
#classes folder Ice.py
from classes import Ice, Electric

#run code in terminal as python3 main.py



#data classes
#for data transfer not methods.  information about a class

#if many dataclasses you can nest them

#defining data class
@dataclass
class InventoryItem:
    name: str
    quantity: int
    serial_num: str

#def data class
    my_item1 = InventoryItem(name = "printer", 
                             quantity = 5, 
                             serial_num = "HDOUHKJN")


#** copies content of item to 2nd item
my_item2 = InventoryItem(**my_serialized_object1)

#can refer to dataclass within dataclass, be aware of the order the classes are defined


#pip install pydantic

#within class def means it only applies to class
@field_validator("country")
@classmethod 
def check_valid_country(cls, country: str):
    assert country == "Ethiopia", "country name must be Ethiopia"


#validationError.  must also add
from pydantic import ValidationError
try:
    statements including invalid to trigger validation error
except ValidationError as ve:
    print(error message)
else:
statement


#regular expressions/RegEx.  used to check if a string contains specified search pattern.  returns a match object if found or None if no matches.  to return a boolean return variable != None
import re
variable_name = re.function(match, string)

#RegEx Functions
findall     #returns list containing all matches
search      #returns match object if in string
split       #returns list where string has been split at each match
sub         #replaces on or many matches in a string

#check for special sequences to use for ReEx here
#https://www.w3schools.com/python/python_regex.asp
#https://www.dataquest.io/blog/regex-cheatsheet/

#when defining a function enter the input type and output type eg str -> bool