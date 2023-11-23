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

@app.get("/items/{item_id}")
def read_item(item_id: int, item: Item, q: Union[str, None] = None): #Default value for q is None
    return {"item_id": item_id, "q": q, "item": item}

#to run code main.py. in terminal(git bash) variable called app
#can add --port:8001 to force it to use another port
#uvicorn main:app --reload
uvicorn fileName:variable_name --reload

#ctrl + click on 127.0.0.1:800 line to see output in a web browser
ctrl + c to quit

check restart homework week03 api_pt1 for more examples
put working examples into body of postman
#to check in api_pt1 works in postman
change to PUT, enter HTTP address http://127.0.0.1:8000/items/riuage56
enter inventory item in body tab, send, should give null result
#change to GET, should return item