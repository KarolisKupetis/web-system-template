# WEB system
- [ ] Wunderlist Task API

## Description
- [ ] API made for planning your work. Create lists, tasks, reminders.

## Entity definition
-  Task
-  Entity should have 3 mandatory attributes:
    -  ID - entityt indentifying number
        -Integer. 
        -Range up to 1000000.
    -  created_at - date, when the task was created. 
        -Automatically generated value.
-  Custom attributes
    -  created_by_id - id that respresent user.
        -integer
    -  created_by_request_id - id that identifies which request created that task.(string)
        -string
        -max length (255)
    -  completed - boolean that shows if task is completed.
        -boolean (true, false, 0 ,1)
    -  list_id - id that represent to which list this task belong to.(boolean, true/false)
        -integer
    -  title - tasks name.
        -string
        -max length(255)
    -  type - type of the task.
        -string
        -max length(255)
    -  revision - special integer for distinguishing if entity was modified.
        -integer
    -  due_date -time when task should be done.
        -formatted as an ISO8601 date
    -  starred - boolean if task is defined as important
        -boolean(true,false, 1, 0)

## API definition
- GET a.wunderlist.com/api/v1/tasks return tasks that belong to a list.
        http_response : 200(OK) - if request was succesfull
        http_response : 400(BAD REQUEST) - if request was bad
        http_response : 403(FORBIDDEN) - if missing authentication
- GET a.wunderlist.com/api/v1/list return all lists that belong to user.(defined by access_token)
        http_response : 200(OK); - if request was succesfull
         http_response : 400(BAD REQUEST); - if request was bad
         http_response : 403(FORBIDDEN) - if missing authentication
- [ ] API should have at least 4 methods
    -  GET /ToDoList/tasks/:id - returns one specific task
        http_response : 200(OK); - if request was succesfull
        http_response : 400(BAD REQUEST); - if request was bad
        http_response : 403(FORBIDDEN) - if missing authentication
    -  GET /ToDoList/tasks?list_id={list_id} - returns all tasks that belong to a list
        http_response : 200(OK) - if request was successfull;
        http_response : 400(BAD REQUEST); - if request was bad
        http_response : 403(FORBIDDEN) - if missing authentication
    -  POST /ToDoList/tasks 
        http_response : 201(CREATED) - if request succesfull
        http_response : 400(BAD REQUEST); - if request was bad
        http_response : 403(FORBIDDEN) - if missing authentication
    -  DELETE /ToDoList/tasks/:id - deletes specific tasks based on his ID.
        http_response : 200(OK) - if request was successfull;
        http_response : 400(BAD REQUEST); - if request was bad
        http_response : 403(FORBIDDEN) - if missing authentication
    -  PATCH /ToDoList/tasks/:id - modifies task based on given parameters in request body
        http_response : 200(OK) - if request was successfull;
        http_response : 400(BAD REQUEST); - if request was bad
        http_response : 403(FORBIDDEN) - if missing authentication
        
     if given invalid route -  http_response : 404(NOT FOUND)
     
## UI frameworks
Two pages representing imaginary - https://wireframe.cc/pro/edit/245453

