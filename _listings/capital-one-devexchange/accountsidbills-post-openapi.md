---
swagger: "2.0"
x-collection-name: Capital One DevExchange
x-complete: 0
info:
  title: Capital One DevExchange Create a bill
  description: Creates a bill for the specific account
  version: 1.0.0
host: api.reimaginebanking.com
basePath: /
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /accounts:
    get:
      summary: Get all accounts
      description: Returns the accounts that have been assigned to you.
      operationId: returns-the-accounts-that-have-been-assigned-to-you
      x-api-path-slug: accounts-get
      parameters:
      - in: query
        name: type
        description: Empty Param will return all types of accounts
      responses:
        200:
          description: OK
      tags:
      - Banks
      - Accounts
  /accounts/{id}:
    get:
      summary: Get account by id
      description: Returns the account with the specific id
      operationId: returns-the-account-with-the-specific-id
      x-api-path-slug: accountsid-get
      parameters:
      - in: path
        name: id
        description: ID of account that needs to be fetched
      responses:
        200:
          description: OK
      tags:
      - Banks
      - Accounts
    put:
      summary: Update a specific existing account
      description: Updates the specific account
      operationId: updates-the-specific-account
      x-api-path-slug: accountsid-put
      parameters:
      - in: body
        name: body
        description: Updated account object
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: id
        description: ID of account that needs to be fetched
      responses:
        200:
          description: OK
      tags:
      - Banks
      - Accounts
    delete:
      summary: Delete a specific existing account
      description: Deletes the specific account
      operationId: deletes-the-specific-account
      x-api-path-slug: accountsid-delete
      parameters:
      - in: path
        name: id
        description: ID of account that needs to be fetched
      responses:
        200:
          description: OK
      tags:
      - Banks
      - Accounts
  /customers/{id}/accounts:
    post:
      summary: Create an account
      description: Creates an account for the customer with the id provided
      operationId: creates-an-account-for-the-customer-with-the-id-provided
      x-api-path-slug: customersidaccounts-post
      parameters:
      - in: body
        name: body
        description: Account to be created
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: id
        description: ID of customer that account will belong to
      responses:
        200:
          description: OK
      tags:
      - Banks
      - Customers
      - ""
      - Accounts
    get:
      summary: Get accounts by customer id
      description: Returns the accounts associated with the specific customer
      operationId: returns-the-accounts-associated-with-the-specific-customer
      x-api-path-slug: customersidaccounts-get
      parameters:
      - in: path
        name: id
        description: ID of customer to fetch accounts for
      responses:
        200:
          description: OK
      tags:
      - Banks
      - Customers
      - ""
      - Accounts
  /accounts/{id}/customer:
    get:
      summary: Get customer that owns the specified account
      description: Returns the customer that the account belongs to.
      operationId: returns-the-customer-that-the-account-belongs-to
      x-api-path-slug: accountsidcustomer-get
      parameters:
      - in: path
        name: id
        description: ID of customer that account will belong to
      responses:
        200:
          description: OK
      tags:
      - Banks
      - Accounts
      - ""
      - Customer
  /atms:
    get:
      summary: Get all ATMs
      description: Returns all of the Capital One ATMs in the speified search area.
      operationId: returns-all-of-the-capital-one-atms-in-the-speified-search-area
      x-api-path-slug: atms-get
      parameters:
      - in: query
        name: lat
        description: Latitude of where youre looking for an ATM
      - in: query
        name: lng
        description: Longitude of where youre looking for an ATM
      - in: query
        name: rad
        description: Search radius in miles
      responses:
        200:
          description: OK
      tags:
      - Banks
      - Atms
  /atms/{id}:
    get:
      summary: Get ATM by id
      description: Returns the ATM with the specific id
      operationId: returns-the-atm-with-the-specific-id
      x-api-path-slug: atmsid-get
      parameters:
      - in: path
        name: id
        description: ID of ATM that needs to be fetched
      responses:
        200:
          description: OK
      tags:
      - Banks
      - Atms
  /accounts/{id}/bills:
    get:
      summary: Get all bills for a specific account
      description: Returns the bills that are tied to the specific account.
      operationId: returns-the-bills-that-are-tied-to-the-specific-account
      x-api-path-slug: accountsidbills-get
      parameters:
      - in: path
        name: id
        description: ID of account to fetch bills for
      responses:
        200:
          description: OK
      tags:
      - Banks
      - Accounts
      - ""
      - Bills
    post:
      summary: Create a bill
      description: Creates a bill for the specific account
      operationId: creates-a-bill-for-the-specific-account
      x-api-path-slug: accountsidbills-post
      parameters:
      - in: body
        name: body
        description: Bill to be created
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: id
        description: ID of account that the bill will belong to
      responses:
        200:
          description: OK
      tags:
      - Banks
      - Accounts
      - ""
      - Bills
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