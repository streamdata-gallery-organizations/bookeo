---
name: Bookeo
x-slug: bookeo
description: Bookeo provides a leading online booking and scheduling system for tours,
  classes, and appointments, to help you save money and time. Click to learn more!
image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28769-www-bookeo-com.jpg
x-kinRank: "7"
x-alexaRank: "23042"
tags: Bookeo
created: "2018-08-29"
modified: "2018-08-29"
url: https://raw.githubusercontent.com/streamdata-gallery-organizations/bookeo/master/_listings/bookeo/apis.md
specificationVersion: "0.14"
apis:
- name: Bookeo - Find available slots matching given search parameters
  x-api-slug: availabilitymatchingslots-post
  description: |-
    Create a search for available slots that match the given search parameters.
     Note that there are two different searches possible, /availability/slots and /availability/matchingslots (this endpoint).
     The former simply shows the number of available seats for each available slot. The latter (this one) takes as input the participant numbers, and shows the slots that are available for those numbers, and an estimate of the price.
     Parameters include product code, number of people and options.
     The successful response also contains a "Location" HTTP header, which can be invoked to navigate the results of the search.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28769-www-bookeo-com.jpg
  humanURL: https://www.bookeo.com
  baseURL: https://api.bookeo.com//v2
  tags: Bookings, Schedules, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/bookeo/master/_listings/bookeo/availabilitymatchingslots-post-openapi.md
- name: Bookeo - Navigate results of a matching slots search
  x-api-slug: availabilitymatchingslotspagenavigationtoken-get
  description: Navigate results of a matching slots search.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28769-www-bookeo-com.jpg
  humanURL: https://www.bookeo.com
  baseURL: https://api.bookeo.com//v2
  tags: Bookings, Schedules, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/bookeo/master/_listings/bookeo/availabilitymatchingslotspagenavigationtoken-get-openapi.md
- name: Bookeo - Get information about the availability of products
  x-api-slug: availabilityslots-get
  description: |-
    Performs a basic search to find available slots and number of seats in each.
     Note that there are two different searches possible, /availability/slots (this endpoint) and /availability/matchingslots .
     The former simply shows the number of available seats for each available slot. The latter takes as input the participant numbers, and shows the slots that are available for those numbers, and an estimate of the price.
     /availability/slots cannot be used for products of type flexibleTime . For those products, use /availability/matchingslots .
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28769-www-bookeo-com.jpg
  humanURL: https://www.bookeo.com
  baseURL: https://api.bookeo.com//v2
  tags: Bookings, Schedules, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/bookeo/master/_listings/bookeo/availabilityslots-get-openapi.md
- name: Bookeo - Retrieve bookings
  x-api-slug: bookings-get
  description: |-
    Retrieve existing bookings
     The result is limited by the permissions of the apiKey.
     <p/>
     It is possible to filter by time booked and/or time of the last change.
     To filter by time booked, the parameters startTime and endTime are required.
     To filter by last time changed, the parameters lastUpdatedStartTime and lastUpdatedEndTime are required.
     It is possible to filter by both at the same time. At least one of the two filters must be used.
     <p/>
     It is further possible to filter by product id.
     <p/>
     Do not use this method to periodically poll for new/changed bookings. Use webhooks (see API general documentation) instead.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28769-www-bookeo-com.jpg
  humanURL: https://www.bookeo.com
  baseURL: https://api.bookeo.com//v2
  tags: Bookings, Schedules, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/bookeo/master/_listings/bookeo/bookings-get-openapi.md
- name: Bookeo - Create a new booking
  x-api-slug: bookings-post
  description: |-
    When creating a booking for a product of type "fixed" or "fixedCourse", the eventId is required. eventIds are obtained by calling /availability/slots or /availability/matchingSlots .
     When creating a booking for a product of type "flexibleTime", you can either specify the eventId or the startTime (in which case you can optionally specify the endTime. If no endTime is specified, Bookeo will automatically calculate the duration based on the options chosen)
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28769-www-bookeo-com.jpg
  humanURL: https://www.bookeo.com
  baseURL: https://api.bookeo.com//v2
  tags: Bookings, Schedules, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/bookeo/master/_listings/bookeo/bookings-post-openapi.md
- name: Bookeo - Retrieve a booking
  x-api-slug: bookingsbookingnumber-get
  description: Retrieve a booking by its booking number
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28769-www-bookeo-com.jpg
  humanURL: https://www.bookeo.com
  baseURL: https://api.bookeo.com//v2
  tags: Bookings, Schedules, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/bookeo/master/_listings/bookeo/bookingsbookingnumber-get-openapi.md
