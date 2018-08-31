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
  /{projectId}/histories:
    get:
      summary: List HIstories
      description: Lists Histories for a given Project
      operationId: toolresults.projects.histories.list
      parameters:
      - in: query
        name: filterByName
        description: If set, only return histories with the given name
      - in: query
        name: pageSize
        description: The maximum number of Histories to fetch
      - in: query
        name: pageToken
        description: A continuation token to resume the query at the next item
      - in: path
        name: projectId
        description: A Project id
      responses:
        200:
          description: OK
      tags:
      - history
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