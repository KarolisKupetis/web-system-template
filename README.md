# WEB system
- [ ] Wunderlist Task API

## Description
- [ ] API made for planning your work. Create lists, tasks, reminders.

## Entity definition
- [ ] Task
- [ ] Entity should have 3 mandatory attributes:
    - [ ] ID - number
    - [ ] created_at
- [ ] Custom attributes
    - [ ] created_by_id - id that respresent user.(unique integer)
    - [ ] created_by_request_id - id that identifies which request created that task.(string)
    - [ ] completed - boolean that shows if task is completed.
    - [ ] list_id - id that represent to which list this task belong to.(boolean, true/false)
    - [ ] title - tasks name.
    - [ ] type - type of the task.
    - [ ] revision - special integer for distinguishing if entity was modified.
    - [ ] starred - boolean if task is defined as important

## API definition
- GET a.wunderlist.com/api/v1/tasks return tasks that belong to somewhat list.
        http_response : 200
- GET a.wunderlist.com/api/v1/list return all lists that belong to user.(defined by access_token)
        http_response : 200;
        
- [ ] API should have at least 4 methods

    -  GET /ToDoList/tasks/:id - returns one specific task
        http_response : 200;
    -  GET /ToDoList/tasks?list_id={list_id} - returns all tasks that belong to a list
        http_response : 200;
    -  POST /ToDoList/tasks 
        http_response : 201;
    -  DELETE /ToDoList/tasks/:id - deletes specific tasks based on his ID.
    -  PATCH /ToDoList/tasks/:id - modifies task based on given parameters in request body
    
    If wrong request url given 404 status code is presented.
