import requests
from datetime import datetime

USERNAME = "hisham2030"
TOKEN = "123456789"
GRAPH_ID = "graph1"

pixela_endpoint = "https://pixe.la/v1/users"

user_params = {
    "token": TOKEN,
    "username": USERNAME,
    "agreeTermsOfService": "yes",
    "notMinor": "yes",
}

##Create User
# response = requests.post(url=pixela_endpoint, json=user_params)
# print(response.text)
## Check the graph on pixe.la/v1/users/hisham2030/graphs/graph1.html

graph_endpoint = f"{pixela_endpoint}/{USERNAME}/graphs"

graph_config = {
    "id": GRAPH_ID,
    "name": "Cycling Graph",
    "unit": "Km",
    "type": "float",
    "color": "ajisai" # color names in japanese
}

headers = {
    "X-USER-TOKEN": TOKEN
}

## Create a new graph
# response = requests.post(url=graph_endpoint, json=graph_config, headers=headers)
# print(response.text)

InputDate = input("what is the date YYYYMMDD you want to use? \n")

switch = input(
    "Write a number to choose what do you want to do \n 1- Create a record \n 2- Edit a record \n 3- Delete a record\n")

if switch == "1":
    pixel_data = {
        "date": InputDate,
        "quantity": input("How many kilometers did you cycle? \n"),
    }
    pixel_creation_endpoint = f"{pixela_endpoint}/{USERNAME}/graphs/{GRAPH_ID}"
    response = requests.post(url=pixel_creation_endpoint, json=pixel_data, headers=headers)
    print(response.text)

if switch == "2":
    update_endpoint = f"{pixela_endpoint}/{USERNAME}/graphs/{GRAPH_ID}/{InputDate}"
    new_pixel_data = {
        "quantity": input("How many kilometers did you cycle? \n"),
    }
    response = requests.put(url=update_endpoint, json=new_pixel_data, headers=headers)
    print(response.text)

if switch == "3":
    delete_endpoint = f"{pixela_endpoint}/{USERNAME}/graphs/{GRAPH_ID}/{InputDate}"
    # DELETE
    response = requests.delete(url=delete_endpoint, headers=headers)
    print(response.text)
