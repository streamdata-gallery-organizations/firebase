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
  /{projectId}/histories/{historyId}/executions/{executionId}/steps/{stepId}:
    patch:
      summary: Update Execution Step
      description: Updates an existing Step with the supplied partial entity
      operationId: toolresults.projects.histories.executions.steps.patch
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: executionId
        description: A Execution id
      - in: path
        name: historyId
        description: A History id
      - in: path
        name: projectId
        description: A Project id
      - in: query
        name: requestId
        description: A unique request ID for server to detect duplicated requests
      - in: path
        name: stepId
        description: A Step id
      responses:
        200:
          description: OK
      tags:
      - execution step
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