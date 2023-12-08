


from fastapi.testclient import TestClient
from .main import app
import pytest


@pytest.fixture
def client():
    yield TestClient(app)


def test_sample(client):
    assert True


# ========================================================================
# the above client fixture was not resetting at the end of each test, with Ahn's help we discovered that if the test client was defined within each test function, the tests would run as intended.  message.clear() was not working to clear the dict
# from .main import messages

@pytest.fixture(function)
def client02():
    test_client = TestClient(app)
    yield test_client
    test_client.close()


@pytest.fixture
def good_beans01():
    return "jellybeans01"


@pytest.fixture
def good_beans02():
    return "jellybeans02"


@pytest.fixture
def good_beans03():
    return "jellybeans03"


@pytest.fixture
def good_beans04():
    return "jellybeans04"


# POST Valid str message
def test_create_message(good_beans01):
    # ensures an empty test client is made
    from .main import messages
    client02 = TestClient(app)
    messages.clear()

    # Tests for a valid string entry
    response = client02.post("/message", params={"message": good_beans01})
    assert response.status_code == 200
    assert response.json() == {"200": f"Successfully entered message: {good_beans01}"}


# POST Invalid empty message field
def test_create_message_unsuccessful():
    # ensures an empty test client is made
    from .main import messages

    client02 = TestClient(app)
    messages.clear()

    # Tests for an invalid string entry
    bad_payload = ""
    response = client02.post("/message", params={"message": bad_payload})
    assert response.status_code == 404
    assert response.json() == {"detail": "Message is not found, please enter message"}


# GET All Valid dict
def test_get_all_messages(good_beans01, good_beans02, good_beans03, good_beans04):
    # ensures an empty test client is made
    from .main import messages

    client02 = TestClient(app)
    messages.clear()

    # Posts 4 entries into message dict
    client02.post("/message", params={"message": good_beans01})
    client02.post("/message", params={"message": good_beans02})
    client02.post("/message", params={"message": good_beans03})
    client02.post("/message", params={"message": good_beans04})

    # GET all and change data to json
    get_response = client02.get("/")
    get_response_data = get_response.json()

    # Valid list of beans to compare
    good_beans_collection = {
        "message_1": good_beans01,
        "message_2": good_beans02,
        "message_3": good_beans03,
        "message_4": good_beans04,
    }

    # compares GET json with valid list of beans
    for key, nested_collection in get_response_data.items():
        assert key == "200"
        for inner_key, value in nested_collection.items():
            assert inner_key in good_beans_collection
            assert value == good_beans_collection[inner_key]


# GET All Invalid dict (empty dict)
def test_get_all_messages_unsuccessful():
    # ensures an empty test client is made
    from .main import messages

    client02 = TestClient(app)
    messages.clear()

    # uses Get on empty dict
    get_response = client02.get("/")
    assert get_response.status_code == 404


#                 _                                _
#                | |                              | |
#    ___ ___   __| | ___    __ _  ___   ___  ___  | |__   ___ _ __ ___
#   / __/ _ \ / _` |/ _ \  / _` |/ _ \ / _ \/ __| | '_ \ / _ \ '__/ _ \
#  | (_| (_) | (_| |  __/ | (_| | (_) |  __/\__ \ | | | |  __/ | |  __/
#   \___\___/ \__,_|\___|  \__, |\___/ \___||___/ |_| |_|\___|_|  \___|
#                           __/ |
#                          |___/
# ========================================================================
