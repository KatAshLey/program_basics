#notes from reading this website
https://fastapi.tiangolo.com

**Install fastAPI**
#in terminal, this includes uvicorn
pip install "fastapi[all]"

---------------------------------------------------------------------
**First Steps**
#in main.py file

from fastapi import FastAPI

app = FastAPI()

@app.get("/")
async def root():
    return {"message": "Hello World"}

#run using in git bash.  uvicorn filename:variableName --reload
uvicorn main:app --reload

#using line INFO:Uvicorn running on http://127.0.0.1:8000 (Press CTRL+C to quit)

#copy http address into web browser to see output
#add to HTTP address /docs eg http://127.0.0.1:8000/docs to enter API documentation
#HTTP address and /redoc to alt auto documentation
#HTTP address and /openapi.json to show JSON output of success

#import Fast Api class
from fastapi import FastAPI

#create fast API instance, main point of interaction to create api
app = FastAPI()

#create a path operation eg https://example.com/items/foo
/items/foo

#operations
POST    #creates data
GET     #read data
PUT     #update data
DELETE  #delete data
OPTIONs
HEAD
PATCH
TRACE

#decorator says function below handles requests to path / using get operation
@app.get("/")

#asnyc/normal functions
async def root()
def root()

#return content, can be list, dict, str, int
return {"message": "Hello World"}

---------------------------------------------------------------------
**Path Parameters**

#parameter given will be passed to function as item_id
@app.get("/items/{item_id}")
async def read_item(item_id):
    return {"item_id": item_id}
 http://127.0.0.1:8000/items/foo returns {"item_id":"foo"}

#declare type, parameters will auto change to type if possible
async def read_item(item_id: int):

#watch out for order of paths defined, will always do the first

#create enum class.  inherit from str, api docs knows values are str to render correctly, fixed values defined
#declare path parameters eg def line
#check docs https:/127.0.0.1:8000/docs#default/get_model_models__model_name__get
#check with if statement. can use model_name.value

from enum import Enum
from fastapi import FastAPI


class ModelName(str, Enum):
    alexnet = "alexnet"
    resnet = "resnet"
    lenet = "lenet"

app = FastAPI()

@app.get("/models/{model_name}")
async def get_model(model_name: ModelName):
    if model_name is ModelName.alexnet:
        return {"model_name": model_name, "message": "Deep Learning FTW!"}

    if model_name.value == "lenet":
        return {"model_name": model_name, "message": "LeCNN all the images"}

    return {"model_name": model_name, "message": "Have some residuals"}

#declare a path parameter containing a path
/files/{file_path:path}

---------------------------------------------------------------------
**Query Parameters**

#query is the key:value pairs after the ? in a URL, separated by & .Are automatically changed by python type.  Are optional and have default values
async def read_item(skip: int = 0, limit: int = 10):
http://127.0.0.1:8000/items/?skip=0&limit=10

#q is optional parameter and None by default.  Fast API knows the difference between path and query parameters
async def read_item(item_id: str, q: str | None = None):

#when using bool as a parameter. any parameter as true, str, int will give a true value