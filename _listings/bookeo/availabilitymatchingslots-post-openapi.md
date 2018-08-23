---
swagger: "2.0"
x-collection-name: Bookeo
x-complete: 0
info:
  title: Bookeo Find available slots matching given search parameters
  version: 1.0.0
  description: |-
    Create a search for available slots that match the given search parameters.
     Note that there are two different searches possible, /availability/slots and /availability/matchingslots (this endpoint).
     The former simply shows the number of available seats for each available slot. The latter (this one) takes as input the participant numbers, and shows the slots that are available for those numbers, and an estimate of the price.
     Parameters include product code, number of people and options.
     The successful response also contains a "Location" HTTP header, which can be invoked to navigate the results of the search.
host: api.bookeo.com
basePath: /v2
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /availability/matchingslots:
    post:
      summary: Find available slots matching given search parameters
      description: |-
        Create a search for available slots that match the given search parameters.
         Note that there are two different searches possible, /availability/slots and /availability/matchingslots (this endpoint).
         The former simply shows the number of available seats for each available slot. The latter (this one) takes as input the participant numbers, and shows the slots that are available for those numbers, and an estimate of the price.
         Parameters include product code, number of people and options.
         The successful response also contains a "Location" HTTP header, which can be invoked to navigate the results of the search.
      operationId: postAvailabilityMatchingslots
      x-api-path-slug: availabilitymatchingslots-post
      parameters:
      - in: query
        name: itemsPerPage
      - in: body
        name: search
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Availability
      - Matchingslots
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