- name: Bookeo - Update an existing booking
  x-api-slug: bookingsbookingnumber-put
  description: Update an existing booking.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28769-www-bookeo-com.jpg
  humanURL: https://www.bookeo.com
  baseURL: https://api.bookeo.com//v2
  tags: Bookings, Schedules, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/bookeo/master/_listings/bookeo/bookingsbookingnumber-put-openapi.md
- name: Bookeo - Cancel a booking
  x-api-slug: bookingsbookingnumber-delete
  description: Cancel a booking. Cancelled bookings remain in the system, but no longer
    show up in the calendar or take up seats.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28769-www-bookeo-com.jpg
  humanURL: https://www.bookeo.com
  baseURL: https://api.bookeo.com//v2
  tags: Bookings, Schedules, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/bookeo/master/_listings/bookeo/bookingsbookingnumber-delete-openapi.md
- name: Bookeo - Retrieve the customer associated with a booking
  x-api-slug: bookingsbookingnumbercustomer-get
  description: Retrieve the customer associated with a booking.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28769-www-bookeo-com.jpg
  humanURL: https://www.bookeo.com
  baseURL: https://api.bookeo.com//v2
  tags: Bookings, Schedules, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/bookeo/master/_listings/bookeo/bookingsbookingnumbercustomer-get-openapi.md
- name: Bookeo - Get the payments received for a booking
  x-api-slug: bookingsbookingnumberpayments-get
  description: Get a list of all payments received for a booking. Only payments for
    which the apiKey has at least read permission will be included
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28769-www-bookeo-com.jpg
  humanURL: https://www.bookeo.com
  baseURL: https://api.bookeo.com//v2
  tags: Bookings, Schedules, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/bookeo/master/_listings/bookeo/bookingsbookingnumberpayments-get-openapi.md
- name: Bookeo - Add a payment to a booking
  x-api-slug: bookingsbookingnumberpayments-post
  description: Create a payment record associated with a booking
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28769-www-bookeo-com.jpg
  humanURL: https://www.bookeo.com
  baseURL: https://api.bookeo.com//v2
  tags: Bookings, Schedules, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/bookeo/master/_listings/bookeo/bookingsbookingnumberpayments-post-openapi.md
- name: Bookeo - Retrieve customers
  x-api-slug: customers-get
  description: Get a list of customers.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28769-www-bookeo-com.jpg
  humanURL: https://www.bookeo.com
  baseURL: https://api.bookeo.com//v2
  tags: Bookings, Schedules, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/bookeo/master/_listings/bookeo/customers-get-openapi.md
- name: Bookeo - Create a new customer.
  x-api-slug: customers-post
  description: |-
    Create a new customer.
     Please note there is a limit to the number of customers that can be imported in Bookeo. Bookeo is primarily a booking system, not a CRM.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28769-www-bookeo-com.jpg
  humanURL: https://www.bookeo.com
  baseURL: https://api.bookeo.com//v2
  tags: Bookings, Schedules, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/bookeo/master/_listings/bookeo/customers-post-openapi.md
- name: Bookeo - Retrieve a person linked to a customer
  x-api-slug: customerscustomeridlinkedpeopleid-get
  description: Retrieve a person linked to a customer.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28769-www-bookeo-com.jpg
  humanURL: https://www.bookeo.com
  baseURL: https://api.bookeo.com//v2
  tags: Bookings, Schedules, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/bookeo/master/_listings/bookeo/customerscustomeridlinkedpeopleid-get-openapi.md
- name: Bookeo - Update the details of a person linked to a customer
  x-api-slug: customerscustomeridlinkedpeopleid-put
  description: Update the details of a person linked to a customer.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28769-www-bookeo-com.jpg
  humanURL: https://www.bookeo.com
  baseURL: https://api.bookeo.com//v2
  tags: Bookings, Schedules, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/bookeo/master/_listings/bookeo/customerscustomeridlinkedpeopleid-put-openapi.md
- name: Bookeo - Delete a person linked to a customer
  x-api-slug: customerscustomeridlinkedpeopleid-delete
  description: Delete a person linked to a customer.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28769-www-bookeo-com.jpg
  humanURL: https://www.bookeo.com
  baseURL: https://api.bookeo.com//v2
  tags: Bookings, Schedules, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/bookeo/master/_listings/bookeo/customerscustomeridlinkedpeopleid-delete-openapi.md
