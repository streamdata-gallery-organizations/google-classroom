---
swagger: "2.0"
info:
  title: Google Classroom
  description: Manages classes, rosters, and invitations in Google Classroom.
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
  /v1/courses/{courseId}/courseWork/{id}:
    patch:
      summary: Update Fields
      description: Updates one or more fields of a course work
      operationId: classroom.courses.courseWork.patch
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: courseId
        description: Identifier of the course
      - in: path
        name: id
        description: Identifier of the course work
      - in: query
        name: updateMask
        description: Mask that identifies which fields on the course work to update
      responses:
        200:
          description: OK
      tags:
      - field
definitions:
  Assignment:
    properties: []
  AssignmentSubmission:
    properties:
      attachments:
        description: This is a default description.
        type: parameters
  Attachment:
    properties: []
  Course:
    properties:
      alternateLink:
        description: This is a default description.
        type: parameters
      courseGroupEmail:
        description: This is a default description.
        type: parameters
      courseMaterialSets:
        description: This is a default description.
        type: parameters
      courseState:
        description: This is a default description.
        type: parameters
      creationTime:
        description: This is a default description.
        type: parameters
      description:
        description: This is a default description.
        type: parameters
      descriptionHeading:
        description: This is a default description.
        type: parameters
      enrollmentCode:
        description: This is a default description.
        type: parameters
      guardiansEnabled:
        description: This is a default description.
        type: parameters
      id:
        description: This is a default description.
        type: parameters
  CourseAlias:
    properties:
      alias:
        description: This is a default description.
        type: parameters
  CourseMaterial:
    properties: []
  CourseMaterialSet:
    properties:
      materials:
        description: This is a default description.
        type: parameters
      title:
        description: This is a default description.
        type: parameters
  CourseWork:
    properties:
      alternateLink:
        description: This is a default description.
        type: parameters
      associatedWithDeveloper:
        description: This is a default description.
        type: parameters
      courseId:
        description: This is a default description.
        type: parameters
      creationTime:
        description: This is a default description.
        type: parameters
      description:
        description: This is a default description.
        type: parameters
      id:
        description: This is a default description.
        type: parameters
      materials:
        description: This is a default description.
        type: parameters
      maxPoints:
        description: This is a default description.
        type: parameters
      state:
        description: This is a default description.
        type: parameters
      submissionModificationMode:
        description: This is a default description.
        type: parameters
  Date:
    properties:
      day:
        description: This is a default description.
        type: parameters
      month:
        description: This is a default description.
        type: parameters
      year:
        description: This is a default description.
        type: parameters
  DriveFile:
    properties:
      alternateLink:
        description: This is a default description.
        type: parameters
      id:
        description: This is a default description.
        type: parameters
      thumbnailUrl:
        description: This is a default description.
        type: parameters
      title:
        description: This is a default description.
        type: parameters
  DriveFolder:
    properties:
      alternateLink:
        description: This is a default description.
        type: parameters
      id:
        description: This is a default description.
        type: parameters
      title:
        description: This is a default description.
        type: parameters
  Empty:
    properties: []
  Form:
    properties:
      formUrl:
        description: This is a default description.
        type: parameters
      responseUrl:
        description: This is a default description.
        type: parameters
      thumbnailUrl:
        description: This is a default description.
        type: parameters
      title:
        description: This is a default description.
        type: parameters
  GlobalPermission:
    properties:
      permission:
        description: This is a default description.
        type: parameters
  Guardian:
    properties:
      guardianId:
        description: This is a default description.
        type: parameters
      invitedEmailAddress:
        description: This is a default description.
        type: parameters
      studentId:
        description: This is a default description.
        type: parameters
  GuardianInvitation:
    properties:
      creationTime:
        description: This is a default description.
        type: parameters
      invitationId:
        description: This is a default description.
        type: parameters
      invitedEmailAddress:
        description: This is a default description.
        type: parameters
      state:
        description: This is a default description.
        type: parameters
      studentId:
        description: This is a default description.
        type: parameters
  Invitation:
    properties:
      courseId:
        description: This is a default description.
        type: parameters
      id:
        description: This is a default description.
        type: parameters
      role:
        description: This is a default description.
        type: parameters
      userId:
        description: This is a default description.
        type: parameters
  Link:
    properties:
      thumbnailUrl:
        description: This is a default description.
        type: parameters
      title:
        description: This is a default description.
        type: parameters
      url:
        description: This is a default description.
        type: parameters
  ListCourseAliasesResponse:
    properties:
      aliases:
        description: This is a default description.
        type: parameters
      nextPageToken:
        description: This is a default description.
        type: parameters
  ListCourseWorkResponse:
    properties:
      courseWork:
        description: This is a default description.
        type: parameters
      nextPageToken:
        description: This is a default description.
        type: parameters
  ListCoursesResponse:
    properties:
      courses:
        description: This is a default description.
        type: parameters
      nextPageToken:
        description: This is a default description.
        type: parameters
  ListGuardianInvitationsResponse:
    properties:
      guardianInvitations:
        description: This is a default description.
        type: parameters
      nextPageToken:
        description: This is a default description.
        type: parameters
  ListGuardiansResponse:
    properties:
      guardians:
        description: This is a default description.
        type: parameters
      nextPageToken:
        description: This is a default description.
        type: parameters
  ListInvitationsResponse:
    properties:
      invitations:
        description: This is a default description.
        type: parameters
      nextPageToken:
        description: This is a default description.
        type: parameters
  ListStudentSubmissionsResponse:
    properties:
      nextPageToken:
        description: This is a default description.
        type: parameters
      studentSubmissions:
        description: This is a default description.
        type: parameters
  ListStudentsResponse:
    properties:
      nextPageToken:
        description: This is a default description.
        type: parameters
      students:
        description: This is a default description.
        type: parameters
  ListTeachersResponse:
    properties:
      nextPageToken:
        description: This is a default description.
        type: parameters
      teachers:
        description: This is a default description.
        type: parameters
  Material:
    properties: []
  ModifyAttachmentsRequest:
    properties:
      addAttachments:
        description: This is a default description.
        type: parameters
  MultipleChoiceQuestion:
    properties:
      choices:
        description: This is a default description.
        type: parameters
  MultipleChoiceSubmission:
    properties:
      answer:
        description: This is a default description.
        type: parameters
  Name:
    properties:
      familyName:
        description: This is a default description.
        type: parameters
      fullName:
        description: This is a default description.
        type: parameters
      givenName:
        description: This is a default description.
        type: parameters
  ReclaimStudentSubmissionRequest:
    properties: []
  ReturnStudentSubmissionRequest:
    properties: []
  SharedDriveFile:
    properties:
      shareMode:
        description: This is a default description.
        type: parameters
  ShortAnswerSubmission:
    properties:
      answer:
        description: This is a default description.
        type: parameters
  Student:
    properties:
      courseId:
        description: This is a default description.
        type: parameters
      userId:
        description: This is a default description.
        type: parameters
  StudentSubmission:
    properties:
      alternateLink:
        description: This is a default description.
        type: parameters
      assignedGrade:
        description: This is a default description.
        type: parameters
      associatedWithDeveloper:
        description: This is a default description.
        type: parameters
      courseId:
        description: This is a default description.
        type: parameters
      courseWorkId:
        description: This is a default description.
        type: parameters
      courseWorkType:
        description: This is a default description.
        type: parameters
      creationTime:
        description: This is a default description.
        type: parameters
      draftGrade:
        description: This is a default description.
        type: parameters
      id:
        description: This is a default description.
        type: parameters
      late:
        description: This is a default description.
        type: parameters
  Teacher:
    properties:
      courseId:
        description: This is a default description.
        type: parameters
      userId:
        description: This is a default description.
        type: parameters
  TimeOfDay:
    properties:
      hours:
        description: This is a default description.
        type: parameters
      minutes:
        description: This is a default description.
        type: parameters
      nanos:
        description: This is a default description.
        type: parameters
      seconds:
        description: This is a default description.
        type: parameters
  TurnInStudentSubmissionRequest:
    properties: []
  UserProfile:
    properties:
      emailAddress:
        description: This is a default description.
        type: parameters
      id:
        description: This is a default description.
        type: parameters
      permissions:
        description: This is a default description.
        type: parameters
      photoUrl:
        description: This is a default description.
        type: parameters
  YouTubeVideo:
    properties:
      alternateLink:
        description: This is a default description.
        type: parameters
      id:
        description: This is a default description.
        type: parameters
      thumbnailUrl:
        description: This is a default description.
        type: parameters
      title:
        description: This is a default description.
        type: parameters
x-collection-name: Google Classroom
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