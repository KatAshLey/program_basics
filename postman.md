# ****** don't use postman in vs code, use desktop app*********
# using postman desktop app

# copy http://127....  from uvicorn in vs code
# new reference + button
# enter http address
# add parameters if needed to address eg /items?q=kdga
# add to body if needed eg {"name": "kat", "price": 35}
# hit send

# check restart homework week03 api_pt1 for more examples
# put working examples into body of postman, raw >> json
# to check if api_pt1 works in postman
# change to PUT, enter HTTP address http://127.0.0.1:8000/items/riuage56
# enter inventory item in body tab, send, should give null result
# change to GET, should return item


# ===============================================================
# vscode instructions

postman icon on side bar
in get box enter https address

headers tab
key = accept
value = application/json or plain/text

gives json version of page


code button under send button
copy curl into git bash will show you the same output

change curl to python to show the code in python

pip install "fastapi[all]"

# ===============================================================

