# fancy-to-do
Create fancy to do app, using express, jquery, ajax

* RESTful endpoint for toDo's CRUD operation
* JSON formatted response

## RESTful endpoints
### GET /todos

> Get all toDo-List

_Request Header_
```
{
  "soon to be updated"
}

```

_Request Body_
```
not needed
```

_Response (200)_
```
[
    {
        "id": 1,
        "title": "<todos title>",
        "description": "<todos description>",
        "status": "<todos status after create or update>",
        "due_date": "<date when this data/object is updated/created>",
        "createdAt": "2020-04-27T07:20:33.949Z",
        "updatedAt": "2020-04-27T07:20:33.949Z"
    },
    {
        "id": 3,
        "title": "<todos title>",
        "description": "<todos description>",
        "status": "<todos status after create or update>",
        "due_date": "<date when this data/object is updated/created>",
        "createdAt": "2020-04-27T07:21:47.000Z",
        "updatedAt": "2020-04-27T08:12:59.330Z"
    },
    {
        "id": 8,
        "title": "<todos title>",
        "description": "<todos description>",
        "status": "<todos status after create or update>",
        "due_date": "<date when this data/object is updated/created>",
        "createdAt": "2020-04-27T11:04:43.556Z",
        "updatedAt": "2020-04-27T11:05:23.575Z"
    }
]

```

_Response (500 - Internal Server Error)_
```
{
  "message": "<returned error message>"
}
```

### GET /todos /:id

> Find toDo-List based on Id

_Request Header_
```
{
  "soon to be updated"
}

```

_Request Body_
```
not needed
```

_Request Params_
```
{ id: ':id' }
```

_Response (200 - Ok)_
```
[
    {
        "id": 1 <if req.params.id is '1'>,
        "title": "<todos title>",
        "description": "<todos description>",
        "status": "<todos status after create or update>",
        "due_date": "2020-04-27T07:20:33.947Z",
        "createdAt": "2020-04-27T07:20:33.949Z",
        "updatedAt": "2020-04-27T07:20:33.949Z"
    }
]

```

_Response (404 - Not Found)_
```
{
    "message": "error, data not found"
}
```

### POST /todos

> Create new toDo-List

_Request Header_
```
{
  "soon to be updated"
}

```

_Request Body_
```
{
  "title": "<posted title of toDo-list>",
  "description": "<posted description of toDo-list>",
  "status": "berhasil di-create" <default>,
  "due_date": new Date(),
}
```

_Response (201 - Created)_
```
{
    "id": <given id by system>,
    "title": "<posted title>",
    "description": "<posted description>",
    "status": "berhasil di-create",
    "due_date": "2020-04-27T11:19:26.264Z",
    "updatedAt": "2020-04-27T11:19:26.267Z",
    "createdAt": "2020-04-27T11:19:26.267Z"
}
```

_Response (400 - Bad Request)_
```
{
    "message": [
        "kolom title tidak boleh kosong" <if title column is empty>,
        "kolom description tidak boleh kosong" <if description column is empty>
    ]
}
```

_Response (500 - Internal Server Error)_
```
{
  "message": "<returned error message>"
}
```

### PUT /todos/:id

> Update toDo-List based in Id

_Request Header_
```
{
  "soon to be updated"
}

```

_Request Body_
```
{
  "title": "<updated title of toDo-list>",
  "description": "<updated description of toDo-list>",
  "status": "berhasil di-update" <default>,
  "due_date": new Date()
}
```

_Request Params_
```
{ id: ':id' }
```

_Response (200 - Ok)_
```
{
    "id": <given id by system>,
    "title": "<updated title>",
    "description": "<updated description>",
    "status": "berhasil di-update",
    "due_date": "2020-04-27T11:19:26.264Z",
    "updatedAt": "2020-04-27T11:19:26.267Z",
    "createdAt": "2020-04-27T11:19:26.267Z"
}
```

_Response (400 - Bad Request)_
```
{
    "message": [
        "kolom title tidak boleh kosong" <if title column is empty>,
        "kolom description tidak boleh kosong" <if description column is empty>
    ]
}
```

_Response (404 - Not Found)_
```
{
    "message": "error, data not found"
}
```

_Response (500 - Internal Server Error)_
```
{
  "message": "<returned error message>"
}
```

### DELETE /todos/:id

> Delete toDo-List based on Id

_Request Header_
```
{
  "soon to be updated"
}

```

_Request Body_
```
not needed
```

_Request Params_
```
{ id: ':id' }
```


_Response (200 - Ok)_
```
{
    "message": "data succesfully deleted"
}
```

_Response (404 - Not Found)_
```
{
    "message": "error, data not found"
}
```

_Response (500 - Internal Server Error)_
```
{
  "message": "<returned error message>"
}
```