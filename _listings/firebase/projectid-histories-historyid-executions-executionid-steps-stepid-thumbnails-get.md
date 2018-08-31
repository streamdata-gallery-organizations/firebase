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
  /{projectId}/histories/{historyId}/executions/{executionId}/steps/{stepId}/thumbnails:
    get:
      summary: Get Thumbnails
      description: Lists thumbnails of images attached to a step
      operationId: toolresults.projects.histories.executions.steps.thumbnails.list
      parameters:
      - in: path
        name: executionId
        description: An Execution id
      - in: path
        name: historyId
        description: A History id
      - in: query
        name: pageSize
        description: The maximum number of thumbnails to fetch
      - in: query
        name: pageToken
        description: A continuation token to resume the query at the next item
      - in: path
        name: projectId
        description: A Project id
      - in: path
        name: stepId
        description: A Step id
      responses:
        200:
          description: OK
      tags:
      - thumbnail
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