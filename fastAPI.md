#more info read the docs
#import from library
from fastapi import FastAPI

#call initializer, call object
variable_name = FastAPI()

#@ calls decorator function
#calls the root function to app variable
@variable_name.get("/")
async def root():
    return {"message": "Hello World"}

#to run code main.py. in terminal(git bash) variable called app
#can add --port:8001 to force it to use another port
#uvicorn main:app --reload
uvicorn fileName:variable_name --reload

#ctrl + click on 127.0.0.1:800 line to see output in a web browser