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
  /{projectId}/settings:
    get:
      summary: Get Project Settings
      description: Gets the Tool Results settings for a project
      operationId: toolresults.projects.getSettings
      parameters:
      - in: path
        name: projectId
        description: A Project id
      responses:
        200:
          description: OK
      tags:
      - project
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