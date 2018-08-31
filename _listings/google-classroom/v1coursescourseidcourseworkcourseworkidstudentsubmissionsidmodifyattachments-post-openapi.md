---
swagger: "2.0"
x-collection-name: Google Classroom
x-complete: 0
info:
  title: Google Classroom API Modify Attachments
  description: |-
    Modifies attachments of student submission.

    Attachments may only be added to student submissions belonging to course
    work objects with a `workType` of `ASSIGNMENT`.

    This request must be made by the Developer Console project of the
    [OAuth client ID](https://support.google.com/cloud/answer/6158849) used to
    create the corresponding course work item.

    This method returns the following error codes:

    * `PERMISSION_DENIED` if the requesting user is not permitted to access the
    requested course or course work, if the user is not permitted to modify
    attachments on the requested student submission, or for
    access errors.
    * `INVALID_ARGUMENT` if the request is malformed.
    * `NOT_FOUND` if the requested course, course work, or student submission
    does not exist.
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
    post:
      summary: Create Alias
      description: |-
        Creates an alias for a course.

        This method returns the following error codes:

        * `PERMISSION_DENIED` if the requesting user is not permitted to create the
        alias or for access errors.
        * `NOT_FOUND` if the course does not exist.
        * `ALREADY_EXISTS` if the alias already exists.
        * `FAILED_PRECONDITION` if the alias requested does not make sense for the
          requesting user or course (for example, if a user not in a domain
          attempts to access a domain-scoped alias).
      operationId: classroom.courses.aliases.create
      x-api-path-slug: v1coursescourseidaliases-post
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: courseId
        description: Identifier of the course to alias
      responses:
        200:
          description: OK
      tags:
      - Alias
  /v1/courses/{courseId}/aliases/{alias}:
    delete:
      summary: Delete Alias
      description: |-
        Deletes an alias of a course.

        This method returns the following error codes:

        * `PERMISSION_DENIED` if the requesting user is not permitted to remove the
        alias or for access errors.
        * `NOT_FOUND` if the alias does not exist.
        * `FAILED_PRECONDITION` if the alias requested does not make sense for the
          requesting user or course (for example, if a user not in a domain
          attempts to delete a domain-scoped alias).
      operationId: classroom.courses.aliases.delete
      x-api-path-slug: v1coursescourseidaliasesalias-delete
      parameters:
      - in: path
        name: alias
        description: Alias to delete
      - in: path
        name: courseId
        description: Identifier of the course whose alias should be deleted
      responses:
        200:
          description: OK
      tags:
      - Alias
  /v1/courses/{courseId}/courseWork:
    get:
      summary: Get Course Work
      description: |-
        Returns a list of course work that the requester is permitted to view.

        Course students may only view `PUBLISHED` course work. Course teachers
        and domain administrators may view all course work.

        This method returns the following error codes:

        * `PERMISSION_DENIED` if the requesting user is not permitted to access
        the requested course or for access errors.
        * `INVALID_ARGUMENT` if the request is malformed.
        * `NOT_FOUND` if the requested course does not exist.
      operationId: classroom.courses.courseWork.list
      x-api-path-slug: v1coursescourseidcoursework-get
      parameters:
      - in: path
        name: courseId
        description: Identifier of the course
      - in: query
        name: courseWorkStates
        description: Restriction on the work status to return
      - in: query
        name: orderBy
        description: Optional sort ordering for results
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
    post:
      summary: Create Course Work
      description: |-
        Creates course work.

        The resulting course work (and corresponding student submissions) are
        associated with the Developer Console project of the
        [OAuth client ID](https://support.google.com/cloud/answer/6158849) used to
        make the request. Classroom API requests to modify course work and student
        submissions must be made with an OAuth client ID from the associated
        Developer Console project.

        This method returns the following error codes:

        * `PERMISSION_DENIED` if the requesting user is not permitted to access the
        requested course, create course work in the requested course, share a
        Drive attachment, or for access errors.
        * `INVALID_ARGUMENT` if the request is malformed.
        * `NOT_FOUND` if the requested course does not exist.
        * `FAILED_PRECONDITION` for the following request error:
            * AttachmentNotVisible
      operationId: classroom.courses.courseWork.create
      x-api-path-slug: v1coursescourseidcoursework-post
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: courseId
        description: Identifier of the course
      responses:
        200:
          description: OK
      tags:
      - Course Work
  /v1/courses/{courseId}/courseWork/{courseWorkId}/studentSubmissions:
    get:
      summary: Get Student Submissions
      description: |-
        Returns a list of student submissions that the requester is permitted to
        view, factoring in the OAuth scopes of the request.
        `-` may be specified as the `course_work_id` to include student
        submissions for multiple course work items.

        Course students may only view their own work. Course teachers
        and domain administrators may view all student submissions.

        This method returns the following error codes:

        * `PERMISSION_DENIED` if the requesting user is not permitted to access the
        requested course or course work, or for access errors.
        * `INVALID_ARGUMENT` if the request is malformed.
        * `NOT_FOUND` if the requested course does not exist.
      operationId: classroom.courses.courseWork.studentSubmissions.list
      x-api-path-slug: v1coursescourseidcourseworkcourseworkidstudentsubmissions-get
      parameters:
      - in: path
        name: courseId
        description: Identifier of the course
      - in: path
        name: courseWorkId
        description: Identifer of the student work to request
      - in: query
        name: late
        description: Requested lateness value
      - in: query
        name: pageSize
        description: Maximum number of items to return
      - in: query
        name: pageToken
        description: nextPageTokenvalue returned from a previouslist call,indicating
          that the subsequent page of results should be returned
      - in: query
        name: states
        description: Requested submission states
      - in: query
        name: userId
        description: Optional argument to restrict returned student work to those
          owned by thestudent with the specified identifier
      responses:
        200:
          description: OK
      tags:
      - Student Submission
  /v1/courses/{courseId}/courseWork/{courseWorkId}/studentSubmissions/{id}:
    get:
      summary: Get Student Submission
      description: |-
        Returns a student submission.

        * `PERMISSION_DENIED` if the requesting user is not permitted to access the
        requested course, course work, or student submission or for
        access errors.
        * `INVALID_ARGUMENT` if the request is malformed.
        * `NOT_FOUND` if the requested course, course work, or student submission
        does not exist.
      operationId: classroom.courses.courseWork.studentSubmissions.get
      x-api-path-slug: v1coursescourseidcourseworkcourseworkidstudentsubmissionsid-get
      parameters:
      - in: path
        name: courseId
        description: Identifier of the course
      - in: path
        name: courseWorkId
        description: Identifier of the course work
      - in: path
        name: id
        description: Identifier of the student submission
      responses:
        200:
          description: OK
      tags:
      - Student Submission
    patch:
      summary: Update Fields
      description: |-
        Updates one or more fields of a student submission.

        See google.classroom.v1.StudentSubmission for details
        of which fields may be updated and who may change them.

        This request must be made by the Developer Console project of the
        [OAuth client ID](https://support.google.com/cloud/answer/6158849) used to
        create the corresponding course work item.

        This method returns the following error codes:

        * `PERMISSION_DENIED` if the requesting developer project did not create
        the corresponding course work, if the user is not permitted to make the
        requested modification to the student submission, or for
        access errors.
        * `INVALID_ARGUMENT` if the request is malformed.
        * `NOT_FOUND` if the requested course, course work, or student submission
        does not exist.
      operationId: classroom.courses.courseWork.studentSubmissions.patch
      x-api-path-slug: v1coursescourseidcourseworkcourseworkidstudentsubmissionsid-patch
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: courseId
        description: Identifier of the course
      - in: path
        name: courseWorkId
        description: Identifier of the course work
      - in: path
        name: id
        description: Identifier of the student submission
      - in: query
        name: updateMask
        description: Mask that identifies which fields on the student submission to
          update
      responses:
        200:
          description: OK
      tags:
      - Field
  /v1/courses/{courseId}/courseWork/{courseWorkId}/studentSubmissions/{id}:modifyAttachments:
    post:
      summary: Modify Attachments
      description: |-
        Modifies attachments of student submission.

        Attachments may only be added to student submissions belonging to course
        work objects with a `workType` of `ASSIGNMENT`.

        This request must be made by the Developer Console project of the
        [OAuth client ID](https://support.google.com/cloud/answer/6158849) used to
        create the corresponding course work item.

        This method returns the following error codes:

        * `PERMISSION_DENIED` if the requesting user is not permitted to access the
        requested course or course work, if the user is not permitted to modify
        attachments on the requested student submission, or for
        access errors.
        * `INVALID_ARGUMENT` if the request is malformed.
        * `NOT_FOUND` if the requested course, course work, or student submission
        does not exist.
      operationId: classroom.courses.courseWork.studentSubmissions.modifyAttachments
      x-api-path-slug: v1coursescourseidcourseworkcourseworkidstudentsubmissionsidmodifyattachments-post
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: courseId
        description: Identifier of the course
      - in: path
        name: courseWorkId
        description: Identifier of the course work
      - in: path
        name: id
        description: Identifier of the student submission
      responses:
        200:
          description: OK
      tags:
      - Attachment
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