---
swagger: "2.0"
x-collection-name: Firebase
x-complete: 0
info:
  title: Firebase Create Releases
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