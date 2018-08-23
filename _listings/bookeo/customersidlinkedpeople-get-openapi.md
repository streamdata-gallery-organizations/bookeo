---
swagger: "2.0"
x-collection-name: Bookeo
x-complete: 0
info:
  title: Bookeo Get the people linked to a customer
  version: 1.0.0
  description: Get the people linked to a customer.
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
  /availability/matchingslots/{pageNavigationToken}:
    get:
      summary: Navigate results of a matching slots search
      description: Navigate results of a matching slots search.
      operationId: getAvailabilityMatchingslotsPagenavigationtoken
      x-api-path-slug: availabilitymatchingslotspagenavigationtoken-get
      parameters:
      - in: path
        name: pageNavigationToken
      - in: query
        name: pageNumber
      responses:
        200:
          description: OK
      tags:
      - Availability
      - Matchingslots
      - PageNavigationToken
  /availability/slots:
    get:
      summary: Get information about the availability of products
      description: |-
        Performs a basic search to find available slots and number of seats in each.
         Note that there are two different searches possible, /availability/slots (this endpoint) and /availability/matchingslots .
         The former simply shows the number of available seats for each available slot. The latter takes as input the participant numbers, and shows the slots that are available for those numbers, and an estimate of the price.
         /availability/slots cannot be used for products of type flexibleTime . For those products, use /availability/matchingslots .
      operationId: getAvailabilitySlots
      x-api-path-slug: availabilityslots-get
      parameters:
      - in: query
        name: endTime
        description: the end time to search to
      - in: query
        name: itemsPerPage
      - in: query
        name: pageNavigationToken
      - in: query
        name: pageNumber
      - in: query
        name: productId
        description: the product id (see /settings/products)
      - in: query
        name: startTime
        description: the start time to search from
      responses:
        200:
          description: OK
      tags:
      - Availability
      - Slots
  /bookings:
    get:
      summary: Retrieve bookings
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
      operationId: getBookings
      x-api-path-slug: bookings-get
      parameters:
      - in: query
        name: endTime
        description: if specified, only include bookings that start on or before this
          time
      - in: query
        name: expandCustomer
        description: if true, the full details of the customer are included (provided
          the application has read permission over the customer)
      - in: query
        name: expandParticipants
        description: if true, full details of the participants are included (provided
          the application has read permission over the participant)
      - in: query
        name: includeCanceled
        description: if true, canceled bookings are included
      - in: query
        name: itemsPerPage
        description: 'maximum: 100'
      - in: query
        name: lastUpdatedEndTime
        description: if specified, only include bookings that were last changed (or
          created) on or before this time
      - in: query
        name: lastUpdatedStartTime
        description: if specified, only include bookings that were last changed (or
          created) on or after this time
      - in: query
        name: pageNavigationToken
      - in: query
        name: pageNumber
      - in: query
        name: productId
        description: if not specified, include bookings for all products
      - in: query
        name: startTime
        description: if specified, only include bookings that start on or after this
          time
      responses:
        200:
          description: OK
      tags:
      - Bookings
    post:
      summary: Create a new booking
      description: |-
        When creating a booking for a product of type "fixed" or "fixedCourse", the eventId is required. eventIds are obtained by calling /availability/slots or /availability/matchingSlots .
         When creating a booking for a product of type "flexibleTime", you can either specify the eventId or the startTime (in which case you can optionally specify the endTime. If no endTime is specified, Bookeo will automatically calculate the duration based on the options chosen)
      operationId: postBookings
      x-api-path-slug: bookings-post
      parameters:
      - in: body
        name: booking
        schema:
          $ref: '#/definitions/holder'
      - in: query
        name: mode
        description: if present and set to backend, treats the operation as if it
          was done by a manager
      - in: query
        name: notifyCustomer
        description: whether to send a confirmation email to the customer
      - in: query
        name: notifyUsers
        description: whether to send a notification email (and possibly SMS, depending
          on settings) to eligible users
      - in: query
        name: previousHoldId
        description: if specified, deletes the hold with the given id
      - in: query
        name: sendCustomerReminders
      - in: query
        name: sendCustomerThankyou
      responses:
        200:
          description: OK
      tags:
      - Bookings
  /bookings/{bookingNumber}:
    get:
      summary: Retrieve a booking
      description: Retrieve a booking by its booking number
      operationId: getBookingsBookingnumber
      x-api-path-slug: bookingsbookingnumber-get
      parameters:
      - in: path
        name: bookingNumber
      - in: query
        name: expandCustomer
        description: if true, the full details of the customer are included (provided
          the application has read permission over the customer)
      - in: query
        name: expandParticipants
        description: if true, full details of the participants are included (provided
          the application has read permission over the participant)
      responses:
        200:
          description: OK
      tags:
      - Bookings
      - BookingNumber
    put:
      summary: Update an existing booking
      description: Update an existing booking.
      operationId: putBookingsBookingnumber
      x-api-path-slug: bookingsbookingnumber-put
      parameters:
      - in: body
        name: booking
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: bookingNumber
      - in: query
        name: mode
        description: if present and set to backend, treats the operation as if it
          was done by a manager
      - in: query
        name: notifyCustomer
      - in: query
        name: notifyUsers
      responses:
        200:
          description: OK
      tags:
      - Bookings
      - BookingNumber
    delete:
      summary: Cancel a booking
      description: Cancel a booking. Cancelled bookings remain in the system, but
        no longer show up in the calendar or take up seats.
      operationId: deleteBookingsBookingnumber
      x-api-path-slug: bookingsbookingnumber-delete
      parameters:
      - in: query
        name: applyCancellationPolicy
        description: if true, the default cancellation policy is applied
      - in: path
        name: bookingNumber
      - in: query
        name: cancelRemainingSeries
        description: if true, and this booking is part of a recurring series, all
          following bookings will be cancelled as well
      - in: query
        name: notifyCustomer
        description: if true, a notification email is sent to the customer
      - in: query
        name: notifyUsers
        description: if true, notification emails and SMS are sent to authorized users
      - in: query
        name: reason
        description: an optional reason that explains why the booking was cancelled
      - in: query
        name: trackInCustomerHistory
        description: if true, the cancellation will be tracked in the customers stats
      responses:
        200:
          description: OK
      tags:
      - Bookings
      - BookingNumber
  /bookings/{bookingNumber}/customer:
    get:
      summary: Retrieve the customer associated with a booking
      description: Retrieve the customer associated with a booking.
      operationId: getBookingsBookingnumberCustomer
      x-api-path-slug: bookingsbookingnumbercustomer-get
      parameters:
      - in: path
        name: bookingNumber
      responses:
        200:
          description: OK
      tags:
      - Bookings
      - BookingNumber
      - Customer
  /bookings/{bookingNumber}/payments:
    get:
      summary: Get the payments received for a booking
      description: Get a list of all payments received for a booking. Only payments
        for which the apiKey has at least read permission will be included
      operationId: getBookingsBookingnumberPayments
      x-api-path-slug: bookingsbookingnumberpayments-get
      parameters:
      - in: path
        name: bookingNumber
      - in: query
        name: itemsPerPage
      - in: query
        name: pageNavigationToken
      - in: query
        name: pageNumber
      responses:
        200:
          description: OK
      tags:
      - Bookings
      - BookingNumber
      - Payments
    post:
      summary: Add a payment to a booking
      description: Create a payment record associated with a booking
      operationId: postBookingsBookingnumberPayments
      x-api-path-slug: bookingsbookingnumberpayments-post
      parameters:
      - in: body
        name: apiPayment
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: bookingNumber
      responses:
        200:
          description: OK
      tags:
      - Bookings
      - BookingNumber
      - Payments
  /customers:
    get:
      summary: Retrieve customers
      description: Get a list of customers.
      operationId: getCustomers
      x-api-path-slug: customers-get
      parameters:
      - in: query
        name: createdSince
        description: if present, only include customers created since the given time
      - in: query
        name: currentMembers
        description: if true, include customers that are current members
      - in: query
        name: currentNonMembers
        description: if true, include customers that are not current members
      - in: query
        name: itemsPerPage
        description: number of items per page
      - in: query
        name: pageNavigationToken
        description: if present, continues navigation after a previous call
      - in: query
        name: pageNumber
      - in: query
        name: searchField
        description: a field on which to apply the search filter
      - in: query
        name: searchText
        description: the text to search for
      responses:
        200:
          description: OK
      tags:
      - Customers
    post:
      summary: Create a new customer.
      description: |-
        Create a new customer.
         Please note there is a limit to the number of customers that can be imported in Bookeo. Bookeo is primarily a booking system, not a CRM.
      operationId: postCustomers
      x-api-path-slug: customers-post
      parameters:
      - in: body
        name: customer
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Customers
  /customers/{customerid}/linkedpeople/{id}:
    get:
      summary: Retrieve a person linked to a customer
      description: Retrieve a person linked to a customer.
      operationId: getCustomersCustomerLinkedpeople
      x-api-path-slug: customerscustomeridlinkedpeopleid-get
      parameters:
      - in: path
        name: customerid
      - in: path
        name: id
      responses:
        200:
          description: OK
      tags:
      - Customers
      - Customerid
      - Linkedpeople
    put:
      summary: Update the details of a person linked to a customer
      description: Update the details of a person linked to a customer.
      operationId: putCustomersCustomerLinkedpeople
      x-api-path-slug: customerscustomeridlinkedpeopleid-put
      parameters:
      - in: body
        name: apiLinkedPerson
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: customerid
      - in: path
        name: id
      responses:
        200:
          description: OK
      tags:
      - Customers
      - Customerid
      - Linkedpeople
    delete:
      summary: Delete a person linked to a customer
      description: Delete a person linked to a customer.
      operationId: deleteCustomersCustomerLinkedpeople
      x-api-path-slug: customerscustomeridlinkedpeopleid-delete
      parameters:
      - in: path
        name: customerid
      - in: path
        name: id
      responses:
        200:
          description: OK
      tags:
      - Customers
      - Customerid
      - Linkedpeople
  /customers/{id}:
    get:
      summary: Retrieve a customer
      description: Retrieve a customer by its id
      operationId: getCustomers
      x-api-path-slug: customersid-get
      parameters:
      - in: path
        name: id
      responses:
        200:
          description: OK
      tags:
      - Customers
    put:
      summary: Update an existing customer
      description: Update an existing customer.
      operationId: putCustomers
      x-api-path-slug: customersid-put
      parameters:
      - in: body
        name: customer
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: id
      responses:
        200:
          description: OK
      tags:
      - Customers
    delete:
      summary: Delete a customer
      description: |-
        Delete a customer.
         Please note it is not possible to delete customers that have bookings in the future, and that are not cancelled.
         If your application needs to delete a customer with future bookings, make sure to cancel all future bookings for that customer first.
      operationId: deleteCustomers
      x-api-path-slug: customersid-delete
      parameters:
      - in: path
        name: id
      responses:
        200:
          description: OK
      tags:
      - Customers
  /customers/{id}/authenticate:
    get:
      summary: Check a customer's password
      description: |-
        The customer's email address is the "username" used by Bookeo to authenticate customers.
         So to authenticate a customer your application would typically use GET /customers to search for customers with a given email address, and then GET /customers/{id}/authenticate to authenticate.
         Remember that there may be duplicate customer records with the same email address, ex. due to duplicate importing or manual record creation.
      operationId: getCustomersAuthenticate
      x-api-path-slug: customersidauthenticate-get
      parameters:
      - in: path
        name: id
      - in: query
        name: password
        description: remember to use URL encoding
      responses:
        200:
          description: OK
      tags:
      - Customers
      - Authenticate
  /customers/{id}/bookings:
    get:
      summary: Retrieve a customer's bookings
      description: Retrieve a customer's bookings.
      operationId: getCustomersBookings
      x-api-path-slug: customersidbookings-get
      parameters:
      - in: query
        name: beginDate
        description: if specified, only bookings on or after this date will be included
      - in: query
        name: endDate
        description: if specified, only bookings on or before this date will be included
      - in: query
        name: expandParticipants
        description: if true, full details of the participants are included (provided
          the application has read permission over the participant)
      - in: path
        name: id
      - in: query
        name: itemsPerPage
      - in: query
        name: pageNavigationToken
      - in: query
        name: pageNumber
      responses:
        200:
          description: OK
      tags:
      - Customers
      - Bookings
  /customers/{id}/linkedpeople:
    get:
      summary: Get the people linked to a customer
      description: Get the people linked to a customer.
      operationId: getCustomersLinkedpeople
      x-api-path-slug: customersidlinkedpeople-get
      parameters:
      - in: path
        name: id
      - in: query
        name: itemsPerPage
        description: 'maximum: 100'
      - in: query
        name: pageNavigationToken
      - in: query
        name: pageNumber
      responses:
        200:
          description: OK
      tags:
      - Customers
      - Linkedpeople
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