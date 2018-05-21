---
swagger: "2.0"
x-collection-name: Google Classroom
x-complete: 0
info:
  title: Google Classroom API Get Aliases
  description: |-
    Returns a list of aliases for a course.

    This method returns the following error codes:

    * `PERMISSION_DENIED` if the requesting user is not permitted to access the
    course or for access errors.
    * `NOT_FOUND` if the course does not exist.
  contact:
    name: Google
    url: https://google.com
  version: v1
host: classroom.googleapis.com
basePath: /
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /v1/courses:
    get:
      summary: Get Courses
      description: |-
        Returns a list of courses that the requesting user is permitted to view,
        restricted to those that match the request.

        This method returns the following error codes:

        * `PERMISSION_DENIED` for access errors.
        * `INVALID_ARGUMENT` if the query argument is malformed.
        * `NOT_FOUND` if any users specified in the query arguments do not exist.
      operationId: classroom.courses.list
      x-api-path-slug: v1courses-get
      parameters:
      - in: query
        name: courseStates
        description: Restricts returned courses to those in one of the specified statesThe
          default value is ACTIVE, ARCHIVED, PROVISIONED, DECLINED
      - in: query
        name: pageSize
        description: Maximum number of items to return
      - in: query
        name: pageToken
        description: nextPageTokenvalue returned from a previouslist call,indicating
          that the subsequent page of results should be returned
      - in: query
        name: studentId
        description: Restricts returned courses to those having a student with the
          specifiedidentifier
      - in: query
        name: teacherId
        description: Restricts returned courses to those having a teacher with the
          specifiedidentifier
      responses:
        200:
          description: OK
      tags:
      - Course
    post:
      summary: Create Course
      description: |-
        Creates a course.

        The user specified in `ownerId` is the owner of the created course
        and added as a teacher.

        This method returns the following error codes:

        * `PERMISSION_DENIED` if the requesting user is not permitted to create
        courses or for access errors.
        * `NOT_FOUND` if the primary teacher is not a valid user.
        * `FAILED_PRECONDITION` if the course owner's account is disabled or for
        the following request errors:
            * UserGroupsMembershipLimitReached
        * `ALREADY_EXISTS` if an alias was specified in the `id` and
        already exists.
      operationId: classroom.courses.create
      x-api-path-slug: v1courses-post
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Course
  /v1/courses/{courseId}/aliases:
    get:
      summary: Get Aliases
      description: |-
        Returns a list of aliases for a course.

        This method returns the following error codes:

        * `PERMISSION_DENIED` if the requesting user is not permitted to access the
        course or for access errors.
        * `NOT_FOUND` if the course does not exist.
      operationId: classroom.courses.aliases.list
      x-api-path-slug: v1coursescourseidaliases-get
      parameters:
      - in: path
        name: courseId
        description: The identifier of the course
      - in: query
        name: pageSize
        description: Maximum number of items to return
      - in: query
        name: pageToken
        description: nextPageTokenvalue returned from a previouslist call,indicating
          that the subsequent page of results should be returned
      responses:
        200:
          description: OK
      tags:
      - Alias
x-streamrank:
  polling_total_time_average: 0
  polling_size_download_average: 0
  streaming_total_time_average: 0
  streaming_size_download_average: 0
  change_yes: 0
  change_no: 0
  time_percentage: 0
  size_percentage: 0
  change_percentage: 0
  last_run: ""
  days_run: 0
  minute_run: 0
---