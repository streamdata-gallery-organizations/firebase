---
swagger: "2.0"
x-collection-name: Firebase
x-complete: 0
info:
  title: Firebase Remote Config Put Project Remoteconfig
  description: |-
    Update a RemoteConfig. We treat this as an always-existing
    resource (when it is not found in our data store, we treat it as version
    0, a template with zero conditions and zero parameters). Hence there are
    no Create or Delete operations. Returns the updated template when
    successful (and the updated eTag as a response header), or an error if
    things go wrong.
    Possible error messages:
    * VALIDATION_ERROR (HTTP status 400) with additional details if the
    template being passed in can not be validated.
    * AUTHENTICATION_ERROR (HTTP status 401) if the request can not be
    authenticate (e.g. no access token, or invalid access token).
    * AUTHORIZATION_ERROR (HTTP status 403) if the request can not be
    authorized (e.g. the user has no access to the specified project id).
    * VERSION_MISMATCH (HTTP status 412) when trying to update when the
    expected eTag (passed in via the "If-match" header) is not specified, or
    is specified but does does not match the current eTag.
    * Internal error (HTTP status 500) for Database problems or other internal
    errors.
  termsOfService: https://developers.google.com/terms/
  contact:
    name: Google
    url: https://google.com
  version: 1.0.0
host: firebaseremoteconfig.googleapis.com
basePath: v1/
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /{project}/remoteConfig:
    get:
      summary: Get Project Remoteconfig
      description: |-
        Get the latest version Remote Configuration for a project.
        Returns the RemoteConfig as the payload, and also the eTag as a
        response header.
      operationId: getProjectRemoteconfig
      x-api-path-slug: projectremoteconfig-get
      parameters:
      - in: path
        name: project
        description: The GMP project identifier
      responses:
        200:
          description: OK
      tags:
      - Project
      - Remote
      - Config
    parameters:
      summary: Parameters Project Remoteconfig
      description: Parameters project remoteconfig.
      operationId: parametersProjectRemoteconfig
      x-api-path-slug: projectremoteconfig-parameters
      responses:
        200:
          description: OK
      tags:
      - Project
      - Remote
      - Config
    put:
      summary: Put Project Remoteconfig
      description: |-
        Update a RemoteConfig. We treat this as an always-existing
        resource (when it is not found in our data store, we treat it as version
        0, a template with zero conditions and zero parameters). Hence there are
        no Create or Delete operations. Returns the updated template when
        successful (and the updated eTag as a response header), or an error if
        things go wrong.
        Possible error messages:
        * VALIDATION_ERROR (HTTP status 400) with additional details if the
        template being passed in can not be validated.
        * AUTHENTICATION_ERROR (HTTP status 401) if the request can not be
        authenticate (e.g. no access token, or invalid access token).
        * AUTHORIZATION_ERROR (HTTP status 403) if the request can not be
        authorized (e.g. the user has no access to the specified project id).
        * VERSION_MISMATCH (HTTP status 412) when trying to update when the
        expected eTag (passed in via the "If-match" header) is not specified, or
        is specified but does does not match the current eTag.
        * Internal error (HTTP status 500) for Database problems or other internal
        errors.
      operationId: putProjectRemoteconfig
      x-api-path-slug: projectremoteconfig-put
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: project
        description: The GMP project identifier
      - in: query
        name: validateOnly
        description: Optional
      responses:
        200:
          description: OK
      tags:
      - Project
      - Remote
      - Config
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