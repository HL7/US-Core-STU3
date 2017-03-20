-----------

`GET /MedicationRequest?patient={id}{&_include=MedicationStatement:medication}`

**Example:**

- GET [base]/MedicationRequest?patient=14676
- GET [base]/MedicationRequest?patient=14676&\_include=MedicationRequest:medication

*Support:* Mandatory for server and client to support search by patient.  Mandatory for client to support the `_include` parameter. Optional for server to support the `_include` parameter.

*Implementation Notes:*  This query searches for all MedicationRequest resources for a patient and returns a Bundle of all MedicationRequest resources for the specified patient. The server application represents the medication using either an inline code or a contained or external reference to the Medication resource.   [(how to search by reference)], and [(how to search by \_include)].

-----

  [(how to search by reference)]: http://hl7.org/fhir/STU3/search.html#reference
  [(how to search by token)]: http://hl7.org/fhir/STU3/search.html#token
  [Composite Search Parameters]: http://hl7.org/fhir/STU3/search.html#combining
  [(how to search by date)]: http://hl7.org/fhir/STU3/search.html#date
  [(how to search by _include)]: http://hl7.org/fhir/STU3/search.html#include
