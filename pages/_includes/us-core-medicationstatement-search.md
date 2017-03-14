
`GET /MedicationStatement?patient={id}{&_include=MedicationStatement:medication}`

**Example:**

- GET [base]/MedicationStatement?patient=14676
- GET [base]/MedicationStatement?patient=14676&\_include=MedicationStatement:medication

*Support:* Mandatory for server and client to support search by patient.  Mandatory for client to support the `_include` parameter. Optional for server to support the `_include` parameter.

*Implementation Notes:*  This query searches for all MedicationStatement resources for a patient and returns a Bundle of all MedicationStatement resources for the specified patient. The server application represents the medication using either an inline code or a contained or external reference to the Medication resource.   [(how to search by reference)], and [(how to search by \_include)].

-------

  [(how to search by reference)]: http://build.fhir.org/search.html#reference
  [(how to search by token)]: http://build.fhir.org/search.html#token
  [Composite Search Parameters]: http://build.fhir.org/search.html#combining
  [(how to search by date)]: http://build.fhir.org/search.html#date
  [(how to search by _include)]: http://build.fhir.org/search.html#include
