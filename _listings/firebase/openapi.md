---
swagger: "2.0"
x-collection-name: Firebase
x-complete: 1
info:
  title: Firebase Rules
  description: creates-and-manages-rules-that-determine-when-a-firebase-rulesenabled-service-should-permit-a-request
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
    post:
      summary: Post Name Rulesets
      description: |-
        Create a `Ruleset` from `Source`.

        The `Ruleset` is given a unique generated name which is returned to the
        caller. `Source` containing syntactic or semantics errors will result in an
        error response indicating the first error encountered. For a detailed view
        of `Source` issues, use TestRuleset.
      operationId: postNameRulesets
      x-api-path-slug: namerulesets-post
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
      - Name
      - Rulesets
  /{name}:getExecutable:
    get:
      summary: Get Name Getexecutable
      description: Get the `Release` executable to use when enforcing rules.
      operationId: getNameGetexecutable
      x-api-path-slug: namegetexecutable-get
      parameters:
      - in: query
        name: executableVersion
        description: The requested runtime executable version
      - in: path
        name: name
        description: Resource name of the `Release`
      responses:
        200:
          description: OK
      tags:
      - Names
      - Executables
    parameters:
      summary: Parameters Name Getexecutable
      description: Parameters name getexecutable.
      operationId: parametersNameGetexecutable
      x-api-path-slug: namegetexecutable-parameters
      responses:
        200:
          description: OK
      tags:
      - Names
      - Executables
  /{name}:test:
    parameters:
      summary: Parameters Name Test
      description: Parameters name test.
      operationId: parametersNameTest
      x-api-path-slug: nametest-parameters
      responses:
        200:
          description: OK
      tags:
      - Names
    post:
      summary: Post Name Test
      description: |-
        Test `Source` for syntactic and semantic correctness. Issues present, if
        any, will be returned to the caller with a description, severity, and
        source location.

        The test method may be executed with `Source` or a `Ruleset` name.
        Passing `Source` is useful for unit testing new rules. Passing a `Ruleset`
        name is useful for regression testing an existing rule.

        The following is an example of `Source` that permits users to upload images
        to a bucket bearing their user id and matching the correct metadata:

        _*Example*_

            // Users are allowed to subscribe and unsubscribe to the blog.
            service firebase.storage {
              match /users/{userId}/images/{imageName} {
                  allow write: if userId == request.auth.uid
                      && (imageName.matches('*.png$')
                      || imageName.matches('*.jpg$'))
                      && resource.mimeType.matches('^image/')
              }
            }
      operationId: postNameTest
      x-api-path-slug: nametest-post
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: name
        description: Tests may either provide `source` or a `Ruleset` resource name
      responses:
        200:
          description: OK
      tags:
      - Names
---