# gerenciador-tarefas
Implementação de uma API de Tarefas 

Create Task
This endpoint allows you to create a new task in the system. It is designed for task management applications where users can track their tasks and responsibilities.
Request
Method: POST
URL: http://localhost:8080/tarefas
Content-Type: application/json

Purpose
The purpose of this request is to submit a new task to the system, which will be stored for future reference and management.
Request Body Parameters
The request body should be a JSON object containing the following parameters:
nome (string): The name of the task you want to create. This should be a brief description of the task.
dataEntrega (string): The due date for the task, formatted as YYYY-MM-DD. This indicates when the task is expected to be completed.
responsavel (string): The name of the person responsible for the task. This helps in identifying who is accountable for the task.

Example Request Body:


JSON


{
        "nome": "Desenvolvimento da API",
        "responsavel": "Lucas 4758862",
        "dataEntrega": "12/12/2025"
}


Response
Upon a successful request, the server will respond with a status code of 200 and a JSON object containing the following fields:
id (integer): The unique identifier for the newly created task. This ID can be used for future reference to the task.
nome (string): The name of the task as provided in the request.
dataEntrega (string): The due date of the task as provided in the request.
responsavel (string): The name of the person responsible for the task as provided in the request.

Example Response:


JSON


{
  "id":11,
  "nome": "Desenvolvimento da API",
  "responsavel": "Lucas 4758862",
  "dataEntrega": "12/12/2025"
}


Notes
Ensure that all required fields are provided in the request body to avoid errors.
The response will include the details of the created task, including its unique ID, which can be used for further operations such as updates or deletions.
This endpoint is essential for managing tasks effectively, allowing users to add and track their responsibilities within the application.


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


This endpoint does not require any parameters and will return an empty array if no tasks are available.

Delete Task
This endpoint allows you to delete a specific task identified by its unique ID. In this case, the task with ID 9 is being targeted for deletion.
Request
Method: DELETE
Endpoint: http://localhost:8080/tarefas/9

Headers
Content-Type: application/json

Request Body
The request body must be in JSON format and can include the following parameters:
nome (string): The name associated with the task.
email (string): The email address related to the task.
fone (string): The phone number linked to the task.

Example Request Body:


JSON

{
  "nome": "Desenvolvimento da API",
  "responsavel": "Lucas Frank Senderski 4758862",
  "dataEntrega": "12/12/2025"
}


Response
Upon successful deletion, the API will return:
Status: 200 OK
Content-Type: text/xml
Body: The response body may not contain any additional information.

Notes
Ensure that the task ID in the endpoint corresponds to an existing task to avoid errors.
The response indicates a successful deletion, but no content will be returned in the body.

This endpoint is used to delete a specific task (tarefa) identified by its unique ID. In this case, the task with ID 9 will be removed from the system.
Request
Method: DELETE
URL: http://localhost:8080/tarefas/9

Request Body
The request body should be in JSON format and includes the following parameters:
nome (string): The name associated with the task.
email (string): The email address related to the task.
fone (string): The phone number linked to the task.

Example Payload:


JSON

{
  "nome": "Desenvolvimento da API",
  "responsavel": "Lucas Frank Senderski 4758862",
  "dataEntrega": "12/12/2025"
}



