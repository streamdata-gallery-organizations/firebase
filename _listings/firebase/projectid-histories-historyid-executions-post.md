---
swagger: "2.0"
info:
  title: Firebase
  version: 1.0.0
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /{projectId}/histories/{historyId}/executions:
    post:
      summary: Create Execution
      description: Creates an Execution
      operationId: toolresults.projects.histories.executions.create
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: historyId
        description: A History id
      - in: path
        name: projectId
        description: A Project id
      - in: query
        name: requestId
        description: A unique request ID for server to detect duplicated requests
      responses:
        200:
          description: OK
      tags:
      - execution
definitions: []
x-collection-name: Firebase
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