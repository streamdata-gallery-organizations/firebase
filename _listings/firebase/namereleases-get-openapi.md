---
swagger: "2.0"
x-collection-name: Firebase
x-complete: 0
info:
  title: Firebase Rules Get Name Releases
  description: |-
    List the `Release` values for a project. This list may optionally be
    filtered by `Release` name, `Ruleset` name, `TestSuite` name, or any
    combination thereof.
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
    patch:
      summary: Patch Name
      description: |-
        Update a `Release` via PATCH.

        Only updates to the `ruleset_name` and `test_suite_name` fields will be
        honored. `Release` rename is not supported. To create a `Release` use the
        CreateRelease method.
      operationId: patchName
      x-api-path-slug: name-patch
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: name
        description: Resource name for the project which owns this `Release`
      responses:
        200:
          description: OK
      tags:
      - Name
  /{name}/releases:
    get:
      summary: Get Name Releases
      description: |-
        List the `Release` values for a project. This list may optionally be
        filtered by `Release` name, `Ruleset` name, `TestSuite` name, or any
        combination thereof.
      operationId: getNameReleases
      x-api-path-slug: namereleases-get
      parameters:
      - in: query
        name: filter
        description: '`Release` filter'
      - in: path
        name: name
        description: Resource name for the project
      - in: query
        name: pageSize
        description: Page size to load
      - in: query
        name: pageToken
        description: Next page token for the next batch of `Release` instances
      responses:
        200:
          description: OK
      tags:
      - Name
      - Releases
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