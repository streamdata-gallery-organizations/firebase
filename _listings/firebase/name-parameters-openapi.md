---
swagger: "2.0"
x-collection-name: Firebase
x-complete: 0
info:
  title: Firebase Rules Parameters Name
  description: Parameters name.
  contact:
    name: Google
    url: https://google.com
  version: 1.0.0
host: firebaserules.googleapis.com
basePath: v1/
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /{name}:
    delete:
      summary: Delete Name
      description: Delete a `Release` by resource name.
      operationId: deleteName
      x-api-path-slug: name-delete
      parameters:
      - in: path
        name: name
        description: Resource name for the `Release` to delete
      responses:
        200:
          description: OK
      tags:
      - Name
    get:
      summary: Get Name
      description: Get a `Release` by name.
      operationId: getName
      x-api-path-slug: name-get
      parameters:
      - in: path
        name: name
        description: Resource name of the `Release`
      responses:
        200:
          description: OK
      tags:
      - Name
    parameters:
      summary: Parameters Name
      description: Parameters name.
      operationId: parametersName
      x-api-path-slug: name-parameters
      responses:
        200:
          description: OK
      tags:
      - Name
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