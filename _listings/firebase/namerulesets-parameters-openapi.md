---
swagger: "2.0"
x-collection-name: Firebase
x-complete: 0
info:
  title: Firebase Rules Parameters Name Rulesets
  description: Parameters name rulesets.
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
    parameters:
      summary: Parameters Name Releases
      description: Parameters name releases.
      operationId: parametersNameReleases
      x-api-path-slug: namereleases-parameters
      responses:
        200:
          description: OK
      tags:
      - Name
      - Releases
    post:
      summary: Post Name Releases
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
        updated using the UpdateRelease method.
      operationId: postNameReleases
      x-api-path-slug: namereleases-post
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
      - Releases
  /{name}/rulesets:
    get:
      summary: Get Name Rulesets
      description: |-
        List `Ruleset` metadata only and optionally filter the results by `Ruleset`
        name.

        The full `Source` contents of a `Ruleset` may be retrieved with
        GetRuleset.
      operationId: getNameRulesets
      x-api-path-slug: namerulesets-get
      parameters:
      - in: query
        name: filter
        description: '`Ruleset` filter'
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
      - Name
      - Rulesets
    parameters:
      summary: Parameters Name Rulesets
      description: Parameters name rulesets.
      operationId: parametersNameRulesets
      x-api-path-slug: namerulesets-parameters
      responses:
        200:
          description: OK
      tags:
      - Name
      - Rulesets
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