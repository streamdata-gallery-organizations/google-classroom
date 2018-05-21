{
  "info": {
    "name": "Google Classroom API Get Courses",
    "_postman_id": "48e50e4f-a3d3-47ca-9ff3-94f4fabb16a2",
    "description": "Returns a list of courses that the requesting user is permitted to view,\nrestricted to those that match the request.\n\nThis method returns the following error codes:\n\n* `PERMISSION_DENIED` for access errors.\n* `INVALID_ARGUMENT` if the query argument is malformed.\n* `NOT_FOUND` if any users specified in the query arguments do not exist.",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "Course",
      "item": [
        {
          "id": "f821f8bf-e66d-464c-8164-2f309f5c1ca5",
          "name": "classroom.courses.list",
          "request": {
            "url": "http://classroom.googleapis.com/v1/courses?courseStates=%7B%7D&pageSize=%7B%7D&pageToken=%7B%7D&studentId=%7B%7D&teacherId=%7B%7D",
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "Returns a list of courses that the requesting user is permitted to view,\nrestricted to those that match the request.\n\nThis method returns the following error codes:\n\n* `PERMISSION_DENIED` for access errors.\n* `INVALID_ARGUMENT` if the query argument is malformed.\n* `NOT_FOUND` if any users specified in the query arguments do not exist."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "a076f929-a498-4289-8121-12bf67a96d20"
            }
          ]
        }
      ]
    }
  ]
}