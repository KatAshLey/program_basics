DUE 15 DEC

# Part one
short answer tcp/pcp to maintain connections
how development works
cryptography, have to research some

# part 2
basic coding exercises
templates are already made and code goes between in the block, leave lines to show where.
to test run test in terminal python
few ways to do the text to output 2.4
2.5 object orientated, raise assertion errors
2.6 modules, refactor the code and put in folders.  do not change the code

# Part 3
3.1 need ot know how many in dict, auto increment index suffix, ensure you don't rewrite existing keys.  be aware of key logic,
3.3 choose one message to retrieve
3.4 if message key exists, if it does update, not 404
3.5 if exist then delete, not 404
post api fill the gap, so if deleted then enter a new one in the gap
bonus points parametrize, to cover different test

# part 4
can create trouble, instructions to create virtual environment,
implement apis, dto and dao are already done.
how to deal with  2 DAO, get all the cars in one api
create owner first, then create car, then link
full car details includes owner details
bonus testing edge testing

==========================================================
Part 3 work in progress code
@app.post("/message")
def create_message(message: str):
    # ========================================================================
    if isinstance(message, str):
        # checks if key is being used, if it is then increment by 1 and checks again, this will take up processing time when getting to larger numbers. Will use previously deleted numbers which will eventually become out of number order eg keys 1,2,3 delete 2, next insert 1,3,2
        key_value = 1
        while f"message_{key_value}" in messages:
            key_value += 1

        # enters message into dictionary at end
        messages[f"message_{key_value}"] = message
        return {"200": f"Successfully entered message: {message}"}
    else:
        raise TypeError("String expected")

    # ========================================================================
    pass

    global messages
    if isinstance(message, str):
        # checks if key is being used, if it is then increment by 1 and checks again, this will take up processing time when getting to larger numbers. Will use previously deleted numbers which will eventually become out of number order eg keys 1,2,3 delete 2, next insert 1,3,2
        key_value = 1
        while f"message_{key_value}" in messages:
            print(f"message_{key_value}")
            key_value += 1

        if len(messages) == 0:
            messages[f"message_{key_value}"] = message
            return {"200": f"Successfully entered message: {message}"}
        else:
            # loop through each key in message dict
            key_before_insert = f"message_{key_value-1}"
            insert_message = {f"message_{key_value}": message}
            new_messages = dict()
            for key in messages:
                new_messages[key] = messages[key]

                # enter message_key_value in appropriate place
                if key == key_before_insert:
                    new_messages.update(insert_message)

            # enters message into dictionary at end
            # messages[f"message_{key_value}"] = message
            messages = new_messages
            return {"200": f"Successfully entered message: {message}"}
    else:
        raise TypeError("String expected")





@app.post("/message")
def create_message(message: str):
    # ========================================================================
    global messages
    if isinstance(message, str):
        # checks if key is being used, if it is then increment by 1 and checks again, this will take up processing time when getting to larger numbers. Will use previously deleted numbers which will eventually become out of number order eg keys 1,2,3 delete 2, next insert 1,3,2
        key_value = 1
        # enters message into empty dict
        if len(messages) == 0:
            messages[f"message_{key_value}"] = message
            return {"200": f"Successfully entered message: {message}"}
        else:
            while f"message_{key_value}" in messages:
                key_value += 1

            index_insert = key_value - 1
            key_list = list(messages.keys())
            value_list = list(messages.values())
            key_list.insert(index_insert, f"message_{key_value}")
            value_list.insert(index_insert, message)
            messages = {key_list[i]: value_list[i] for i in range(len(key_list))}
            return {"200": f"Successfully entered message: {message}"}
    else:
        raise TypeError("String expected")
