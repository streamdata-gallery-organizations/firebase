---
name: Firebase
x-slug: firebase
description: Firebase is a mobile platform that gives developers the tools and infrastructure
  to build better apps and grow successful businesses.
image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/firebase-logo.png
x-kinRank: "9"
x-alexaRank: "1"
tags: Firebase
created: "2018-06-25"
modified: "2018-06-25"
url: https://raw.githubusercontent.com/streamdata-gallery-organizations/firebase/master/_listings/firebase/apis.md
specificationVersion: "0.14"
apis:
- name: Firebase Create Link
  x-api-slug: firebase
  description: |-
    Creates a short Dynamic Link given either a valid long Dynamic Link or
    details such as Dynamic Link domain, Android and iOS app information.
    The created short Dynamic Link will not expire.

    Repeated calls with the same long Dynamic Link or Dynamic Link information
    will produce the same short Dynamic Link.

    The Dynamic Link domain in the request must be owned by requester's
    Firebase project.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/firebase-logo.png
  humanURL: https://Firebase.google.com
  baseURL: https://{project_id].firebaseio.co}////v1/shortLinks
  tags: Shortened Link
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/firebase/master/_listings/firebase/v1shortlinks-post-openapi.md
- name: Firebase Delete Release
  x-api-slug: firebase
  description: Delete a `Release` by resource name.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/firebase-logo.png
  humanURL: https://Firebase.google.com
  baseURL: https://{project_id].firebaseio.co}////v1/{name}
  tags: Release
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/firebase/master/_listings/firebase/v1name-delete-openapi.md
- name: Firebase Get Release
  x-api-slug: firebase
  description: Get a `Release` by name.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/firebase-logo.png
  humanURL: https://Firebase.google.com
  baseURL: https://{project_id].firebaseio.co}////v1/{name}
  tags: Release
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/firebase/master/_listings/firebase/v1name-get-openapi.md
- name: Firebase Update Release
  x-api-slug: firebase
  description: |-
    Update a `Release`.

    Only updates to the `ruleset_name` field will be honored. `Release` rename
    is not supported. To create a `Release` use the CreateRelease method
    instead.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/firebase-logo.png
  humanURL: https://Firebase.google.com
  baseURL: https://{project_id].firebaseio.co}////v1/{name}
  tags: Release
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/firebase/master/_listings/firebase/v1name-put-openapi.md
- name: Firebase List Releases
  x-api-slug: firebase
  description: |-
    List the `Release` values for a project. This list may optionally be
    filtered by `Release` name or `Ruleset` id or both.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/firebase-logo.png
  humanURL: https://Firebase.google.com
  baseURL: https://{project_id].firebaseio.co}////v1/{name}/releases
  tags: Release
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/firebase/master/_listings/firebase/v1namereleases-get-openapi.md
- name: Firebase Create Releases
  x-api-slug: firebase
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
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/firebase-logo.png
  humanURL: https://Firebase.google.com
  baseURL: https://{project_id].firebaseio.co}////v1/{name}/releases
  tags: Release
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/firebase/master/_listings/firebase/v1namereleases-post-openapi.md
- name: Firebase List Rules
  x-api-slug: firebase
  description: |-
    List `Ruleset` metadata only and optionally filter the results by Ruleset
    name.

    The full `Source` contents of a `Ruleset` may be retrieved with
    GetRuleset.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/firebase-logo.png
  humanURL: https://Firebase.google.com
  baseURL: https://{project_id].firebaseio.co}////v1/{name}/rulesets
  tags: Rules
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/firebase/master/_listings/firebase/v1namerulesets-get-openapi.md
- name: Firebase Create Rules
  x-api-slug: firebase
  description: |-
    Create a `Ruleset` from `Source`.

    The `Ruleset` is given a unique generated name which is returned to the
    caller. `Source` containing syntactic or semantics errors will result in an
    error response indicating the first error encountered. For a detailed view
    of `Source` issues, use TestRuleset.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/firebase-logo.png
  humanURL: https://Firebase.google.com
  baseURL: https://{project_id].firebaseio.co}////v1/{name}/rulesets
  tags: Rules
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/firebase/master/_listings/firebase/v1namerulesets-post-openapi.md
- name: Firebase Test  Rule
  x-api-slug: firebase
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
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/firebase-logo.png
  humanURL: https://Firebase.google.com
  baseURL: https://{project_id].firebaseio.co}////v1/{name}:test
  tags: Rules
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/firebase/master/_listings/firebase/v1nametest-post-openapi.md
- name: Firebase List HIstories
  x-api-slug: firebase
  description: |-
    Lists Histories for a given Project.

    The histories are sorted by modification time in descending order. The history_id key will be used to order the history with the same modification time.

    May return any of the following canonical error codes:

    - PERMISSION_DENIED - if the user is not authorized to read project - INVALID_ARGUMENT - if the request is malformed - NOT_FOUND - if the History does not exist
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/firebase-logo.png
  humanURL: https://Firebase.google.com
  baseURL: https://{project_id].firebaseio.co}////{projectId}/histories
  tags: History
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/firebase/master/_listings/firebase/projectidhistories-get-openapi.md
- name: Firebase Create History
  x-api-slug: firebase
  description: |-
    Creates a History.

    The returned History will have the id set.

    May return any of the following canonical error codes:

    - PERMISSION_DENIED - if the user is not authorized to write to project - INVALID_ARGUMENT - if the request is malformed - NOT_FOUND - if the containing project does not exist
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/firebase-logo.png
  humanURL: https://Firebase.google.com
  baseURL: https://{project_id].firebaseio.co}////{projectId}/histories
  tags: History
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/firebase/master/_listings/firebase/projectidhistories-post-openapi.md
- name: Firebase Get History
  x-api-slug: firebase
  description: |-
    Gets a History.

    May return any of the following canonical error codes:

    - PERMISSION_DENIED - if the user is not authorized to read project - INVALID_ARGUMENT - if the request is malformed - NOT_FOUND - if the History does not exist
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/firebase-logo.png
  humanURL: https://Firebase.google.com
  baseURL: https://{project_id].firebaseio.co}////{projectId}/histories/{historyId}
  tags: History
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/firebase/master/_listings/firebase/projectidhistorieshistoryid-get-openapi.md
- name: Firebase Get Executions
  x-api-slug: firebase
  description: |-
    Lists Histories for a given Project.

    The executions are sorted by creation_time in descending order. The execution_id key will be used to order the executions with the same creation_time.

    May return any of the following canonical error codes:

    - PERMISSION_DENIED - if the user is not authorized to read project - INVALID_ARGUMENT - if the request is malformed - NOT_FOUND - if the containing History does not exist
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/firebase-logo.png
  humanURL: https://Firebase.google.com
  baseURL: https://{project_id].firebaseio.co}////{projectId}/histories/{historyId}/executions
  tags: History
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/firebase/master/_listings/firebase/projectidhistorieshistoryidexecutions-get-openapi.md
- name: Firebase Create Execution
  x-api-slug: firebase
  description: |-
    Creates an Execution.

    The returned Execution will have the id set.

    May return any of the following canonical error codes:

    - PERMISSION_DENIED - if the user is not authorized to write to project - INVALID_ARGUMENT - if the request is malformed - NOT_FOUND - if the containing History does not exist
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/firebase-logo.png
  humanURL: https://Firebase.google.com
  baseURL: https://{project_id].firebaseio.co}////{projectId}/histories/{historyId}/executions
  tags: Execution
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/firebase/master/_listings/firebase/projectidhistorieshistoryidexecutions-post-openapi.md
- name: Firebase Get Execution
  x-api-slug: firebase
  description: |-
    Gets an Execution.

    May return any of the following canonical error codes:

    - PERMISSION_DENIED - if the user is not authorized to write to project - INVALID_ARGUMENT - if the request is malformed - NOT_FOUND - if the Execution does not exist
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/firebase-logo.png
  humanURL: https://Firebase.google.com
  baseURL: https://{project_id].firebaseio.co}////{projectId}/histories/{historyId}/executions/{executionId}
  tags: Execution
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/firebase/master/_listings/firebase/projectidhistorieshistoryidexecutionsexecutionid-get-openapi.md
- name: Firebase Update Execution
  x-api-slug: firebase
  description: |-
    Updates an existing Execution with the supplied partial entity.

    May return any of the following canonical error codes:

    - PERMISSION_DENIED - if the user is not authorized to write to project - INVALID_ARGUMENT - if the request is malformed - FAILED_PRECONDITION - if the requested state transition is illegal - NOT_FOUND - if the containing History does not exist
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/firebase-logo.png
  humanURL: https://Firebase.google.com
  baseURL: https://{project_id].firebaseio.co}////{projectId}/histories/{historyId}/executions/{executionId}
  tags: Execution
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/firebase/master/_listings/firebase/projectidhistorieshistoryidexecutionsexecutionid-patch-openapi.md
- name: Firebase Get Execution Steps
  x-api-slug: firebase
  description: |-
    Lists Steps for a given Execution.

    The steps are sorted by creation_time in descending order. The step_id key will be used to order the steps with the same creation_time.

    May return any of the following canonical error codes:

    - PERMISSION_DENIED - if the user is not authorized to read project - INVALID_ARGUMENT - if the request is malformed - FAILED_PRECONDITION - if an argument in the request happens to be invalid; e.g. if an attempt is made to list the children of a nonexistent Step - NOT_FOUND - if the containing Execution does not exist
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/firebase-logo.png
  humanURL: https://Firebase.google.com
  baseURL: https://{project_id].firebaseio.co}////{projectId}/histories/{historyId}/executions/{executionId}/steps
  tags: Execution Step
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/firebase/master/_listings/firebase/projectidhistorieshistoryidexecutionsexecutionidsteps-get-openapi.md
- name: Firebase Create Execution Steps
  x-api-slug: firebase
  description: |-
    Creates a Step.

    The returned Step will have the id set.

    May return any of the following canonical error codes:

    - PERMISSION_DENIED - if the user is not authorized to write to project - INVALID_ARGUMENT - if the request is malformed - FAILED_PRECONDITION - if the step is too large (more than 10Mib) - NOT_FOUND - if the containing Execution does not exist
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/firebase-logo.png
  humanURL: https://Firebase.google.com
  baseURL: https://{project_id].firebaseio.co}////{projectId}/histories/{historyId}/executions/{executionId}/steps
  tags: Execution Step
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/firebase/master/_listings/firebase/projectidhistorieshistoryidexecutionsexecutionidsteps-post-openapi.md
- name: Firebase Get Execution Step
  x-api-slug: firebase
  description: |-
    Gets a Step.

    May return any of the following canonical error codes:

    - PERMISSION_DENIED - if the user is not authorized to read project - INVALID_ARGUMENT - if the request is malformed - NOT_FOUND - if the Step does not exist
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/firebase-logo.png
  humanURL: https://Firebase.google.com
  baseURL: https://{project_id].firebaseio.co}////{projectId}/histories/{historyId}/executions/{executionId}/steps/{stepId}
  tags: Execution Step
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/firebase/master/_listings/firebase/projectidhistorieshistoryidexecutionsexecutionidstepsstepid-get-openapi.md
- name: Firebase Update Execution Step
  x-api-slug: firebase
  description: |-
    Updates an existing Step with the supplied partial entity.

    May return any of the following canonical error codes:

    - PERMISSION_DENIED - if the user is not authorized to write project - INVALID_ARGUMENT - if the request is malformed - FAILED_PRECONDITION - if the requested state transition is illegal (e.g try to upload a duplicate xml file), if the updated step is too large (more than 10Mib) - NOT_FOUND - if the containing Execution does not exist
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/firebase-logo.png
  humanURL: https://Firebase.google.com
  baseURL: https://{project_id].firebaseio.co}////{projectId}/histories/{historyId}/executions/{executionId}/steps/{stepId}
  tags: Execution Step
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/firebase/master/_listings/firebase/projectidhistorieshistoryidexecutionsexecutionidstepsstepid-patch-openapi.md
- name: Firebase Get Metrics Summary
  x-api-slug: firebase
  description: |-
    Retrieves a PerfMetricsSummary.

    May return any of the following error code(s): - NOT_FOUND - The specified PerfMetricsSummary does not exist
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/firebase-logo.png
  humanURL: https://Firebase.google.com
  baseURL: https://{project_id].firebaseio.co}////{projectId}/histories/{historyId}/executions/{executionId}/steps/{stepId}/perfMetricsSummary
  tags: Metrics
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/firebase/master/_listings/firebase/projectidhistorieshistoryidexecutionsexecutionidstepsstepidperfmetricssummary-get-openapi.md
- name: Firebase Create Metric Summary
  x-api-slug: firebase
  description: |-
    Creates a PerfMetricsSummary resource.

    May return any of the following error code(s): - ALREADY_EXISTS - A PerfMetricSummary already exists for the given Step - NOT_FOUND - The containing Step does not exist
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/firebase-logo.png
  humanURL: https://Firebase.google.com
  baseURL: https://{project_id].firebaseio.co}////{projectId}/histories/{historyId}/executions/{executionId}/steps/{stepId}/perfMetricsSummary
  tags: Metrics
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/firebase/master/_listings/firebase/projectidhistorieshistoryidexecutionsexecutionidstepsstepidperfmetricssummary-post-openapi.md
- name: Firebase Get Sample Series
  x-api-slug: firebase
  description: |-
    Lists PerfSampleSeries for a given Step.

    The request provides an optional filter which specifies one or more PerfMetricsType to include in the result; if none returns all. The resulting PerfSampleSeries are sorted by ids.

    May return any of the following canonical error codes: - NOT_FOUND - The containing Step does not exist
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/firebase-logo.png
  humanURL: https://Firebase.google.com
  baseURL: https://{project_id].firebaseio.co}////{projectId}/histories/{historyId}/executions/{executionId}/steps/{stepId}/perfSampleSeries
  tags: Sample Series
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/firebase/master/_listings/firebase/projectidhistorieshistoryidexecutionsexecutionidstepsstepidperfsampleseries-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/firebase/master/_listings/firebase/projectidhistorieshistoryidexecutionsexecutionidstepsstepidperfsampleseries-get-openapi.md
- name: Firebase Create Sample Series
  x-api-slug: firebase
  description: |-
    Creates a PerfSampleSeries.

    May return any of the following error code(s): - ALREADY_EXISTS - PerfMetricSummary already exists for the given Step - NOT_FOUND - The containing Step does not exist
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/firebase-logo.png
  humanURL: https://Firebase.google.com
  baseURL: https://{project_id].firebaseio.co}////{projectId}/histories/{historyId}/executions/{executionId}/steps/{stepId}/perfSampleSeries
  tags: Sample Series
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/firebase/master/_listings/firebase/projectidhistorieshistoryidexecutionsexecutionidstepsstepidperfsampleseries-post-openapi.md
- name: Firebase Get Sample Series
  x-api-slug: firebase
  description: |-
    Gets a PerfSampleSeries.

    May return any of the following error code(s): - NOT_FOUND - The specified PerfSampleSeries does not exist
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/firebase-logo.png
  humanURL: https://Firebase.google.com
  baseURL: https://{project_id].firebaseio.co}////{projectId}/histories/{historyId}/executions/{executionId}/steps/{stepId}/perfSampleSeries/{sampleSeriesId}
  tags: Sample Series
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/firebase/master/_listings/firebase/projectidhistorieshistoryidexecutionsexecutionidstepsstepidperfsampleseriessampleseriesid-get-openapi.md
- name: Firebase Get Sample Series
  x-api-slug: firebase
  description: |-
    Lists the Performance Samples of a given Sample Series - The list results are sorted by timestamps ascending - The default page size is 500 samples; and maximum size allowed 5000 - The response token indicates the last returned PerfSample timestamp - When the results size exceeds the page size, submit a subsequent request including the page token to return the rest of the samples up to the page limit

    May return any of the following canonical error codes: - OUT_OF_RANGE - The specified request page_token is out of valid range - NOT_FOUND - The containing PerfSampleSeries does not exist
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/firebase-logo.png
  humanURL: https://Firebase.google.com
  baseURL: https://{project_id].firebaseio.co}////{projectId}/histories/{historyId}/executions/{executionId}/steps/{stepId}/perfSampleSeries/{sampleSeriesId}/samples
  tags: Sample Series
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/firebase/master/_listings/firebase/projectidhistorieshistoryidexecutionsexecutionidstepsstepidperfsampleseriessampleseriesidsamples-get-openapi.md
- name: Firebase Create Sample
  x-api-slug: firebase
  description: |-
    Creates a batch of PerfSamples - a client can submit multiple batches of Perf Samples through repeated calls to this method in order to split up a large request payload - duplicates and existing timestamp entries will be ignored. - the batch operation may partially succeed - the set of elements successfully inserted is returned in the response (omits items which already existed in the database).

    May return any of the following canonical error codes: - NOT_FOUND - The containing PerfSampleSeries does not exist
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/firebase-logo.png
  humanURL: https://Firebase.google.com
  baseURL: https://{project_id].firebaseio.co}////{projectId}/histories/{historyId}/executions/{executionId}/steps/{stepId}/perfSampleSeries/{sampleSeriesId}/samples:batchCreate
  tags: Sample Series
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/firebase/master/_listings/firebase/projectidhistorieshistoryidexecutionsexecutionidstepsstepidperfsampleseriessampleseriesidsamplesbatchcreate-post-openapi.md
- name: Firebase Get Thumbnails
  x-api-slug: firebase
  description: |-
    Lists thumbnails of images attached to a step.

    May return any of the following canonical error codes: - PERMISSION_DENIED - if the user is not authorized to read from the project, or from any of the images - INVALID_ARGUMENT - if the request is malformed - NOT_FOUND - if the step does not exist, or if any of the images do not exist
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/firebase-logo.png
  humanURL: https://Firebase.google.com
  baseURL: https://{project_id].firebaseio.co}////{projectId}/histories/{historyId}/executions/{executionId}/steps/{stepId}/thumbnails
  tags: Thumbnail
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/firebase/master/_listings/firebase/projectidhistorieshistoryidexecutionsexecutionidstepsstepidthumbnails-get-openapi.md
- name: Firebase Publish XML Files
  x-api-slug: firebase
  description: |-
    Publish xml files to an existing Step.

    May return any of the following canonical error codes:

    - PERMISSION_DENIED - if the user is not authorized to write project - INVALID_ARGUMENT - if the request is malformed - FAILED_PRECONDITION - if the requested state transition is illegal, e.g try to upload a duplicate xml file or a file too large. - NOT_FOUND - if the containing Execution does not exist
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/firebase-logo.png
  humanURL: https://Firebase.google.com
  baseURL: https://{project_id].firebaseio.co}////{projectId}/histories/{historyId}/executions/{executionId}/steps/{stepId}:publishXunitXmlFiles
  tags: XML File
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/firebase/master/_listings/firebase/projectidhistorieshistoryidexecutionsexecutionidstepsstepidpublishxunitxmlfiles-post-openapi.md
- name: Firebase Get Project Settings
  x-api-slug: firebase
  description: |-
    Gets the Tool Results settings for a project.

    May return any of the following canonical error codes:

    - PERMISSION_DENIED - if the user is not authorized to read from project
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/firebase-logo.png
  humanURL: https://Firebase.google.com
  baseURL: https://{project_id].firebaseio.co}////{projectId}/settings
  tags: Project
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/firebase/master/_listings/firebase/projectidsettings-get-openapi.md
- name: Firebase Initialize Settings
  x-api-slug: firebase
  description: |-
    Creates resources for settings which have not yet been set.

    Currently, this creates a single resource: a Google Cloud Storage bucket, to be used as the default bucket for this project. The bucket is created in the name of the user calling. Except in rare cases, calling this method in parallel from multiple clients will only create a single bucket. In order to avoid unnecessary storage charges, the bucket is configured to automatically delete objects older than 90 days.

    The bucket is created with the project-private ACL: All project team members are given permissions to the bucket and objects created within it according to their roles. Project owners have owners rights, and so on. The default ACL on objects created in the bucket is project-private as well. See Google Cloud Storage documentation for more details.

    If there is already a default bucket set and the project can access the bucket, this call does nothing. However, if the project doesn't have the permission to access the bucket or the bucket is deteleted, a new bucket will be created.

    May return any canonical error codes, including the following:

    - PERMISSION_DENIED - if the user is not authorized to write to project - Any error code raised by Google Cloud Storage
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/firebase-logo.png
  humanURL: https://Firebase.google.com
  baseURL: https://{project_id].firebaseio.co}////{projectId}:initializeSettings
  tags: Project
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/firebase/master/_listings/firebase/projectidinitializesettings-post-openapi.md
- name: Firebase
  x-api-slug: firebase
  description: Firebase is a mobile platform that gives developers the tools and infrastructure
    to build better apps and grow successful businesses.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/firebase-logo.png
  humanURL: https://Firebase.google.com
  baseURL: https://{project_id].firebaseio.co}//
  tags: Firebase
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/firebase/master/_listings/firebase/openapi.md
x-common:
- type: x-website
  url: https://Firebase.google.com