- name: Bookeo - Retrieve a customer
  x-api-slug: customersid-get
  description: Retrieve a customer by its id
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28769-www-bookeo-com.jpg
  humanURL: https://www.bookeo.com
  baseURL: https://api.bookeo.com//v2
  tags: Bookings, Schedules, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/bookeo/master/_listings/bookeo/customersid-get-openapi.md
- name: Bookeo - Update an existing customer
  x-api-slug: customersid-put
  description: Update an existing customer.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28769-www-bookeo-com.jpg
  humanURL: https://www.bookeo.com
  baseURL: https://api.bookeo.com//v2
  tags: Bookings, Schedules, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/bookeo/master/_listings/bookeo/customersid-put-openapi.md
- name: Bookeo - Delete a customer
  x-api-slug: customersid-delete
  description: |-
    Delete a customer.
     Please note it is not possible to delete customers that have bookings in the future, and that are not cancelled.
     If your application needs to delete a customer with future bookings, make sure to cancel all future bookings for that customer first.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28769-www-bookeo-com.jpg
  humanURL: https://www.bookeo.com
  baseURL: https://api.bookeo.com//v2
  tags: Bookings, Schedules, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/bookeo/master/_listings/bookeo/customersid-delete-openapi.md
- name: Bookeo - Check a customer's password
  x-api-slug: customersidauthenticate-get
  description: |-
    The customer's email address is the "username" used by Bookeo to authenticate customers.
     So to authenticate a customer your application would typically use GET /customers to search for customers with a given email address, and then GET /customers/{id}/authenticate to authenticate.
     Remember that there may be duplicate customer records with the same email address, ex. due to duplicate importing or manual record creation.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28769-www-bookeo-com.jpg
  humanURL: https://www.bookeo.com
  baseURL: https://api.bookeo.com//v2
  tags: Bookings, Schedules, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/bookeo/master/_listings/bookeo/customersidauthenticate-get-openapi.md
- name: Bookeo - Retrieve a customer's bookings
  x-api-slug: customersidbookings-get
  description: Retrieve a customer's bookings.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28769-www-bookeo-com.jpg
  humanURL: https://www.bookeo.com
  baseURL: https://api.bookeo.com//v2
  tags: Bookings, Schedules, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/bookeo/master/_listings/bookeo/customersidbookings-get-openapi.md
- name: Bookeo - Get the people linked to a customer
  x-api-slug: customersidlinkedpeople-get
  description: Get the people linked to a customer.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28769-www-bookeo-com.jpg
  humanURL: https://www.bookeo.com
  baseURL: https://api.bookeo.com//v2
  tags: Bookings, Schedules, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/bookeo/master/_listings/bookeo/customersidlinkedpeople-get-openapi.md
- name: Bookeo - Create a temporary hold to finalize the booking
  x-api-slug: holds-post
  description: |-
    Performs a final check of the booking, and reserves required resources/seats to allow finalization of the booking process (ex. process payment).
     The returned object also contains the updated price calculations.
     Normally your application should have no more than one hold in place during a customer booking process.
     Make sure to not leave many holds around. In any case, holds are deleted automatically after a fixed time from creation.
     Note that when creating a hold, the customer field of the booking can be missing, in which case Bookeo will assume a default customer coming from the same country as the account.
     The successful response also contains a "Location" HTTP header, which can be used to access the created resource in future invocations.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28769-www-bookeo-com.jpg
  humanURL: https://www.bookeo.com
  baseURL: https://api.bookeo.com//v2
  tags: Bookings, Schedules, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/bookeo/master/_listings/bookeo/holds-post-openapi.md
- name: Bookeo - Retrieve a hold previously generated
  x-api-slug: holdsid-get
  description: Retrieve a hold previously generated.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28769-www-bookeo-com.jpg
  humanURL: https://www.bookeo.com
  baseURL: https://api.bookeo.com//v2
  tags: Bookings, Schedules, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/bookeo/master/_listings/bookeo/holdsid-get-openapi.md
- name: Bookeo - Delete a temporary hold
  x-api-slug: holdsid-delete
  description: |-
    Delete a temporary hold previously created.
     Note that you can also delete a hold when creating a new hold (ex. when the customer goes back in the booking process and selects a different time), or when creating a booking (i.e. when the customer checks out), without having to make a separate call to this endpoint.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28769-www-bookeo-com.jpg
  humanURL: https://www.bookeo.com
  baseURL: https://api.bookeo.com//v2
  tags: Bookings, Schedules, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/bookeo/master/_listings/bookeo/holdsid-delete-openapi.md
