---
name: Google Classroom
x-slug: google-classroom
description: Google Classroom is mission control for your classes. As a free service
  for teachers and students, you can create classes, distribute assignments, send
  feedback, and see everything in one place. Instant. Paperless. Easy.
image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/google-classroom.png
x-kinRank: "9"
x-alexaRank: "0"
tags: Google Classroom
created: "2018-06-25"
modified: "2018-06-25"
url: https://raw.githubusercontent.com/streamdata-gallery-organizations/google-classroom/master/_listings/google-classroom/apis.md
specificationVersion: "0.14"
apis:
- name: Google Classroom API Get Courses
  x-api-slug: google-classroom-api
  description: |-
    Returns a list of courses that the requesting user is permitted to view,
    restricted to those that match the request.

    This method returns the following error codes:

    * `PERMISSION_DENIED` for access errors.
    * `INVALID_ARGUMENT` if the query argument is malformed.
    * `NOT_FOUND` if any users specified in the query arguments do not exist.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/google-classroom.png
  humanURL: https://classroom.google.com/
  baseURL: ://classroom.googleapis.com////v1/courses
  tags: Course
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/google-classroom/master/_listings/google-classroom/v1courses-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/google-classroom/master/_listings/google-classroom/v1courses-get-openapi.md
- name: Google Classroom API Create Course
  x-api-slug: google-classroom-api
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
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/google-classroom.png
  humanURL: https://classroom.google.com/
  baseURL: ://classroom.googleapis.com////v1/courses
  tags: Course
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/google-classroom/master/_listings/google-classroom/v1courses-post-openapi.md
- name: Google Classroom API Get Aliases
  x-api-slug: google-classroom-api
  description: |-
    Returns a list of aliases for a course.

    This method returns the following error codes:

    * `PERMISSION_DENIED` if the requesting user is not permitted to access the
    course or for access errors.
    * `NOT_FOUND` if the course does not exist.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/google-classroom.png
  humanURL: https://classroom.google.com/
  baseURL: ://classroom.googleapis.com////v1/courses/{courseId}/aliases
  tags: Alias
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/google-classroom/master/_listings/google-classroom/v1coursescourseidaliases-get-openapi.md
- name: Google Classroom API Create Alias
  x-api-slug: google-classroom-api
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
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/google-classroom.png
  humanURL: https://classroom.google.com/
  baseURL: ://classroom.googleapis.com////v1/courses/{courseId}/aliases
  tags: Alias
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/google-classroom/master/_listings/google-classroom/v1coursescourseidaliases-post-openapi.md
- name: Google Classroom API Delete Alias
  x-api-slug: google-classroom-api
  description: |-
    Deletes an alias of a course.

    This method returns the following error codes:

    * `PERMISSION_DENIED` if the requesting user is not permitted to remove the
    alias or for access errors.
    * `NOT_FOUND` if the alias does not exist.
    * `FAILED_PRECONDITION` if the alias requested does not make sense for the
      requesting user or course (for example, if a user not in a domain
      attempts to delete a domain-scoped alias).
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/google-classroom.png
  humanURL: https://classroom.google.com/
  baseURL: ://classroom.googleapis.com////v1/courses/{courseId}/aliases/{alias}
  tags: Alias
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/google-classroom/master/_listings/google-classroom/v1coursescourseidaliasesalias-delete-openapi.md
- name: Google Classroom API Get Course Work
  x-api-slug: google-classroom-api
  description: |-
    Returns a list of course work that the requester is permitted to view.

    Course students may only view `PUBLISHED` course work. Course teachers
    and domain administrators may view all course work.

    This method returns the following error codes:

    * `PERMISSION_DENIED` if the requesting user is not permitted to access
    the requested course or for access errors.
    * `INVALID_ARGUMENT` if the request is malformed.
    * `NOT_FOUND` if the requested course does not exist.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/google-classroom.png
  humanURL: https://classroom.google.com/
  baseURL: ://classroom.googleapis.com////v1/courses/{courseId}/courseWork
  tags: Alias
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/google-classroom/master/_listings/google-classroom/v1coursescourseidcoursework-get-openapi.md
- name: Google Classroom API Create Course Work
  x-api-slug: google-classroom-api
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
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/google-classroom.png
  humanURL: https://classroom.google.com/
  baseURL: ://classroom.googleapis.com////v1/courses/{courseId}/courseWork
  tags: Course Work
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/google-classroom/master/_listings/google-classroom/v1coursescourseidcoursework-post-openapi.md
- name: Google Classroom API Get Student Submissions
  x-api-slug: google-classroom-api
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
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/google-classroom.png
  humanURL: https://classroom.google.com/
  baseURL: ://classroom.googleapis.com////v1/courses/{courseId}/courseWork/{courseWorkId}/studentSubmissions
  tags: Student Submission
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/google-classroom/master/_listings/google-classroom/v1coursescourseidcourseworkcourseworkidstudentsubmissions-get-openapi.md
- name: Google Classroom API Get Student Submission
  x-api-slug: google-classroom-api
  description: |-
    Returns a student submission.

    * `PERMISSION_DENIED` if the requesting user is not permitted to access the
    requested course, course work, or student submission or for
    access errors.
    * `INVALID_ARGUMENT` if the request is malformed.
    * `NOT_FOUND` if the requested course, course work, or student submission
    does not exist.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/google-classroom.png
  humanURL: https://classroom.google.com/
  baseURL: ://classroom.googleapis.com////v1/courses/{courseId}/courseWork/{courseWorkId}/studentSubmissions/{id}
  tags: Student Submission
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/google-classroom/master/_listings/google-classroom/v1coursescourseidcourseworkcourseworkidstudentsubmissionsid-get-openapi.md
- name: Google Classroom API Update Fields
  x-api-slug: google-classroom-api
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
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/google-classroom.png
  humanURL: https://classroom.google.com/
  baseURL: ://classroom.googleapis.com////v1/courses/{courseId}/courseWork/{courseWorkId}/studentSubmissions/{id}
  tags: Field
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/google-classroom/master/_listings/google-classroom/v1coursescourseidcourseworkcourseworkidstudentsubmissionsid-patch-openapi.md
- name: Google Classroom API Modify Attachments
  x-api-slug: google-classroom-api
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
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/google-classroom.png
  humanURL: https://classroom.google.com/
  baseURL: ://classroom.googleapis.com////v1/courses/{courseId}/courseWork/{courseWorkId}/studentSubmissions/{id}:modifyAttachments
  tags: Attachment
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/google-classroom/master/_listings/google-classroom/v1coursescourseidcourseworkcourseworkidstudentsubmissionsidmodifyattachments-post-openapi.md
- name: Google Classroom API Reclaim Student Submission
  x-api-slug: google-classroom-api
  description: |-
    Reclaims a student submission on behalf of the student that owns it.

    Reclaiming a student submission transfers ownership of attached Drive
    files to the student and update the submission state.

    Only the student that owns the requested student submission may call this
    method, and only for a student submission that has been turned in.

    This request must be made by the Developer Console project of the
    [OAuth client ID](https://support.google.com/cloud/answer/6158849) used to
    create the corresponding course work item.

    This method returns the following error codes:

    * `PERMISSION_DENIED` if the requesting user is not permitted to access the
    requested course or course work, unsubmit the requested student submission,
    or for access errors.
    * `FAILED_PRECONDITION` if the student submission has not been turned in.
    * `INVALID_ARGUMENT` if the request is malformed.
    * `NOT_FOUND` if the requested course, course work, or student submission
    does not exist.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/google-classroom.png
  humanURL: https://classroom.google.com/
  baseURL: ://classroom.googleapis.com////v1/courses/{courseId}/courseWork/{courseWorkId}/studentSubmissions/{id}:reclaim
  tags: Student Submission
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/google-classroom/master/_listings/google-classroom/v1coursescourseidcourseworkcourseworkidstudentsubmissionsidreclaim-post-openapi.md
- name: Google Classroom API Get Student Submission
  x-api-slug: google-classroom-api
  description: |-
    Returns a student submission.

    Returning a student submission transfers ownership of attached Drive
    files to the student and may also update the submission state.
    Unlike the Classroom application, returning a student submission does not
    set assignedGrade to the draftGrade value.

    Only a teacher of the course that contains the requested student submission
    may call this method.

    This request must be made by the Developer Console project of the
    [OAuth client ID](https://support.google.com/cloud/answer/6158849) used to
    create the corresponding course work item.

    This method returns the following error codes:

    * `PERMISSION_DENIED` if the requesting user is not permitted to access the
    requested course or course work, return the requested student submission,
    or for access errors.
    * `INVALID_ARGUMENT` if the request is malformed.
    * `NOT_FOUND` if the requested course, course work, or student submission
    does not exist.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/google-classroom.png
  humanURL: https://classroom.google.com/
  baseURL: ://classroom.googleapis.com////v1/courses/{courseId}/courseWork/{courseWorkId}/studentSubmissions/{id}:return
  tags: Student Submission
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/google-classroom/master/_listings/google-classroom/v1coursescourseidcourseworkcourseworkidstudentsubmissionsidreturn-post-openapi.md
- name: Google Classroom API Turn in Student Submission
  x-api-slug: google-classroom-api
  description: |-
    Turns in a student submission.

    Turning in a student submission transfers ownership of attached Drive
    files to the teacher and may also update the submission state.

    This may only be called by the student that owns the specified student
    submission.

    This request must be made by the Developer Console project of the
    [OAuth client ID](https://support.google.com/cloud/answer/6158849) used to
    create the corresponding course work item.

    This method returns the following error codes:

    * `PERMISSION_DENIED` if the requesting user is not permitted to access the
    requested course or course work, turn in the requested student submission,
    or for access errors.
    * `INVALID_ARGUMENT` if the request is malformed.
    * `NOT_FOUND` if the requested course, course work, or student submission
    does not exist.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/google-classroom.png
  humanURL: https://classroom.google.com/
  baseURL: ://classroom.googleapis.com////v1/courses/{courseId}/courseWork/{courseWorkId}/studentSubmissions/{id}:turnIn
  tags: Student Submission
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/google-classroom/master/_listings/google-classroom/v1coursescourseidcourseworkcourseworkidstudentsubmissionsidturnin-post-openapi.md
- name: Google Classroom API Delete Course Work
  x-api-slug: google-classroom-api
  description: |-
    Deletes a course work.

    This request must be made by the Developer Console project of the
    [OAuth client ID](https://support.google.com/cloud/answer/6158849) used to
    create the corresponding course work item.

    This method returns the following error codes:

    * `PERMISSION_DENIED` if the requesting developer project did not create
    the corresponding course work, if the requesting user is not permitted
    to delete the requested course or for access errors.
    * `FAILED_PRECONDITION` if the requested course work has already been
    deleted.
    * `NOT_FOUND` if no course exists with the requested ID.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/google-classroom.png
  humanURL: https://classroom.google.com/
  baseURL: ://classroom.googleapis.com////v1/courses/{courseId}/courseWork/{id}
  tags: Course Work
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/google-classroom/master/_listings/google-classroom/v1coursescourseidcourseworkid-delete-openapi.md
- name: Google Classroom API Get Course Work
  x-api-slug: google-classroom-api
  description: |-
    Returns course work.

    This method returns the following error codes:

    * `PERMISSION_DENIED` if the requesting user is not permitted to access the
    requested course or course work, or for access errors.
    * `INVALID_ARGUMENT` if the request is malformed.
    * `NOT_FOUND` if the requested course or course work does not exist.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/google-classroom.png
  humanURL: https://classroom.google.com/
  baseURL: ://classroom.googleapis.com////v1/courses/{courseId}/courseWork/{id}
  tags: Course Work
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/google-classroom/master/_listings/google-classroom/v1coursescourseidcourseworkid-get-openapi.md
- name: Google Classroom API Update Fields
  x-api-slug: google-classroom-api
  description: |-
    Updates one or more fields of a course work.

    See google.classroom.v1.CourseWork for details
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
    * `FAILED_PRECONDITION` if the requested course work has already been
    deleted.
    * `NOT_FOUND` if the requested course, course work, or student submission
    does not exist.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/google-classroom.png
  humanURL: https://classroom.google.com/
  baseURL: ://classroom.googleapis.com////v1/courses/{courseId}/courseWork/{id}
  tags: Field
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/google-classroom/master/_listings/google-classroom/v1coursescourseidcourseworkid-patch-openapi.md
- name: Google Classroom API Get Students
  x-api-slug: google-classroom-api
  description: |-
    Returns a list of students of this course that the requester
    is permitted to view.

    This method returns the following error codes:

    * `NOT_FOUND` if the course does not exist.
    * `PERMISSION_DENIED` for access errors.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/google-classroom.png
  humanURL: https://classroom.google.com/
  baseURL: ://classroom.googleapis.com////v1/courses/{courseId}/students
  tags: Student
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/google-classroom/master/_listings/google-classroom/v1coursescourseidstudents-get-openapi.md
- name: Google Classroom API Add Student
  x-api-slug: google-classroom-api
  description: |-
    Adds a user as a student of a course.

    This method returns the following error codes:

    * `PERMISSION_DENIED` if the requesting user is not permitted to create
    students in this course or for access errors.
    * `NOT_FOUND` if the requested course ID does not exist.
    * `FAILED_PRECONDITION` if the requested user's account is disabled,
    for the following request errors:
        * CourseMemberLimitReached
        * CourseNotModifiable
        * UserGroupsMembershipLimitReached
    * `ALREADY_EXISTS` if the user is already a student or teacher in the
    course.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/google-classroom.png
  humanURL: https://classroom.google.com/
  baseURL: ://classroom.googleapis.com////v1/courses/{courseId}/students
  tags: Student
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/google-classroom/master/_listings/google-classroom/v1coursescourseidstudents-post-openapi.md
- name: Google Classroom API Delete Student
  x-api-slug: google-classroom-api
  description: |-
    Deletes a student of a course.

    This method returns the following error codes:

    * `PERMISSION_DENIED` if the requesting user is not permitted to delete
    students of this course or for access errors.
    * `NOT_FOUND` if no student of this course has the requested ID or if the
    course does not exist.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/google-classroom.png
  humanURL: https://classroom.google.com/
  baseURL: ://classroom.googleapis.com////v1/courses/{courseId}/students/{userId}
  tags: Student
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/google-classroom/master/_listings/google-classroom/v1coursescourseidstudentsuserid-delete-openapi.md
- name: Google Classroom API Get Student
  x-api-slug: google-classroom-api
  description: |-
    Returns a student of a course.

    This method returns the following error codes:

    * `PERMISSION_DENIED` if the requesting user is not permitted to view
    students of this course or for access errors.
    * `NOT_FOUND` if no student of this course has the requested ID or if the
    course does not exist.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/google-classroom.png
  humanURL: https://classroom.google.com/
  baseURL: ://classroom.googleapis.com////v1/courses/{courseId}/students/{userId}
  tags: Student
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/google-classroom/master/_listings/google-classroom/v1coursescourseidstudentsuserid-get-openapi.md
- name: Google Classroom API Get Teachers
  x-api-slug: google-classroom-api
  description: |-
    Returns a list of teachers of this course that the requester
    is permitted to view.

    This method returns the following error codes:

    * `NOT_FOUND` if the course does not exist.
    * `PERMISSION_DENIED` for access errors.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/google-classroom.png
  humanURL: https://classroom.google.com/
  baseURL: ://classroom.googleapis.com////v1/courses/{courseId}/teachers
  tags: Teacher
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/google-classroom/master/_listings/google-classroom/v1coursescourseidteachers-get-openapi.md
- name: Google Classroom API Create Teacher
  x-api-slug: google-classroom-api
  description: |-
    Creates a teacher of a course.

    This method returns the following error codes:

    * `PERMISSION_DENIED` if the requesting user is not  permitted to create
    teachers in this course or for access errors.
    * `NOT_FOUND` if the requested course ID does not exist.
    * `FAILED_PRECONDITION` if the requested user's account is disabled,
    for the following request errors:
        * CourseMemberLimitReached
        * CourseNotModifiable
        * CourseTeacherLimitReached
        * UserGroupsMembershipLimitReached
    * `ALREADY_EXISTS` if the user is already a teacher or student in the
    course.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/google-classroom.png
  humanURL: https://classroom.google.com/
  baseURL: ://classroom.googleapis.com////v1/courses/{courseId}/teachers
  tags: Teacher
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/google-classroom/master/_listings/google-classroom/v1coursescourseidteachers-post-openapi.md
- name: Google Classroom API Delete Teacher
  x-api-slug: google-classroom-api
  description: |-
    Deletes a teacher of a course.

    This method returns the following error codes:

    * `PERMISSION_DENIED` if the requesting user is not permitted to delete
    teachers of this course or for access errors.
    * `NOT_FOUND` if no teacher of this course has the requested ID or if the
    course does not exist.
    * `FAILED_PRECONDITION` if the requested ID belongs to the primary teacher
    of this course.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/google-classroom.png
  humanURL: https://classroom.google.com/
  baseURL: ://classroom.googleapis.com////v1/courses/{courseId}/teachers/{userId}
  tags: Teacher
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/google-classroom/master/_listings/google-classroom/v1coursescourseidteachersuserid-delete-openapi.md
- name: Google Classroom API Get Teacher
  x-api-slug: google-classroom-api
  description: |-
    Returns a teacher of a course.

    This method returns the following error codes:

    * `PERMISSION_DENIED` if the requesting user is not permitted to view
    teachers of this course or for access errors.
    * `NOT_FOUND` if no teacher of this course has the requested ID or if the
    course does not exist.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/google-classroom.png
  humanURL: https://classroom.google.com/
  baseURL: ://classroom.googleapis.com////v1/courses/{courseId}/teachers/{userId}
  tags: Teacher
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/google-classroom/master/_listings/google-classroom/v1coursescourseidteachersuserid-get-openapi.md
- name: Google Classroom API Delete Course
  x-api-slug: google-classroom-api
  description: |-
    Deletes a course.

    This method returns the following error codes:

    * `PERMISSION_DENIED` if the requesting user is not permitted to delete the
    requested course or for access errors.
    * `NOT_FOUND` if no course exists with the requested ID.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/google-classroom.png
  humanURL: https://classroom.google.com/
  baseURL: ://classroom.googleapis.com////v1/courses/{id}
  tags: Course
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/google-classroom/master/_listings/google-classroom/v1coursesid-delete-openapi.md
- name: Google Classroom API Get Course
  x-api-slug: google-classroom-api
  description: |-
    Returns a course.

    This method returns the following error codes:

    * `PERMISSION_DENIED` if the requesting user is not permitted to access the
    requested course or for access errors.
    * `NOT_FOUND` if no course exists with the requested ID.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/google-classroom.png
  humanURL: https://classroom.google.com/
  baseURL: ://classroom.googleapis.com////v1/courses/{id}
  tags: Course
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/google-classroom/master/_listings/google-classroom/v1coursesid-get-openapi.md
- name: Google Classroom API Update Fields
  x-api-slug: google-classroom-api
  description: |-
    Updates one or more fields in a course.

    This method returns the following error codes:

    * `PERMISSION_DENIED` if the requesting user is not permitted to modify the
    requested course or for access errors.
    * `NOT_FOUND` if no course exists with the requested ID.
    * `INVALID_ARGUMENT` if invalid fields are specified in the update mask or
    if no update mask is supplied.
    * `FAILED_PRECONDITION` for the following request errors:
        * CourseNotModifiable
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/google-classroom.png
  humanURL: https://classroom.google.com/
  baseURL: ://classroom.googleapis.com////v1/courses/{id}
  tags: Field
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/google-classroom/master/_listings/google-classroom/v1coursesid-patch-openapi.md
- name: Google Classroom API Update Course
  x-api-slug: google-classroom-api
  description: |-
    Updates a course.

    This method returns the following error codes:

    * `PERMISSION_DENIED` if the requesting user is not permitted to modify the
    requested course or for access errors.
    * `NOT_FOUND` if no course exists with the requested ID.
    * `FAILED_PRECONDITION` for the following request errors:
        * CourseNotModifiable
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/google-classroom.png
  humanURL: https://classroom.google.com/
  baseURL: ://classroom.googleapis.com////v1/courses/{id}
  tags: Course
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/google-classroom/master/_listings/google-classroom/v1coursesid-put-openapi.md
- name: Google Classroom API Get Invitations
  x-api-slug: google-classroom-api
  description: |-
    Returns a list of invitations that the requesting user is permitted to
    view, restricted to those that match the list request.

    *Note:* At least one of `user_id` or `course_id` must be supplied. Both
    fields can be supplied.

    This method returns the following error codes:

    * `PERMISSION_DENIED` for access errors.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/google-classroom.png
  humanURL: https://classroom.google.com/
  baseURL: ://classroom.googleapis.com////v1/invitations
  tags: Invitation
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/google-classroom/master/_listings/google-classroom/v1invitations-get-openapi.md
- name: Google Classroom API Create Invitation
  x-api-slug: google-classroom-api
  description: |-
    Creates an invitation. Only one invitation for a user and course may exist
    at a time. Delete and re-create an invitation to make changes.

    This method returns the following error codes:

    * `PERMISSION_DENIED` if the requesting user is not permitted to create
    invitations for this course or for access errors.
    * `NOT_FOUND` if the course or the user does not exist.
    * `FAILED_PRECONDITION` if the requested user's account is disabled or if
    the user already has this role or a role with greater permissions.
    * `ALREADY_EXISTS` if an invitation for the specified user and course
    already exists.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/google-classroom.png
  humanURL: https://classroom.google.com/
  baseURL: ://classroom.googleapis.com////v1/invitations
  tags: Invitation
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/google-classroom/master/_listings/google-classroom/v1invitations-post-openapi.md
- name: Google Classroom API Delete Invitation
  x-api-slug: google-classroom-api
  description: |-
    Deletes an invitation.

    This method returns the following error codes:

    * `PERMISSION_DENIED` if the requesting user is not permitted to delete the
    requested invitation or for access errors.
    * `NOT_FOUND` if no invitation exists with the requested ID.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/google-classroom.png
  humanURL: https://classroom.google.com/
  baseURL: ://classroom.googleapis.com////v1/invitations/{id}
  tags: Invitation
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/google-classroom/master/_listings/google-classroom/v1invitationsid-delete-openapi.md
- name: Google Classroom API Get Invitation
  x-api-slug: google-classroom-api
  description: |-
    Returns an invitation.

    This method returns the following error codes:

    * `PERMISSION_DENIED` if the requesting user is not permitted to view the
    requested invitation or for access errors.
    * `NOT_FOUND` if no invitation exists with the requested ID.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/google-classroom.png
  humanURL: https://classroom.google.com/
  baseURL: ://classroom.googleapis.com////v1/invitations/{id}
  tags: Invitation
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/google-classroom/master/_listings/google-classroom/v1invitationsid-get-openapi.md
- name: Google Classroom API Accept Invitation
  x-api-slug: google-classroom-api
  description: |-
    Accepts an invitation, removing it and adding the invited user to the
    teachers or students (as appropriate) of the specified course. Only the
    invited user may accept an invitation.

    This method returns the following error codes:

    * `PERMISSION_DENIED` if the requesting user is not permitted to accept the
    requested invitation or for access errors.
    * `FAILED_PRECONDITION` for the following request errors:
        * CourseMemberLimitReached
        * CourseNotModifiable
        * CourseTeacherLimitReached
        * UserGroupsMembershipLimitReached
    * `NOT_FOUND` if no invitation exists with the requested ID.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/google-classroom.png
  humanURL: https://classroom.google.com/
  baseURL: ://classroom.googleapis.com////v1/invitations/{id}:accept
  tags: Invitation
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/google-classroom/master/_listings/google-classroom/v1invitationsidaccept-post-openapi.md
- name: Google Classroom API Get Guardian Invitations
  x-api-slug: google-classroom-api
  description: |-
    Returns a list of guardian invitations that the requesting user is
    permitted to view, filtered by the parameters provided.

    This method returns the following error codes:

    * `PERMISSION_DENIED` if a `student_id` is specified, and the requesting
      user is not permitted to view guardian invitations for that student, if
      `"-"` is specified as the `student_id` and the user is not a domain
      administrator, if guardians are not enabled for the domain in question,
      or for other access errors.
    * `INVALID_ARGUMENT` if a `student_id` is specified, but its format cannot
      be recognized (it is not an email address, nor a `student_id` from the
      API, nor the literal string `me`). May also be returned if an invalid
      `page_token` or `state` is provided.
    * `NOT_FOUND` if a `student_id` is specified, and its format can be
      recognized, but Classroom has no record of that student.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/google-classroom.png
  humanURL: https://classroom.google.com/
  baseURL: ://classroom.googleapis.com////v1/userProfiles/{studentId}/guardianInvitations
  tags: Guardian Invitation
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/google-classroom/master/_listings/google-classroom/v1userprofilesstudentidguardianinvitations-get-openapi.md
- name: Google Classroom API Create Guardian Invitation
  x-api-slug: google-classroom-api
  description: |-
    Creates a guardian invitation, and sends an email to the guardian asking
    them to confirm that they are the student's guardian.

    Once the guardian accepts the invitation, their `state` will change to
    `COMPLETED` and they will start receiving guardian notifications. A
    `Guardian` resource will also be created to represent the active guardian.

    The request object must have the `student_id` and
    `invited_email_address` fields set. Failing to set these fields, or
    setting any other fields in the request, will result in an error.

    This method returns the following error codes:

    * `PERMISSION_DENIED` if the current user does not have permission to
      manage guardians, if the guardian in question has already rejected
      too many requests for that student, if guardians are not enabled for the
      domain in question, or for other access errors.
    * `RESOURCE_EXHAUSTED` if the student or guardian has exceeded the guardian
      link limit.
    * `INVALID_ARGUMENT` if the guardian email address is not valid (for
      example, if it is too long), or if the format of the student ID provided
      cannot be recognized (it is not an email address, nor a `user_id` from
      this API). This error will also be returned if read-only fields are set,
      or if the `state` field is set to to a value other than `PENDING`.
    * `NOT_FOUND` if the student ID provided is a valid student ID, but
      Classroom has no record of that student.
    * `ALREADY_EXISTS` if there is already a pending guardian invitation for
      the student and `invited_email_address` provided, or if the provided
      `invited_email_address` matches the Google account of an existing
      `Guardian` for this user.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/google-classroom.png
  humanURL: https://classroom.google.com/
  baseURL: ://classroom.googleapis.com////v1/userProfiles/{studentId}/guardianInvitations
  tags: Guardian Invitation
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/google-classroom/master/_listings/google-classroom/v1userprofilesstudentidguardianinvitations-post-openapi.md
- name: Google Classroom API Get Guardian Invitation
  x-api-slug: google-classroom-api
  description: |-
    Returns a specific guardian invitation.

    This method returns the following error codes:

    * `PERMISSION_DENIED` if the requesting user is not permitted to view
      guardian invitations for the student identified by the `student_id`, if
      guardians are not enabled for the domain in question, or for other
      access errors.
    * `INVALID_ARGUMENT` if a `student_id` is specified, but its format cannot
      be recognized (it is not an email address, nor a `student_id` from the
      API, nor the literal string `me`).
    * `NOT_FOUND` if Classroom cannot find any record of the given student or
      `invitation_id`. May also be returned if the student exists, but the
      requesting user does not have access to see that student.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/google-classroom.png
  humanURL: https://classroom.google.com/
  baseURL: ://classroom.googleapis.com////v1/userProfiles/{studentId}/guardianInvitations/{invitationId}
  tags: Guardian Invitation
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/google-classroom/master/_listings/google-classroom/v1userprofilesstudentidguardianinvitationsinvitationid-get-openapi.md
- name: Google Classroom API Update Guardian Invitations
  x-api-slug: google-classroom-api
  description: |-
    Modifies a guardian invitation.

    Currently, the only valid modification is to change the `state` from
    `PENDING` to `COMPLETE`. This has the effect of withdrawing the invitation.

    This method returns the following error codes:

    * `PERMISSION_DENIED` if the current user does not have permission to
      manage guardians, if guardians are not enabled for the domain in question
      or for other access errors.
    * `FAILED_PRECONDITION` if the guardian link is not in the `PENDING` state.
    * `INVALID_ARGUMENT` if the format of the student ID provided
      cannot be recognized (it is not an email address, nor a `user_id` from
      this API), or if the passed `GuardianInvitation` has a `state` other than
      `COMPLETE`, or if it modifies fields other than `state`.
    * `NOT_FOUND` if the student ID provided is a valid student ID, but
      Classroom has no record of that student, or if the `id` field does not
      refer to a guardian invitation known to Classroom.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/google-classroom.png
  humanURL: https://classroom.google.com/
  baseURL: ://classroom.googleapis.com////v1/userProfiles/{studentId}/guardianInvitations/{invitationId}
  tags: Guardian Invitation
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/google-classroom/master/_listings/google-classroom/v1userprofilesstudentidguardianinvitationsinvitationid-patch-openapi.md
- name: Google Classroom API Get Guardians
  x-api-slug: google-classroom-api
  description: |-
    Returns a list of guardians that the requesting user is permitted to
    view, restricted to those that match the request.

    To list guardians for any student that the requesting user may view
    guardians for, use the literal character `-` for the student ID.

    This method returns the following error codes:

    * `PERMISSION_DENIED` if a `student_id` is specified, and the requesting
      user is not permitted to view guardian information for that student, if
      `"-"` is specified as the `student_id` and the user is not a domain
      administrator, if guardians are not enabled for the domain in question,
      if the `invited_email_address` filter is set by a user who is not a
      domain administrator, or for other access errors.
    * `INVALID_ARGUMENT` if a `student_id` is specified, but its format cannot
      be recognized (it is not an email address, nor a `student_id` from the
      API, nor the literal string `me`). May also be returned if an invalid
      `page_token` is provided.
    * `NOT_FOUND` if a `student_id` is specified, and its format can be
      recognized, but Classroom has no record of that student.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/google-classroom.png
  humanURL: https://classroom.google.com/
  baseURL: ://classroom.googleapis.com////v1/userProfiles/{studentId}/guardians
  tags: Guardian
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/google-classroom/master/_listings/google-classroom/v1userprofilesstudentidguardians-get-openapi.md
- name: Google Classroom API Delete Guardian
  x-api-slug: google-classroom-api
  description: |-
    Deletes a guardian.

    The guardian will no longer receive guardian notifications and the guardian
    will no longer be accessible via the API.

    This method returns the following error codes:

    * `PERMISSION_DENIED` if no user that matches the provided `student_id`
      is visible to the requesting user, if the requesting user is not
      permitted to manage guardians for the student identified by the
      `student_id`, if guardians are not enabled for the domain in question,
      or for other access errors.
    * `INVALID_ARGUMENT` if a `student_id` is specified, but its format cannot
      be recognized (it is not an email address, nor a `student_id` from the
      API).
    * `NOT_FOUND` if the requesting user is permitted to modify guardians for
      the requested `student_id`, but no `Guardian` record exists for that
      student with the provided `guardian_id`.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/google-classroom.png
  humanURL: https://classroom.google.com/
  baseURL: ://classroom.googleapis.com////v1/userProfiles/{studentId}/guardians/{guardianId}
  tags: Guardian
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/google-classroom/master/_listings/google-classroom/v1userprofilesstudentidguardiansguardianid-delete-openapi.md
- name: Google Classroom API Get Guardian
  x-api-slug: google-classroom-api
  description: |-
    Returns a specific guardian.

    This method returns the following error codes:

    * `PERMISSION_DENIED` if no user that matches the provided `student_id`
      is visible to the requesting user, if the requesting user is not
      permitted to view guardian information for the student identified by the
      `student_id`, if guardians are not enabled for the domain in question,
      or for other access errors.
    * `INVALID_ARGUMENT` if a `student_id` is specified, but its format cannot
      be recognized (it is not an email address, nor a `student_id` from the
      API, nor the literal string `me`).
    * `NOT_FOUND` if the requesting user is permitted to view guardians for
      the requested `student_id`, but no `Guardian` record exists for that
      student that matches the provided `guardian_id`.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/google-classroom.png
  humanURL: https://classroom.google.com/
  baseURL: ://classroom.googleapis.com////v1/userProfiles/{studentId}/guardians/{guardianId}
  tags: Guardian
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/google-classroom/master/_listings/google-classroom/v1userprofilesstudentidguardiansguardianid-get-openapi.md
- name: Google Classroom API Get User
  x-api-slug: google-classroom-api
  description: |-
    Returns a user profile.

    This method returns the following error codes:

    * `PERMISSION_DENIED` if the requesting user is not permitted to access
    this user profile, if no profile exists with the requested ID, or for
    access errors.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/google-classroom.png
  humanURL: https://classroom.google.com/
  baseURL: ://classroom.googleapis.com////v1/userProfiles/{userId}
  tags: User
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/google-classroom/master/_listings/google-classroom/v1userprofilesuserid-get-openapi.md
- name: Google Classroom API
  x-api-slug: google-classroom-api
  description: Google Classroom is mission control for your classes. As a free service
    for teachers and students, you can create classes, distribute assignments, send
    feedback, and see everything in one place. Instant. Paperless. Easy.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/google-classroom.png
  humanURL: https://classroom.google.com/
  baseURL: ://classroom.googleapis.com//
  tags: Google Classroom
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/google-classroom/master/_listings/google-classroom/openapi.md
x-common:
- type: x-button
  url: https://developers.google.com/classroom/guides/sharebutton
- type: x-developer
  url: https://developers.google.com/classroom/
- type: x-getting-started
  url: ""
- type: x-issues
  url: https://code.google.com/a/google.com/p/apps-api-issues/issues/list?can=2&q=label%3AAPI-Classroom
- type: x-website
  url: https://classroom.google.com/
include: []
maintainers:
- FN: Kin Lane
  x-twitter: apievangelist
  email: info@apievangelist.com
---