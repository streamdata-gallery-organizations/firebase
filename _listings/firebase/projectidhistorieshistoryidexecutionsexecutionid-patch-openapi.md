---
swagger: "2.0"
x-collection-name: Firebase
x-complete: 0
info:
  title: Firebase Update Execution
  description: |-
    Updates an existing Execution with the supplied partial entity.

    May return any of the following canonical error codes:

    - PERMISSION_DENIED - if the user is not authorized to write to project - INVALID_ARGUMENT - if the request is malformed - FAILED_PRECONDITION - if the requested state transition is illegal - NOT_FOUND - if the containing History does not exist
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
  /v1/{name}:
    delete:
      summary: Delete Release
      description: Delete a `Release` by resource name.
      operationId: firebaserules.projects.releases.delete
      x-api-path-slug: v1name-delete
      parameters:
      - in: path
        name: name
        description: Resource name for the `Release` to delete
      responses:
        200:
          description: OK
      tags:
      - Release
    get:
      summary: Get Release
      description: Get a `Release` by name.
      operationId: firebaserules.projects.releases.get
      x-api-path-slug: v1name-get
      parameters:
      - in: path
        name: name
        description: Resource name of the `Release`
      responses:
        200:
          description: OK
      tags:
      - Release
    put:
      summary: Update Release
      description: |-
        Update a `Release`.

        Only updates to the `ruleset_name` field will be honored. `Release` rename
        is not supported. To create a `Release` use the CreateRelease method
        instead.
      operationId: firebaserules.projects.releases.update
      x-api-path-slug: v1name-put
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: name
        description: Resource name for the `Release`
      responses:
        200:
          description: OK
      tags:
      - Release
  /v1/{name}/releases:
    get:
      summary: List Releases
      description: |-
        List the `Release` values for a project. This list may optionally be
        filtered by `Release` name or `Ruleset` id or both.
      operationId: firebaserules.projects.releases.list
      x-api-path-slug: v1namereleases-get
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
      - Release
    post:
      summary: Create Releases
      description: |-
        Create a `Release`.

        Release names should reflect the developer's deployment practices. For
        example, the release name may include the environment name, application
        name, application version, or any other name meaningful to the developer.
        Once a `Release` refers to a `Ruleset`, the rules can be enforced by
        Firebase Rules-enabled services.

        More than one `Release` may be 'live' concurrently. Consider the following
        three `Release` names for `projects/foo` and the `Ruleset` to which they
        refer.

        Release Name                    | Ruleset Name
        --------------------------------|-------------
        projects/foo/releases/prod      | projects/foo/rulesets/uuid123
        projects/foo/releases/prod/beta | projects/foo/rulesets/uuid123
        projects/foo/releases/prod/v23  | projects/foo/rulesets/uuid456

        The table reflects the `Ruleset` rollout in progress. The `prod` and
        `prod/beta` releases refer to the same `Ruleset`. However, `prod/v23`
        refers to a new `Ruleset`. The `Ruleset` reference for a `Release` may be
        updated using the UpdateRelease method, and the custom `Release` name
        may be referenced by specifying the `X-Firebase-Rules-Release-Name` header.
      operationId: firebaserules.projects.releases.create
      x-api-path-slug: v1namereleases-post
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
      - Release
  /v1/{name}/rulesets:
    get:
      summary: List Rules
      description: |-
        List `Ruleset` metadata only and optionally filter the results by Ruleset
        name.

        The full `Source` contents of a `Ruleset` may be retrieved with
        GetRuleset.
      operationId: firebaserules.projects.rulesets.list
      x-api-path-slug: v1namerulesets-get
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
      - Rules
    post:
      summary: Create Rules
      description: |-
        Create a `Ruleset` from `Source`.

        The `Ruleset` is given a unique generated name which is returned to the
        caller. `Source` containing syntactic or semantics errors will result in an
        error response indicating the first error encountered. For a detailed view
        of `Source` issues, use TestRuleset.
      operationId: firebaserules.projects.rulesets.create
      x-api-path-slug: v1namerulesets-post
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: name
        description: Resource name for Project which owns this `Ruleset`
      responses:
        200:
          description: OK
      tags:
      - Rules
  /v1/{name}:test:
    post:
      summary: Test  Rule
      description: |-
        Test `Source` for syntactic and semantic correctness. Issues present in the
        rules, if any, will be returned to the caller with a description, severity,
        and source location.

        The test method will typically be executed with a developer provided
        `Source`, but if regression testing is desired, this method may be
        executed against a `Ruleset` resource name and the `Source` will be
        retrieved from the persisted `Ruleset`.

        The following is an example of `Source` that permits users to upload images
        to a bucket bearing their user id and matching the correct metadata:

        _*Example*_

            // Users are allowed to subscribe and unsubscribe to the blog.
            service firebase.storage {
              match /users/{userId}/images/{imageName} {
                  allow write: if userId == request.userId
                      && (imageName.endsWith('.png') || imageName.endsWith('.jpg'))
                      && resource.mimeType.startsWith('image/')
              }
            }
      operationId: firebaserules.projects.test
      x-api-path-slug: v1nametest-post
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: name
        description: Name of the project
      responses:
        200:
          description: OK
      tags:
      - Rules
  /{projectId}/histories:
    get:
      summary: List HIstories
      description: |-
        Lists Histories for a given Project.

        The histories are sorted by modification time in descending order. The history_id key will be used to order the history with the same modification time.

        May return any of the following canonical error codes:

        - PERMISSION_DENIED - if the user is not authorized to read project - INVALID_ARGUMENT - if the request is malformed - NOT_FOUND - if the History does not exist
      operationId: toolresults.projects.histories.list
      x-api-path-slug: projectidhistories-get
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
      - History
    post:
      summary: Create History
      description: |-
        Creates a History.

        The returned History will have the id set.

        May return any of the following canonical error codes:

        - PERMISSION_DENIED - if the user is not authorized to write to project - INVALID_ARGUMENT - if the request is malformed - NOT_FOUND - if the containing project does not exist
      operationId: toolresults.projects.histories.create
      x-api-path-slug: projectidhistories-post
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: projectId
        description: A Project id
      - in: query
        name: requestId
        description: A unique request ID for server to detect duplicated requests
      responses:
        200:
          description: OK
      tags:
      - History
  /{projectId}/histories/{historyId}:
    get:
      summary: Get History
      description: |-
        Gets a History.

        May return any of the following canonical error codes:

        - PERMISSION_DENIED - if the user is not authorized to read project - INVALID_ARGUMENT - if the request is malformed - NOT_FOUND - if the History does not exist
      operationId: toolresults.projects.histories.get
      x-api-path-slug: projectidhistorieshistoryid-get
      parameters:
      - in: path
        name: historyId
        description: A History id
      - in: path
        name: projectId
        description: A Project id
      responses:
        200:
          description: OK
      tags:
      - History
  /{projectId}/histories/{historyId}/executions:
    get:
      summary: Get Executions
      description: |-
        Lists Histories for a given Project.

        The executions are sorted by creation_time in descending order. The execution_id key will be used to order the executions with the same creation_time.

        May return any of the following canonical error codes:

        - PERMISSION_DENIED - if the user is not authorized to read project - INVALID_ARGUMENT - if the request is malformed - NOT_FOUND - if the containing History does not exist
      operationId: toolresults.projects.histories.executions.list
      x-api-path-slug: projectidhistorieshistoryidexecutions-get
      parameters:
      - in: path
        name: historyId
        description: A History id
      - in: query
        name: pageSize
        description: The maximum number of Executions to fetch
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
      - History
    post:
      summary: Create Execution
      description: |-
        Creates an Execution.

        The returned Execution will have the id set.

        May return any of the following canonical error codes:

        - PERMISSION_DENIED - if the user is not authorized to write to project - INVALID_ARGUMENT - if the request is malformed - NOT_FOUND - if the containing History does not exist
      operationId: toolresults.projects.histories.executions.create
      x-api-path-slug: projectidhistorieshistoryidexecutions-post
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: historyId
        description: A History id
      - in: path
        name: projectId
        description: A Project id
      - in: query
        name: requestId
        description: A unique request ID for server to detect duplicated requests
      responses:
        200:
          description: OK
      tags:
      - Execution
  /{projectId}/histories/{historyId}/executions/{executionId}:
    get:
      summary: Get Execution
      description: |-
        Gets an Execution.

        May return any of the following canonical error codes:

        - PERMISSION_DENIED - if the user is not authorized to write to project - INVALID_ARGUMENT - if the request is malformed - NOT_FOUND - if the Execution does not exist
      operationId: toolresults.projects.histories.executions.get
      x-api-path-slug: projectidhistorieshistoryidexecutionsexecutionid-get
      parameters:
      - in: path
        name: executionId
        description: An Execution id
      - in: path
        name: historyId
        description: A History id
      - in: path
        name: projectId
        description: A Project id
      responses:
        200:
          description: OK
      tags:
      - Execution
    patch:
      summary: Update Execution
      description: |-
        Updates an existing Execution with the supplied partial entity.

        May return any of the following canonical error codes:

        - PERMISSION_DENIED - if the user is not authorized to write to project - INVALID_ARGUMENT - if the request is malformed - FAILED_PRECONDITION - if the requested state transition is illegal - NOT_FOUND - if the containing History does not exist
      operationId: toolresults.projects.histories.executions.patch
      x-api-path-slug: projectidhistorieshistoryidexecutionsexecutionid-patch
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: executionId
        description: Required
      - in: path
        name: historyId
        description: Required
      - in: path
        name: projectId
        description: A Project id
      - in: query
        name: requestId
        description: A unique request ID for server to detect duplicated requests
      responses:
        200:
          description: OK
      tags:
      - Execution
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