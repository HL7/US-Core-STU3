
`GET /MedicationStatement?patient={id}`

**Example:** GET [base]/MedicationStatement?patient=14676

*Support:* Mandatory for client to support search MedicationStatement by patient parameter.  Optional for server to support.

*Implementation Notes:*  Used when the server application represents the medication using either an inline code or a contained Medication resource. This searches for all MedicationStatement resources for a patient and returns a Bundle of all MedicationStatement resources for the specified patient.  [(how to search by reference)].

*Response Class:*

-   (Status 200): successful operation
-   (Status 400): invalid parameter
-   (Status 401/4xx): unauthorized request
-   (Status 403): insufficient scope

-----------

`GET /MedicationStatement?patient={id}&_include=MedicationStatement:medication`

**Example:** GET [base]/MedicationStatement?patient=14676&\_include=MedicationStatement:medication

*Support:* Mandatory for client to support search by patient and the include parameter.  Optional for server to support.

*Implementation Notes:*  Used when the server application represents the medication with an external reference to  a Medication resource. This searches for all MedicationStatement resources for a patient and returns a Bundle of all MedicationStatement and Medication resources for the specified patient.  [(how to search by reference)].

*Response Class:*

-   (Status 200): successful operation
-   (Status 400): invalid parameter
-   (Status 401/4xx): unauthorized request
-   (Status 403): insufficient scope

-------

  [(how to search by reference)]: http://build.fhir.org/search.html#reference
  [(how to search by token)]: http://build.fhir.org/search.html#token
  [Composite Search Parameters]: http://build.fhir.org/search.html#combining
  [(how to search by date)]: http://build.fhir.org/search.html#date
