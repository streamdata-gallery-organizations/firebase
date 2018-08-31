---
swagger: "2.0"
info:
  title: Firebase
  version: 1.0.0
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /{projectId}/histories/{historyId}/executions/{executionId}/steps/{stepId}/perfSampleSeries/{sampleSeriesId}/samples:batchCreate:
    post:
      summary: Create Sample
      description: Creates a batch of PerfSamples - a client can submit multiple batches
        of Perf Samples through repeated calls to this method in order to split up
        a large request payload - duplicates and existing timestamp entries will be
        ignored
      operationId: toolresults.projects.histories.executions.steps.perfSampleSeries.samples.batchCreate
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: executionId
        description: A tool results execution ID
      - in: path
        name: historyId
        description: A tool results history ID
      - in: path
        name: projectId
        description: The cloud project
      - in: path
        name: sampleSeriesId
        description: A sample series id
      - in: path
        name: stepId
        description: A tool results step ID
      responses:
        200:
          description: OK
      tags:
      - sample series
definitions: []
x-collection-name: Firebase
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