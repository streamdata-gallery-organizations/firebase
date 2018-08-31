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
  /v1/{name}/rulesets:
    get:
      summary: List Rules
      description: |-
        List `Ruleset` metadata only and optionally filter the results by Ruleset
        name
      operationId: firebaserules.projects.rulesets.list
      parameters:
      - in: path
        name: name
        description: Resource name for the project
      - in: query
        name: pageSize
        description: Page size to load
      - in: query
        name: pageToken
        description: Next page token for loading the next batch of `Ruleset` instances
      responses:
        200:
          description: OK
      tags:
      - rules
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