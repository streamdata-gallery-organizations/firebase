---
swagger: "2.0"
x-collection-name: Firebase
x-complete: 0
info:
  title: Firebase Dynamic Links Post Shortlinks
  description: |-
    Creates a short Dynamic Link given either a valid long Dynamic Link or
    details such as Dynamic Link domain, Android and iOS app information.
    The created short Dynamic Link will not expire.

    Repeated calls with the same long Dynamic Link or Dynamic Link information
    will produce the same short Dynamic Link.

    The Dynamic Link domain in the request must be owned by requester's
    Firebase project.
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
  /managedShortLinks:create:
    post:
      summary: Post Managedshortlinks Create
      description: |-
        Creates a managed short Dynamic Link given either a valid long Dynamic Link
        or details such as Dynamic Link domain, Android and iOS app information.
        The created short Dynamic Link will not expire.

        This differs from CreateShortDynamicLink in the following ways:
          - The request will also contain a name for the link (non unique name
            for the front end).
          - The response must be authenticated with an auth token (generated with
            the admin service account).
          - The link will appear in the FDL list of links in the console front end.

        The Dynamic Link domain in the request must be owned by requester's
        Firebase project.
      operationId: firebasedynamiclinks.managedShortLinks.create
      x-api-path-slug: managedshortlinkscreate-post
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
  /shortLinks:
    post:
      summary: Post Shortlinks
      description: |-
        Creates a short Dynamic Link given either a valid long Dynamic Link or
        details such as Dynamic Link domain, Android and iOS app information.
        The created short Dynamic Link will not expire.

        Repeated calls with the same long Dynamic Link or Dynamic Link information
        will produce the same short Dynamic Link.

        The Dynamic Link domain in the request must be owned by requester's
        Firebase project.
      operationId: firebasedynamiclinks.shortLinks.create
      x-api-path-slug: shortlinks-post
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