- name: Bookeo - Get a list of payments received
  x-api-slug: payments-get
  description: Get a list of payments received.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28769-www-bookeo-com.jpg
  humanURL: https://www.bookeo.com
  baseURL: https://api.bookeo.com//v2
  tags: Bookings, Schedules, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/bookeo/master/_listings/bookeo/payments-get-openapi.md
- name: Bookeo - Retrieve a specific payment
  x-api-slug: paymentsid-get
  description: Retrieve a specific payment.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28769-www-bookeo-com.jpg
  humanURL: https://www.bookeo.com
  baseURL: https://api.bookeo.com//v2
  tags: Bookings, Schedules, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/bookeo/master/_listings/bookeo/paymentsid-get-openapi.md
- name: Bookeo - Retrieve resource blocks
  x-api-slug: resourceblocks-get
  description: |-
    Retrieve existing resource blocks
     The result is limited by the permissions of the apiKey.
     <p/>
     It is possible to filter by time blocked and/or time of the last change.
     To filter by time blocked, the parameters startTime and endTime are required.
     To filter by last time changed, the parameters lastUpdatedStartTime and lastUpdatedEndTime are required.
     It is possible to filter by both at the same time. At least one of the two filters must be used.
     <p/>
     It is further possible to filter by resource.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28769-www-bookeo-com.jpg
  humanURL: https://www.bookeo.com
  baseURL: https://api.bookeo.com//v2
  tags: Bookings, Schedules, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/bookeo/master/_listings/bookeo/resourceblocks-get-openapi.md
- name: Bookeo - Create a new resource block
  x-api-slug: resourceblocks-post
  description: |-
    "blocks" time for one or more resources, so that they're not available for booking.
     A resource block must be for at least one resource, but it can block more than one.
     When setting the resources in the block, only the id is required.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28769-www-bookeo-com.jpg
  humanURL: https://www.bookeo.com
  baseURL: https://api.bookeo.com//v2
  tags: Bookings, Schedules, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/bookeo/master/_listings/bookeo/resourceblocks-post-openapi.md
- name: Bookeo - Retrieve a block
  x-api-slug: resourceblocksid-get
  description: Retrieve a block by its id
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28769-www-bookeo-com.jpg
  humanURL: https://www.bookeo.com
  baseURL: https://api.bookeo.com//v2
  tags: Bookings, Schedules, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/bookeo/master/_listings/bookeo/resourceblocksid-get-openapi.md
- name: Bookeo - Update an existing block
  x-api-slug: resourceblocksid-put
  description: |-
    A resource block must be for at least one resource, but it can block more than one.
     When setting the resources in the block, only the id is required.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28769-www-bookeo-com.jpg
  humanURL: https://www.bookeo.com
  baseURL: https://api.bookeo.com//v2
  tags: Bookings, Schedules, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/bookeo/master/_listings/bookeo/resourceblocksid-put-openapi.md
- name: Bookeo - Delete a block
  x-api-slug: resourceblocksid-delete
  description: Delete a block.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28769-www-bookeo-com.jpg
  humanURL: https://www.bookeo.com
  baseURL: https://api.bookeo.com//v2
  tags: Bookings, Schedules, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/bookeo/master/_listings/bookeo/resourceblocksid-delete-openapi.md
- name: Bookeo - Retrieve seat blocks
  x-api-slug: seatblocks-get
  description: |-
    Retrieve existing seat blocks
     The result is limited by the permissions of the apiKey.
     <p/>
     It is possible to filter by time blocked and/or time of the last change.
     To filter by time blocked, the parameters startTime and endTime are required.
     To filter by last time changed, the parameters lastUpdatedStartTime and lastUpdatedEndTime are required.
     It is possible to filter by both at the same time. At least one of the two filters must be used.
     <p/>
     It is further possible to filter by product id.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28769-www-bookeo-com.jpg
  humanURL: https://www.bookeo.com
  baseURL: https://api.bookeo.com//v2
  tags: Bookings, Schedules, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/bookeo/master/_listings/bookeo/seatblocks-get-openapi.md
- name: Bookeo - Create a new seat block
  x-api-slug: seatblocks-post
  description: '"blocks" a given number of seats, so that they''re not available for
    booking.'
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28769-www-bookeo-com.jpg
  humanURL: https://www.bookeo.com
  baseURL: https://api.bookeo.com//v2
  tags: Bookings, Schedules, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/bookeo/master/_listings/bookeo/seatblocks-post-openapi.md
