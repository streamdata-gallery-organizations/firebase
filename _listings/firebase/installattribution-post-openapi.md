---
swagger: "2.0"
x-collection-name: Firebase
x-complete: 0
info:
  title: Firebase Dynamic Links Post Installattribution
  description: Get iOS strong/weak-match info for post-install attribution.
  contact:
    name: Google
    url: https://google.com
  version: 1.0.0
host: firebasedynamiclinks-ipv6.googleapis.com
basePath: v1/
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /installAttribution:
    post:
      summary: Post Installattribution
      description: Get iOS strong/weak-match info for post-install attribution.
      operationId: firebasedynamiclinks.installAttribution
      x-api-path-slug: installattribution-post
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Dynammic
      - Links
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