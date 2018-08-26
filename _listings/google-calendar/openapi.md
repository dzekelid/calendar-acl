---
swagger: "2.0"
x-collection-name: Google Calendar
x-complete: 1
info:
  title: Google Calendar
  description: manipulates-events-and-other-calendar-data-
  contact:
    name: Google
    url: https://google.com
  version: v3/
host: www.googleapis.com
basePath: /calendar/v3
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /calendars/{calendarId}/acl:
    get:
      summary: Get Calendar ACL
      description: Returns the rules in the access control list for the calendar.
      operationId: calendar.acl.list
      x-api-path-slug: calendarscalendaridacl-get
      parameters:
      - in: path
        name: calendarId
        description: Calendar identifier
      - in: query
        name: maxResults
        description: Maximum number of entries returned on one result page
      - in: query
        name: pageToken
        description: Token specifying which result page to return
      - in: query
        name: showDeleted
        description: Whether to include deleted ACLs in the result
      - in: query
        name: syncToken
        description: Token obtained from the nextSyncToken field returned on the last
          page of results from the previous list request
      responses:
        200:
          description: OK
      tags:
      - Calendar ACL
    post:
      summary: Create Calendar ACL
      description: Creates an access control rule.
      operationId: calendar.acl.insert
      x-api-path-slug: calendarscalendaridacl-post
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: calendarId
        description: Calendar identifier
      responses:
        200:
          description: OK
      tags:
      - Calendar ACL
  /calendars/{calendarId}/acl/watch:
    post:
      summary: Watch Calendar ACL
      description: Watch for changes to ACL resources.
      operationId: calendar.acl.watch
      x-api-path-slug: calendarscalendaridaclwatch-post
      parameters:
      - in: path
        name: calendarId
        description: Calendar identifier
      - in: query
        name: maxResults
        description: Maximum number of entries returned on one result page
      - in: query
        name: pageToken
        description: Token specifying which result page to return
      - in: body
        name: resource
        schema:
          $ref: '#/definitions/holder'
      - in: query
        name: showDeleted
        description: Whether to include deleted ACLs in the result
      - in: query
        name: syncToken
        description: Token obtained from the nextSyncToken field returned on the last
          page of results from the previous list request
      responses:
        200:
          description: OK
      tags:
      - Calendar ACL
  /calendars/{calendarId}/acl/{ruleId}:
    delete:
      summary: Delete Calendar ACL
      description: Deletes an access control rule.
      operationId: calendar.acl.delete
      x-api-path-slug: calendarscalendaridaclruleid-delete
      parameters:
      - in: path
        name: calendarId
        description: Calendar identifier
      - in: path
        name: ruleId
        description: ACL rule identifier
      responses:
        200:
          description: OK
      tags:
      - Calendar ACL
    get:
      summary: Get Calendar ACL
      description: Returns an access control rule.
      operationId: calendar.acl.get
      x-api-path-slug: calendarscalendaridaclruleid-get
      parameters:
      - in: path
        name: calendarId
        description: Calendar identifier
      - in: path
        name: ruleId
        description: ACL rule identifier
      responses:
        200:
          description: OK
      tags:
      - Calendar ACL
    patch:
      summary: Update Calendar ACL
      description: Updates an access control rule. This method supports patch semantics.
      operationId: calendar.acl.patch
      x-api-path-slug: calendarscalendaridaclruleid-patch
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: calendarId
        description: Calendar identifier
      - in: path
        name: ruleId
        description: ACL rule identifier
      responses:
        200:
          description: OK
      tags:
      - Calendar ACL
    put:
      summary: Update Calendar ACL
      description: Updates an access control rule.
      operationId: calendar.acl.update
      x-api-path-slug: calendarscalendaridaclruleid-put
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: calendarId
        description: Calendar identifier
      - in: path
        name: ruleId
        description: ACL rule identifier
      responses:
        200:
          description: OK
      tags:
      - Calendar ACL
---