# snakebox-api
**snakebox-api** is a quick and simple messaging API with IP2Location integration.

## Introduction
Hi, my name is `Muhamad Nur Ikmal bin Mohd Said` and I'm from `Malaysia`. With all the challenges that I faced, I finally finished this project.
**snakebox-api** is a lightweight REST API that is built to serve instant messaging services with integration of geolocation technology
provided by the one and only, **IP2Location.com**!

## Features
Here are the features currently offered by **snakebox-api**:
1. Send messages to a centralized message database.
2. View messages written by a single user or multiple users.
3. Edit and delete messages that has been sent.
4. Identify the origin of the message sender by their location and IP address.

## Usage Instructions
### Setting Up and Launching the API
You can start by cloning this repository by using the command below:
```
$ git clone https://github.com/ikmalsaid/snakebox-api.git
```
Once done, create a new Python virtual environment and install the dependencies with `pip`:
```
$ python -m venv env
$ source env/bin/activate
(env) $ pip install -r requirements.txt
```
To save time, the following files are included with the repository:
```
snakebox-api_data/IP2LOCATION-LITE-DB3.BIN (The free version of IP2Location DB3 Database)
snakebox-api_data/snakebox-api-database.db (An empty database prepared for the project)
```
Finally, launch the API by using the following command:
```
(env) $ python main.py
```

### Using the API
* Accessing the home page of the API:
```
curl -X GET 'http://127.0.0.1:5000'
```
* Lists all messages stored by the API:
```
curl -X GET 'http://127.0.0.1:5000/messages'
```
* Lists a message from a specified `<message_id>`:
```
curl -X GET 'http://127.0.0.1:5000/messages/<message_id>'
```
* Deletes a message from a specified `<message_id>`:
```
curl -X DELETE -I 'http://127.0.0.1:5000/messages/<message_id>'
```
* Sends a message to the API by specifying `"sender_name"` and `"sender_message"`:
```
curl -X POST -H 'Content-Type: application/json; charset=utf-8' --data '{"sender_name":"ikmal","sender_message":"test message"}' 'http://127.0.0.1:5000/messages'
```
* Edits a sent message by specifying `<message_id>`, `"sender_name"` and `"sender_message"`:
```
curl -X PATCH -H 'Content-Type: application/json; charset=utf-8' --data '{"sender_name":"ikmal","sender_message":"test message"}' 'http://127.0.0.1:5000/messages/<message_id>'
```

## Example output from the API
Here is one of the outputs that you will see while using the API:
```
[
    {
        "message_id": 1,
        "creation_time": "2022-09-30T13:55:18.931707",
        "sender_name": "ikmal",
        "sender_message": "test message",
        "sender_ip": "35.237.21.8",
        "sender_country": "US",
        "sender_region": "South Carolina",
        "sender_city": "North Charleston"
    }
]
```

## License
This is free software, licensed under the MIT license.

## IP2Location Databases
- [Free Version](https://lite.ip2location.com/)
- [Commercial Version](https://ip2location.com/database/ip2location)