- name: Bookeo - Retrieve a block
  x-api-slug: seatblocksid-get
  description: Retrieve a block by its id
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28769-www-bookeo-com.jpg
  humanURL: https://www.bookeo.com
  baseURL: https://api.bookeo.com//v2
  tags: Bookings, Schedules, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/bookeo/master/_listings/bookeo/seatblocksid-get-openapi.md
- name: Bookeo - Update an existing block
  x-api-slug: seatblocksid-put
  description: Updates an existing seat block
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28769-www-bookeo-com.jpg
  humanURL: https://www.bookeo.com
  baseURL: https://api.bookeo.com//v2
  tags: Bookings, Schedules, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/bookeo/master/_listings/bookeo/seatblocksid-put-openapi.md
- name: Bookeo - Delete a block
  x-api-slug: seatblocksid-delete
  description: Delete a block.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28769-www-bookeo-com.jpg
  humanURL: https://www.bookeo.com
  baseURL: https://api.bookeo.com//v2
  tags: Bookings, Schedules, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/bookeo/master/_listings/bookeo/seatblocksid-delete-openapi.md
- name: Bookeo - Get information about your own API Key
  x-api-slug: settingsapikeyinfo-get
  description: Get information about your own api key.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28769-www-bookeo-com.jpg
  humanURL: https://www.bookeo.com
  baseURL: https://api.bookeo.com//v2
  tags: Bookings, Schedules, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/bookeo/master/_listings/bookeo/settingsapikeyinfo-get-openapi.md
- name: Bookeo - Get information, location and contact details about the business
  x-api-slug: settingsbusiness-get
  description: Get information, location and contact details about the business.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28769-www-bookeo-com.jpg
  humanURL: https://www.bookeo.com
  baseURL: https://api.bookeo.com//v2
  tags: Bookings, Schedules, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/bookeo/master/_listings/bookeo/settingsbusiness-get-openapi.md
- name: Bookeo - Retrieve all supported languages
  x-api-slug: settingslanguages-get
  description: Retrieve all supported languages.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28769-www-bookeo-com.jpg
  humanURL: https://www.bookeo.com
  baseURL: https://api.bookeo.com//v2
  tags: Bookings, Schedules, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/bookeo/master/_listings/bookeo/settingslanguages-get-openapi.md
- name: Bookeo - Retrieve all supported people categories
  x-api-slug: settingspeoplecategories-get
  description: |-
    Retrieve the people categories supported by this account.
     This can include the default ones ("Adults","Children","Infants") and also custom ones defined by the account ("Students", ...)
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28769-www-bookeo-com.jpg
  humanURL: https://www.bookeo.com
  baseURL: https://api.bookeo.com//v2
  tags: Bookings, Schedules, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/bookeo/master/_listings/bookeo/settingspeoplecategories-get-openapi.md
- name: Bookeo - Get information about the products offered
  x-api-slug: settingsproducts-get
  description: |-
    Get information about all the products (things that can be booked) offered.
     3 types of product are available:
     - fixed are products with a fixed schedule and a given number of seats. Ex a group tour, a class, a workshop
     - fixedCourse are fixed products that are defined as a course, i.e. comprise of a series of dates
     - flexibleTime are products that describe private appointments, i.e. when one booking uses one resource (teacher, consultant, etc)

     Although Bookeo applies a minimum amount of caching, it is recommended to cache these results for 10-15 minutes to improve the performance of your application, as product settings change rarely.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28769-www-bookeo-com.jpg
  humanURL: https://www.bookeo.com
  baseURL: https://api.bookeo.com//v2
  tags: Bookings, Schedules, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/bookeo/master/_listings/bookeo/settingsproducts-get-openapi.md
- name: Bookeo - Retrieve all available resources
  x-api-slug: settingsresources-get
  description: Retrieve all available resources.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28769-www-bookeo-com.jpg
  humanURL: https://www.bookeo.com
  baseURL: https://api.bookeo.com//v2
  tags: Bookings, Schedules, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/bookeo/master/_listings/bookeo/settingsresources-get-openapi.md
- name: Bookeo - Retrieve all taxes used by this business
  x-api-slug: settingstaxes-get
  description: Retrieve all taxes used by this business.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28769-www-bookeo-com.jpg
  humanURL: https://www.bookeo.com
  baseURL: https://api.bookeo.com//v2
  tags: Bookings, Schedules, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/bookeo/master/_listings/bookeo/settingstaxes-get-openapi.md
