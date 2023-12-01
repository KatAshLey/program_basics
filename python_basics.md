# =====================================================================


# 06 Nov

filename.py = make a new python file

#  in terminal
# makes terminal ready to run python in the terminal, easy way to debug, a read-eval-print loop (REPL) mode
python3

# quit REPL mode in terminal
quit()

# new jupyter notebook, choose python environment.  Jupyter will allow to run line by line
filename.ipynb

# gives a value to a variable
variable_name = value

# shows the variable, can also use variableName
print(variable_name)

# asks for an input.  Inputs will come up as pop up at command palette level
variable_name = input("question")

# sets variable as a boolean, must be capital for True/False
variable_name_boolean = True/False

# execute particular line
ctrl + Enter

# execute block of code
crtl + Alt + Enter 

# will show what type the variable is
type(variable)

# used to add comments to code or comment out code
# comment

# change string variable to uppercase
variable.upper() 

# change string variable to lowercase
variable.lower()

# creates a list
variable_name = [] 

# access items in a list.  Use integer/number, First item is index/position 0
variable_name[indexPosition]

# gives the last item on list
variable_name[-1]

# access an item in a nested list
variable_name[nestedListIndexPosition][indexPositionInNestedList]

# gives the length of list at the first level, not nested
len(list_variable)

# shows length of nested variable
len(list_variable[nestedListIndexPosition])

# return a section of a string variable.  String given is from indexOne to one less than indexTwo
variable_name = [indexOne:indexTwo] 

# new code block
shift + Enter 

# can reorder blocks of code
click and drag blue bar on left of each code block

# adds item to end of list
list_variable.append(newItem) 

# adds new item in the index position given
list_variable.insert(indexPosition, newItem) 

# removes and returns item at index, default is index -1/last item
list_variable.pop(index)

# sorts a list by ascending order number or alpha.  Capital letters come before lowercase. Cannot mix int and string
variable_name.sort() 

# sorts decreasing number or alpha
variable_name.sort(reverse=True)

# prints a sorted list without altering the original list/variableName.  Can do reverse=True
print(sorted(variable_name)) 

# turns string into a number.  Must be a number to start with eg "352"
int("string") 

# turns number into a string
str("number")
bool(value) 

# string interpolation, value in curly brackets is forced to string
print(f"string {value}") 

# are named as capitals
CONSTANTS

# imports the final class.  This class will underline constants in red if they are being changed
from typing import Final 

# sets the constant using Final class
CONSTANT:Final[type] = value



# ======================================================================



# 07 Nov

# tuples are initialized and can not be changed

# creates a set
set_name = {"set_item1", "set_item2", ...} 

# joins two sets together, removing duplicates
set_name.union(set_name2) 

# finds the set items that are the same
set_name.intersection(set_name2) 

# finds items that are different to the set compared to 
set_name.difference(set_name2)

# changes a set into a list, then sorts it
sorted(list(set_name)) 

#  compare two files, using hash of file and compare set

# creates a new dictionary using key value pairs.  key can be int/str
my_dict = {"key1":"value1", "key2":"value2", .....} 

# alternative way to create a new dictionary
my_dict = {} 

# alternative way
my_dict = dict() 

# returns the value associated with the keyName
my_dict["keyName"] 

# to change the value associated with the keyName
my_dict["keyName"] = myDictionary["keyName"] modified 

# gives new value to new keyName
my_dict["keyName"] = value 


# know how to configure level 7/application level traffic access messaging queues/bursts file based sharing, read/write
integration 

# split screen.  Can be split vertical/horizontal
click drag name of file to the right side of workspace 

# read a file in the same place as current file.  can use path name eg: C:/folder/folder/filename.etc
variable_name = open("file_name", "r") 

# read the contents of the file
variable_name.read()

# read a line in a file.  Using this a second time immediately after the first, will give the second line. Can go through the lines of your file.  Inserting value in () will give that many characters in the line
variable_name.readline() 

# creates a for loop, useful for going through a list
for iteration_variable in variable:
    statement using iteration_variable

# creates a if/elif statement.  if condition is true then run statement indented
if condition:
    statement
elif condition:
    statement
else:
    statement

# operations for conditions
# equal to
== 
# not equal to 
!= 
# greater/less than
>/< 
# greater/less than or equal to
>=/<= 
# is the same including type
is 
# is not the same including type
is not 

# logical conditions
# true if BOTH conditions are true
and 
# true if EITHER condition is true
or 
# makes it opposite, boolean
not 

# creates a while loop. Loops until the conditions are false
while condition:
    statement

# example while loop asking for certain input (dogs/cats)
dogCat = None
while dogCat != "dogs" and dogCat != "cats":
    dogCat = input("Do you like dogs or cats?")



# ====================================================================



# 08 Nov

# stops while loops
break 

# match case used to filter out variable values, more complicated pattern matching than if, more readable than if statements
match variable:            
    case variable_value:    
        statement          
    case variable_value:
        statement
    case _:                # default case, like else in if statements
        statement          # use _ or other


# enum used to only use acceptable answers amd make it readable
from enum import Enum  #to import enum into file

# define allowable options, use capitals
class class_name(Enum):    
    OPTION = 1
    OPTION = 2

