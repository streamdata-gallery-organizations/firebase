---
swagger: "2.0"
x-collection-name: Firebase
x-complete: 0
info:
  title: Firebase Create Link
  description: |-
    Creates a short Dynamic Link given either a valid long Dynamic Link or
    details such as Dynamic Link domain, Android and iOS app information.
    The created short Dynamic Link will not expire.

    Repeated calls with the same long Dynamic Link or Dynamic Link information
    will produce the same short Dynamic Link.

    The Dynamic Link domain in the request must be owned by requester's
    Firebase project.
  version: 1.0.0
host: '{project_id].firebaseio.co}'
basePath: /
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /v1/shortLinks:
    post:
      summary: Create Link
      description: |-
        Creates a short Dynamic Link given either a valid long Dynamic Link or
        details such as Dynamic Link domain, Android and iOS app information.
        The created short Dynamic Link will not expire.

        Repeated calls with the same long Dynamic Link or Dynamic Link information
        will produce the same short Dynamic Link.

        The Dynamic Link domain in the request must be owned by requester's
        Firebase project.
      operationId: firebasedynamiclinks.shortLinks.create
      x-api-path-slug: v1shortlinks-post
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Shortened Link
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