
`GET /Goal?patient=[id]`

**Example:** GET [base]/Goal?patient=1137192

*Support:* Mandatory to support search by patient.

*Implementation Notes:* Search for all goals for a patient. Fetches a bundle of all Goal resources for the specified patient. [(how to search by reference)].


*Response Class:*

-   (Status 200): successful operation
-   (Status 400): invalid parameter
-   (Status 401/4xx): unauthorized request
-   (Status 403): insufficient scope

-----------

`GET /Goal?patient=[id]&date=[date]{&date=[date]}[edit]`

**Example:**

- GET [base]/Goal?patient=1137192&date=ge2015-01-14
- GET [base]/Goal?patient=1137192&date=ge2015-01-14&date=le2016-01-14

*Support:* Mandatory to support search by date.

*Implementation Notes:* Search for all goals for a patient within a time period. Fetches a bundle of all Goal resources for the specified patient with a specified time period. [(how to search by reference)] and [(how to search by date)].

*Response Class:*

-   (Status 200): successful operation
-   (Status 400): invalid parameter
-   (Status 401/4xx): unauthorized request
-   (Status 403): insufficient scope


  [(how to search by reference)]: http://build.fhir.org/search.html#reference
  [(how to search by token)]: http://build.fhir.org/search.html#token
  [Composite Search Parameters]: http://build.fhir.org/search.html#combining
  [(how to search by date)]: http://build.fhir.org/search.html#date
