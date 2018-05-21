---
swagger: "2.0"
x-collection-name: Firebase
x-complete: 0
info:
  title: Firebase Remote Config Parameters Project Remoteconfig
  description: Parameters project remoteconfig.
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