- name: Bookeo - List all subaccounts in the portal
  x-api-slug: subaccounts-get
  description: Retrieve all the webhooks for this api key
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28769-www-bookeo-com.jpg
  humanURL: https://www.bookeo.com
  baseURL: https://api.bookeo.com//v2
  tags: Bookings, Schedules, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/bookeo/master/_listings/bookeo/subaccounts-get-openapi.md
- name: Bookeo - Create a new API Key for this application to access a subaccount
  x-api-slug: subaccountssubaccountidapikeys-post
  description: |-
    Install this application in a subaccount.
     Note that the API key used in this call must be that of the portal manager account. The application installed in the subaccount will be the same as this one, with the same permissions.
     If this application was already installed in the subaccount, its API key will be replaced by the one created in this call.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28769-www-bookeo-com.jpg
  humanURL: https://www.bookeo.com
  baseURL: https://api.bookeo.com//v2
  tags: Bookings, Schedules, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/bookeo/master/_listings/bookeo/subaccountssubaccountidapikeys-post-openapi.md
- name: Bookeo - Delete the API Key for this application from a subaccount
  x-api-slug: subaccountssubaccountidapikeysapikey-delete
  description: Delete the api key for this application from a subaccount.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28769-www-bookeo-com.jpg
  humanURL: https://www.bookeo.com
  baseURL: https://api.bookeo.com//v2
  tags: Bookings, Schedules, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/bookeo/master/_listings/bookeo/subaccountssubaccountidapikeysapikey-delete-openapi.md
- name: Bookeo - List all webhooks
  x-api-slug: webhooks-get
  description: Retrieve all the webhooks for this api key
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28769-www-bookeo-com.jpg
  humanURL: https://www.bookeo.com
  baseURL: https://api.bookeo.com//v2
  tags: Bookings, Schedules, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/bookeo/master/_listings/bookeo/webhooks-get-openapi.md
- name: Bookeo - Create a new webhook
  x-api-slug: webhooks-post
  description: |-
    Note that if an existing webhook for the same domain and type was already set for this api key, it will be automatically replaced by this new webhook.
     In other words, there can be only one webhook for each combination of domain and type, for an API key.
     So to upgrade an existing webhook URL, simply create a new one with the same domain and type, but a different URL.

     For webhook with domain "bookings" and type "deleted", the notification will be sent whether the booking is canceled or completely deleted.
     Users can delete bookings by, for example, deleting their associated customer.
     Also note that these "bookings" "deleted" notifications are sent even for bookings in the past.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28769-www-bookeo-com.jpg
  humanURL: https://www.bookeo.com
  baseURL: https://api.bookeo.com//v2
  tags: Bookings, Schedules, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/bookeo/master/_listings/bookeo/webhooks-post-openapi.md
- name: Bookeo - Retrieve a webhook
  x-api-slug: webhookswebhookid-get
  description: Retrieve a webhook.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28769-www-bookeo-com.jpg
  humanURL: https://www.bookeo.com
  baseURL: https://api.bookeo.com//v2
  tags: Bookings, Schedules, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/bookeo/master/_listings/bookeo/webhookswebhookid-get-openapi.md
- name: Bookeo - Delete a webhook
  x-api-slug: webhookswebhookid-delete
  description: Delete a webhook.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28769-www-bookeo-com.jpg
  humanURL: https://www.bookeo.com
  baseURL: https://api.bookeo.com//v2
  tags: Bookings, Schedules, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/bookeo/master/_listings/bookeo/webhookswebhookid-delete-openapi.md
x-common:
- type: x-api-gallery
  url: http://bmc.software.api.gallery.streamdata.io
- type: x-api-stack
  url: http://bookeo.stack.network
- type: x-crunchbase
  url: https://crunchbase.com/organization/bookeo
- type: x-developer
  url: https://www.bookeo.com/api/
- type: x-documentation
  url: https://www.bookeo.com/apiref/index.html
- type: x-partners
  url: https://www.bookeo.com/affiliate/
- type: x-privacy-policy
  url: https://www.bookeo.com/privacy/
- type: x-terms-of-service
  url: https://www.bookeo.com/termsofservice/
- type: x-twitter
  url: https://twitter.com/bookeo
- type: x-webhook
  url: https://www.bookeo.com/api/webhooks/
- type: x-website
  url: https://www.bookeo.com
include: []
maintainers:
- FN: Kin Lane
  x-twitter: apievangelist
  email: info@apievangelist.com
---