- type: x-blog
  url: https://firebase.googleblog.com/
- type: x-blog-rss
  url: http://firebase.googleblog.com/feeds/posts/default?alt=rss
- type: x-case-studies
  url: https://firebase.google.com/customers/
- type: x-change-log
  url: https://firebase.google.com/support/releases
- type: x-code
  url: https://firebase.google.com/docs/libraries/
- type: x-crunchbase
  url: https://crunchbase.com/organization/google
- type: x-documentation
  url: https://firebase.google.com/docs/
- type: x-faq
  url: https://firebase.google.com/support/faq/
- type: x-forum
  url: https://groups.google.com/forum/#!forum/firebase-talk
- type: x-github
  url: https://github.com/firebase
- type: x-pricing
  url: https://firebase.google.com/pricing/
- type: x-pricing
  url: https://adwords.google.com/home/pricing/
- type: x-slack
  url: https://firebase.community/
- type: x-submit-bug
  url: https://firebase.google.com/support/contact/bugs-features
- type: x-support
  url: https://firebase.google.com/support/
- type: x-twitter
  url: https://twitter.com/Google
- type: x-twitter
  url: https://twitter.com/firebase
- type: x-website
  url: https://firebase.google.com/
include: []
maintainers:
- FN: Kin Lane
  x-twitter: apievangelist
  email: info@apievangelist.com
---