variable = class_name.OPTION

match variable:
    case class_name.OPTION
        statement
    case class_name.OPTION
        statement



# value is a number, iterable
range(value) 

# for alternative spacing, list comprehension, can use eg i.upper() as statement
new_list = [statement for i in old_list]  

# enumerate shows the index of the list items
my_nums = [0,2,4,6]                      
for index, item in enumerate(my_nums):
    print(f"{index}.item")


# prints dict key and value, iterate dict
my_dict = {key1 : value1, key2 : value2}   
for key, value in my_dict.items():
    print(f"{key}, {value}")


# when using lists, items are first in, first out.
# use a queue, append() lines one after another to add
# when using pop(index) make sure to put in a index


# defining a function. Return will end a function and hand back a value.  if there is no return, function will run till the end
def function_name(input_argument):
    return statement


# scope, variables defined/modified in a function, only exist/change within that function



# ===========================================================



# 09 Nov

# Error messages
# red shows the type of error, white explains the problem

# when you give the assertion a false outcome, there will be an error, only stops at first assertion problem.  String is returned when false, explain what you are trying to test.  ALternative to using print() to test.  Can use this to test many input/output, using test case tables
assert boolean_test, "string_returned_if_false"
eg assert 1 == 0, "expect 1 and 0 to be different"
AssertionError 


# will print out the kind of error that's happening 
try:
    print(u)
except Exception as e:
    print(e)
print("program is still operating normally")

output: name 'u' is not defined
        program is still operating normally


# ZeroDivisionError, code stops at this level
try:
    print(1/0)
except ZeroDivisionError as zde:
    print("I caught zero division error")
except Exception as e:
    print(e)
print("program is still operating normally")


# try, except, exception error, else(if it all runs)
try:
    statement
except particular_error as error_variable_name:
    statement/print
except Exception as error_variable_name:
    statement/print
else:
    statement if everything runs
    return variable_name



# =============================================================



# 10 Nov

# OOP = object orientated programming.  If you like this go into dev ops
# Functional programming = only use functions to program, can be painful to write fully functional programs. benefit: less prone to error, less side effects


# defining a class, must use capital for name, must have something in the statement(if not use pass)
class ClassName:
    pass

# initialize a class
class ClassName:
    def __init__(self, attribute1, attribute2):
        self.attribute1 = attribute1
        self.attribute2 = attribute2

# create variable using class
variable_name = ClassName(attribute1, attribute 2)

# to call a class
ClassName.attribute

# can create functions in classes to do actions
# to call
VariableClassName.function(value)

# calls the attributes of the className as a dictionary
VariableNameOfClass.__dict__


# child class initialized
# can use ParentClassName or super() -automatically inherit methods and attributes from parent class, but remove self from attribute list eg super().__init__(attri1, attri2)r

class ChildClassName(ParentClassName):
    def __init__ (self, attribute1, attribute2, attribute3)
        ParentClassName.__init__(self,attribute1, attribute2)    #match parentclass
        self.attribute3 = attribute3



# ===================================================================



# 13 Nov

# create file
folder > library > libraryName.py

# create file - this folder used to import 
__init__.py in library folder

# create file for main code
main.py in folder

# to confirm running main function
# test It Allows You to Execute Code When the File Runs as a Script, but Not When It’s Imported as a Module
if __name__ == "__main__":
    main()

# python conventions 
variable_name
ClassName
method_name()

# in __init__.py folder to use library, exports library methods
from .libraryName import method/class

# in child class file, to call parent class from child class.  parent class file is named the same as parent class
from .ParentClassLibraryName import ParentClass

# call two classes from classes folder
# classes folder Ice.py
from classes import Ice, Electric

# run code in terminal 
python3 main.py



# data classes
# for data transfer not methods.  information about a class

# if many dataclasses you can nest them

# defining data class
@dataclass
class InventoryItem:
    name: str
    quantity: int
    serial_num: str

#def data class
    my_item1 = InventoryItem(name = "printer", 
                             quantity = 5, 
                             serial_num = "HDOUHKJN")


# copies content of item to 2nd item
my_item2 = InventoryItem(**my_serialized_object1)

# can refer to dataclass within dataclass, be aware of the order the classes are defined


# install pydantics, in terminal
pip install pydantic

# within class def means it only applies to class
@field_validator("country")
@classmethod 
def check_valid_country(cls, country: str):
    assert country == "Ethiopia", "country name must be Ethiopia"


# validationError.  must also add
from pydantic import ValidationError
try:
    statements including invalid to trigger validation error
except ValidationError as ve:
    print(error message)
else:
statement


# regular expressions/RegEx.  used to check if a string contains specified search pattern.  returns a match object if found or None if no matches.  to return a boolean return variable != None
import re
variable_name = re.function(match, string)

# RegEx Functions
findall     #returns list containing all matches
search      #returns match object if in string
split       #returns list where string has been split at each match
sub         #replaces on or many matches in a string

#check for special sequences to use for ReEx here
#https://www.w3schools.com/python/python_regex.asp
#https://www.dataquest.io/blog/regex-cheatsheet/

# when defining a function enter the input type and output type eg str -> bool