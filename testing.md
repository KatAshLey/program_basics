#looks for test_*.py files, and the functions that are test_*()
#unit tests for tests with code, integration test for whole container testing
#unit test you have to write test class for everything

in terminal. if it doesn't work then pip install pytest, to test functions
pytest

#shows details of pytest
pytest -vvl

#shows print functions and pytest
pytest -s

#must be imported to use testing
from fastapi.testclient import TestClient
from .main import app  #this is the file to test(main.py) and api(app from main.py)


print(response.json()) #must use pytest -s


set up folders
test folder in same level as main.py
in this folder __init__.py (empty), test_main.py

#code in test_main.py
from fastapi.testclient import TestClient
from main import app

#basic unit test
def test_basic_example():
    assert True
    
client = TestClient(app)

#example put test
def test_put_api():
    response = client.put("/items/jjn536156154",  json={
        "name": "Chewies",
        "quantity": 54351,
        "serial_num": "jjn536156154",
        "origin": {
            "country": "Ethiopia",
            "production_date": "16/09/1343"
        }
    })
    assert response.status_code==200