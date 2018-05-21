---
name: Firebase
x-slug: firebase
description: Firebase is a mobile platform that helps you quicklydevelophigh-quality
  apps,growyour user base, andearnmore money. Firebase is made up of complementary
  features that you can mix-and-match to fit your needs.
image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/firebase-logo.png
x-kinRank: "9"
x-alexaRank: ""
tags: Firebase
created: "2018-05-21"
modified: "2018-05-21"
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
  humanURL: https://firebase.google.com/
  baseURL: https://{project_id].firebaseio.co}////v1/shortLinks
  tags: Shortened Link
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/firebase/master/_listings/firebase/v1shortlinks-post-openapi.md
- name: Firebase Delete Release
  x-api-slug: firebase
  description: Delete a `Release` by resource name.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/firebase-logo.png
  humanURL: https://firebase.google.com/
  baseURL: https://{project_id].firebaseio.co}////v1/{name}
  tags: Release
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/firebase/master/_listings/firebase/v1name-delete-openapi.md
- name: Firebase Get Release
  x-api-slug: firebase
  description: Get a `Release` by name.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/firebase-logo.png
  humanURL: https://firebase.google.com/
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
  humanURL: https://firebase.google.com/
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
  humanURL: https://firebase.google.com/
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
  humanURL: https://firebase.google.com/
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
  humanURL: https://firebase.google.com/
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
  humanURL: https://firebase.google.com/
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
  humanURL: https://firebase.google.com/
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
  humanURL: https://firebase.google.com/
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
  humanURL: https://firebase.google.com/
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
  humanURL: https://firebase.google.com/
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
  humanURL: https://firebase.google.com/
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
  humanURL: https://firebase.google.com/
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
  humanURL: https://firebase.google.com/
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
  humanURL: https://firebase.google.com/
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
  humanURL: https://firebase.google.com/
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
  humanURL: https://firebase.google.com/
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
  humanURL: https://firebase.google.com/
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
  humanURL: https://firebase.google.com/
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
  humanURL: https://firebase.google.com/
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
  humanURL: https://firebase.google.com/
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
  humanURL: https://firebase.google.com/
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
  humanURL: https://firebase.google.com/
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
  humanURL: https://firebase.google.com/
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
  humanURL: https://firebase.google.com/
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
  humanURL: https://firebase.google.com/
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
  humanURL: https://firebase.google.com/
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
  humanURL: https://firebase.google.com/
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
  humanURL: https://firebase.google.com/
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
  humanURL: https://firebase.google.com/
  baseURL: https://{project_id].firebaseio.co}////{projectId}:initializeSettings
  tags: Project
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/firebase/master/_listings/firebase/projectidinitializesettings-post-openapi.md
- name: Firebase
  x-api-slug: firebase
  description: Firebase is a mobile platform that helps you quicklydevelophigh-quality
    apps,growyour user base, andearnmore money. Firebase is made up of complementary
    features that you can mix-and-match to fit your needs.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/firebase-logo.png
  humanURL: https://firebase.google.com/
  baseURL: https://{project_id].firebaseio.co}//
  tags: Firebase
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/firebase/master/_listings/firebase/openapi.md
- name: Firebase Dynamic Links Post Installattribution
  x-api-slug: firebase-dynamic-links
  description: Get iOS strong/weak-match info for post-install attribution.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/firebase-logo.png
  humanURL: https://firebase.google.com/
  baseURL: https://firebasedynamiclinks-ipv6.googleapis.com/v1///installAttribution
  tags: Dynammic,Links
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/firebase/master/_listings/firebase/installattribution-post-openapi.md
- name: Firebase Dynamic Links Post Managedshortlinks Create
  x-api-slug: firebase-dynamic-links
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
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/firebase-logo.png
  humanURL: https://firebase.google.com/
  baseURL: https://firebasedynamiclinks-ipv6.googleapis.com/v1///managedShortLinks:create
  tags: Dynammic,Links
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/firebase/master/_listings/firebase/managedshortlinkscreate-post-openapi.md
- name: Firebase Dynamic Links Post Shortlinks
  x-api-slug: firebase-dynamic-links
  description: |-
    Creates a short Dynamic Link given either a valid long Dynamic Link or
    details such as Dynamic Link domain, Android and iOS app information.
    The created short Dynamic Link will not expire.

    Repeated calls with the same long Dynamic Link or Dynamic Link information
    will produce the same short Dynamic Link.

    The Dynamic Link domain in the request must be owned by requester's
    Firebase project.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/firebase-logo.png
  humanURL: https://firebase.google.com/
  baseURL: https://firebasedynamiclinks-ipv6.googleapis.com/v1///shortLinks
  tags: Dynammic,Links
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/firebase/master/_listings/firebase/shortlinks-post-openapi.md
- name: Firebase Dynamic Links Get Dynamiclink Linkstats
  x-api-slug: firebase-dynamic-links
  description: |-
    Fetches analytics stats of a short Dynamic Link for a given
    duration. Metrics include number of clicks, redirects, installs,
    app first opens, and app reopens.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/firebase-logo.png
  humanURL: https://firebase.google.com/
  baseURL: https://firebasedynamiclinks-ipv6.googleapis.com/v1///{dynamicLink}/linkStats
  tags: Dynammic,Links,Statistics
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/firebase/master/_listings/firebase/dynamiclinklinkstats-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/firebase/master/_listings/firebase/dynamiclinklinkstats-get-openapi.md
- name: Firebase Dynamic Links
  x-api-slug: firebase-dynamic-links
  description: Firebase is a mobile platform that helps you quicklydevelophigh-quality
    apps,growyour user base, andearnmore money. Firebase is made up of complementary
    features that you can mix-and-match to fit your needs.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/firebase-logo.png
  humanURL: https://firebase.google.com/
  baseURL: https://firebasedynamiclinks-ipv6.googleapis.com/v1/
  tags: Firebase
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/firebase/master/_listings/firebase/openapi.md
- name: Firebase Remote Config Get Project Remoteconfig
  x-api-slug: firebase-remote-config
  description: |-
    Get the latest version Remote Configuration for a project.
    Returns the RemoteConfig as the payload, and also the eTag as a
    response header.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/firebase-logo.png
  humanURL: https://firebase.google.com/
  baseURL: https://firebaseremoteconfig.googleapis.com/v1///{project}/remoteConfig
  tags: Project,Remote,Config
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/firebase/master/_listings/firebase/projectremoteconfig-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/firebase/master/_listings/firebase/projectremoteconfig-get-openapi.md
- name: Firebase Remote Config Parameters Project Remoteconfig
  x-api-slug: firebase-remote-config
  description: Parameters project remoteconfig.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/firebase-logo.png
  humanURL: https://firebase.google.com/
  baseURL: https://firebaseremoteconfig.googleapis.com/v1///{project}/remoteConfig
  tags: Project,Remote,Config
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/firebase/master/_listings/firebase/projectremoteconfig-parameters-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/firebase/master/_listings/firebase/projectremoteconfig-parameters-openapi.md
- name: Firebase Remote Config Put Project Remoteconfig
  x-api-slug: firebase-remote-config
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
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/firebase-logo.png
  humanURL: https://firebase.google.com/
  baseURL: https://firebaseremoteconfig.googleapis.com/v1///{project}/remoteConfig
  tags: Project,Remote,Config
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/firebase/master/_listings/firebase/projectremoteconfig-put-openapi.md
- name: Firebase Remote Config
  x-api-slug: firebase-remote-config
  description: Firebase is a mobile platform that helps you quicklydevelophigh-quality
    apps,growyour user base, andearnmore money. Firebase is made up of complementary
    features that you can mix-and-match to fit your needs.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/firebase-logo.png
  humanURL: https://firebase.google.com/
  baseURL: https://firebaseremoteconfig.googleapis.com/v1/
  tags: Firebase
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/firebase/master/_listings/firebase/openapi.md
- name: Firebase Rules Delete Name
  x-api-slug: firebase-rules
  description: Delete a `Release` by resource name.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/firebase-logo.png
  humanURL: https://firebase.google.com/
  baseURL: https://firebaserules.googleapis.com/v1///{name}
  tags: Name
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/firebase/master/_listings/firebase/name-delete-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/firebase/master/_listings/firebase/name-delete-openapi.md
- name: Firebase Rules Get Name
  x-api-slug: firebase-rules
  description: Get a `Release` by name.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/firebase-logo.png
  humanURL: https://firebase.google.com/
  baseURL: https://firebaserules.googleapis.com/v1///{name}
  tags: Name
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/firebase/master/_listings/firebase/name-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/firebase/master/_listings/firebase/name-get-openapi.md
- name: Firebase Rules Parameters Name
  x-api-slug: firebase-rules
  description: Parameters name.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/firebase-logo.png
  humanURL: https://firebase.google.com/
  baseURL: https://firebaserules.googleapis.com/v1///{name}
  tags: Name
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/firebase/master/_listings/firebase/name-parameters-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/firebase/master/_listings/firebase/name-parameters-openapi.md
- name: Firebase Rules Patch Name
  x-api-slug: firebase-rules
  description: |-
    Update a `Release` via PATCH.

    Only updates to the `ruleset_name` and `test_suite_name` fields will be
    honored. `Release` rename is not supported. To create a `Release` use the
    CreateRelease method.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/firebase-logo.png
  humanURL: https://firebase.google.com/
  baseURL: https://firebaserules.googleapis.com/v1///{name}
  tags: Name
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/firebase/master/_listings/firebase/name-patch-openapi.md
- name: Firebase Rules Get Name Releases
  x-api-slug: firebase-rules
  description: |-
    List the `Release` values for a project. This list may optionally be
    filtered by `Release` name, `Ruleset` name, `TestSuite` name, or any
    combination thereof.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/firebase-logo.png
  humanURL: https://firebase.google.com/
  baseURL: https://firebaserules.googleapis.com/v1///{name}/releases
  tags: Name,Releases
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/firebase/master/_listings/firebase/namereleases-get-openapi.md
- name: Firebase Rules Parameters Name Releases
  x-api-slug: firebase-rules
  description: Parameters name releases.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/firebase-logo.png
  humanURL: https://firebase.google.com/
  baseURL: https://firebaserules.googleapis.com/v1///{name}/releases
  tags: Name,Releases
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/firebase/master/_listings/firebase/namereleases-parameters-openapi.md
- name: Firebase Rules Post Name Releases
  x-api-slug: firebase-rules
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
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/firebase-logo.png
  humanURL: https://firebase.google.com/
  baseURL: https://firebaserules.googleapis.com/v1///{name}/releases
  tags: Name,Releases
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/firebase/master/_listings/firebase/namereleases-post-openapi.md
- name: Firebase Rules Get Name Rulesets
  x-api-slug: firebase-rules
  description: |-
    List `Ruleset` metadata only and optionally filter the results by `Ruleset`
    name.

    The full `Source` contents of a `Ruleset` may be retrieved with
    GetRuleset.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/firebase-logo.png
  humanURL: https://firebase.google.com/
  baseURL: https://firebaserules.googleapis.com/v1///{name}/rulesets
  tags: Name,Rulesets
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/firebase/master/_listings/firebase/namerulesets-get-openapi.md
- name: Firebase Rules Parameters Name Rulesets
  x-api-slug: firebase-rules
  description: Parameters name rulesets.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/firebase-logo.png
  humanURL: https://firebase.google.com/
  baseURL: https://firebaserules.googleapis.com/v1///{name}/rulesets
  tags: Name,Rulesets
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/firebase/master/_listings/firebase/namerulesets-parameters-openapi.md
- name: Firebase Rules Post Name Rulesets
  x-api-slug: firebase-rules
  description: |-
    Create a `Ruleset` from `Source`.

    The `Ruleset` is given a unique generated name which is returned to the
    caller. `Source` containing syntactic or semantics errors will result in an
    error response indicating the first error encountered. For a detailed view
    of `Source` issues, use TestRuleset.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/firebase-logo.png
  humanURL: https://firebase.google.com/
  baseURL: https://firebaserules.googleapis.com/v1///{name}/rulesets
  tags: Name,Rulesets
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/firebase/master/_listings/firebase/namerulesets-post-openapi.md
- name: Firebase Rules Get Name Getexecutable
  x-api-slug: firebase-rules
  description: Get the `Release` executable to use when enforcing rules.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/firebase-logo.png
  humanURL: https://firebase.google.com/
  baseURL: https://firebaserules.googleapis.com/v1///{name}:getExecutable
  tags: Names,Executables
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/firebase/master/_listings/firebase/namegetexecutable-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/firebase/master/_listings/firebase/namegetexecutable-get-openapi.md
- name: Firebase Rules Parameters Name Getexecutable
  x-api-slug: firebase-rules
  description: Parameters name getexecutable.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/firebase-logo.png
  humanURL: https://firebase.google.com/
  baseURL: https://firebaserules.googleapis.com/v1///{name}:getExecutable
  tags: Names,Executables
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/firebase/master/_listings/firebase/namegetexecutable-parameters-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/firebase/master/_listings/firebase/namegetexecutable-parameters-openapi.md
- name: Firebase Rules Parameters Name Test
  x-api-slug: firebase-rules
  description: Parameters name test.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/firebase-logo.png
  humanURL: https://firebase.google.com/
  baseURL: https://firebaserules.googleapis.com/v1///{name}:test
  tags: Names
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/firebase/master/_listings/firebase/nametest-parameters-openapi.md
- name: Firebase Rules Post Name Test
  x-api-slug: firebase-rules
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
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/firebase-logo.png
  humanURL: https://firebase.google.com/
  baseURL: https://firebaserules.googleapis.com/v1///{name}:test
  tags: Names
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/firebase/master/_listings/firebase/nametest-post-openapi.md
- name: Firebase Rules
  x-api-slug: firebase-rules
  description: Firebase is a mobile platform that helps you quicklydevelophigh-quality
    apps,growyour user base, andearnmore money. Firebase is made up of complementary
    features that you can mix-and-match to fit your needs.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/firebase-logo.png
  humanURL: https://firebase.google.com/
  baseURL: https://firebaserules.googleapis.com/v1/
  tags: Firebase
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/firebase/master/_listings/firebase/openapi.md
x-common:
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
  url: https://twitter.com/firebase
- type: x-website
  url: https://firebase.google.com/
include: []
maintainers:
- FN: Kin Lane
  x-twitter: apievangelist
  email: info@apievangelist.com
---