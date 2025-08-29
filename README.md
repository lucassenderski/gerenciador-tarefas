# gerenciador-tarefas
Implementação de uma API de Tarefas 

Create Task
This endpoint allows you to create a new task in the system. 
Request
Method: POST
URL: http://localhost:8080/tarefas
Content-Type: application/json

Request Body Parameters
The request body should be a JSON object containing the following parameters:
nome (string): The name of the task you want to create. 
dataEntrega (string): The due date for the task in the format YYYY-MM-DD.
responsavel (string): The name of the person responsible for the task.

Example Request Body:


JSON


{
  "nome": "Estudar Spring Boot",
  "dataEntrega": "2025-09-01",
  "responsavel": "Lucas"
}


Response
Upon a successful request, the server will respond with a status code of 200 and a JSON object containing the following fields:
id (integer): The unique identifier for the newly created task.
nome (string): The name of the task.
dataEntrega (string): The due date of the task.
responsavel (string): The name of the person responsible for the task.

Example Response:


JSON

{
  "id": 0,
  "nome": "",
  "dataEntrega": "",
  "responsavel": ""
}


Notes
Ensure that all required fields are provided in the request body.
The response will include the details of the created task, including its unique ID.
This endpoint is useful for task management applications where users can track their tasks and responsibilities.



Update Task
This endpoint allows you to update an existing task identified by its unique ID. In this case, the task with ID 9 is being updated with new details.
Request
Method: PUT
URL: http://localhost:8080/tarefas/9
Headers:
Content-Type: application/json (indicates that the request body is in JSON format)


Request Body
The request body must be in JSON format and should contain the following fields:
nome (string): The name of the task.
responsavel (string): The name of the person responsible for the task.
dataEntrega (string): The due date for the task, formatted as DD/MM/YYYY.

Example:


JSON

{
  "nome": "Desenvolvimento da API",
  "responsavel": "Lucas Frank Senderski 4758862",
  "dataEntrega": "12/12/2025"
}


Response
Upon a successful update, the API will return a response with a status code of 200 and the following structure:
Content-Type: application/json
Response Body:
id (integer): The unique identifier of the task.
nome (string): The updated name of the task.
responsavel (string): The updated name of the person responsible for the task.
dataEntrega (string): The updated due date for the task.


Example Response:


JSON


{
  "id": 0,
  "nome": "",
  "responsavel": "",
  "dataEntrega": ""
}


Notes
Ensure that the task ID in the URL corresponds to an existing task; otherwise, the update will not be processed.
The response will reflect the updated task details based on the provided request body.


 Get Tarefas
This endpoint retrieves a list of tasks from the server.
Request
Method: GET
Endpoint: http://localhost:8080/tarefas

Response
Status Code: 200 OK
Content-Type: application/json

Response Format
The response will return a JSON array containing task objects. Each task object includes the following fields:
id (integer): The unique identifier of the task.
nome (string): The name of the task.
responsavel (string): The person responsible for the task.
dataEntrega (string): The due date for the task.

Example response:


JSON
[
    {
        "id": 0,
        "nome": "",
        "responsavel": "",
        "dataEntrega": ""
    }
]


This endpoint does not require any parameters and will return an empty array if no tasks are available.

DELETE Tarefa
This endpoint is used to delete a specific task (tarefa) identified by its unique ID from the system. The request is sent to the specified URL, where the ID of the task to be deleted is included in the path.
Request
Method: DELETE
URL: http://localhost:8080/tarefas/{id}

Path Parameter
id (required): The unique identifier of the task you want to delete. In the example provided, the ID is 9.

Request Body
The request body should be in JSON format, containing the following fields:
nome (string): The name associated with the task.
email (string): The email of the user related to the task.
fone (string): The phone number associated with the task.

Example Request Body:


JSON

{
  "nome": "Lucas Frank Senderski",
  "email": "lucasfsenderski@gmail.com",
  "fone": "(45) 988241374"
}


Response
Upon successful deletion of the task, the server responds with:
Status Code: 200 OK indicating that the request was successful.
Content-Type: text/xml, although the body may not contain any content (null).

Usage
To effectively use this DELETE request, ensure that you provide the correct ID in the URL and include the necessary fields in the request body. A successful response indicates that the task has been deleted from the system.
