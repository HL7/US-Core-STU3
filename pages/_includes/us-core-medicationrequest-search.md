-----------

`GET /MedicationRequest?patient={id}`

**Example:** GET [base]/MedicationRequest?patient=14676

*Support:* Mandatory for client to support search by patient.  Optional for server to support.

*Implementation Notes:*  Used when the server application represents the medication using either an inline code or a contained Medication resource. This searches for all MedicationRequest resources for a patient and returns a Bundle of all MedicationRequest resources for the specified patient.  [(how to search by reference)].


-----------

`GET /MedicationRequest?patient={id}&_include=MedicationRequest:medication`

**Example:** GET [base]/MedicationRequest?patient=14676&_include=MedicationRequest:medication

*Support:* Mandatory for client to support search by patient using the include parameter.  Optional for server to support.

*Implementation Notes:*  Used when the server application represents the medication with an external reference to  a Medication resource. This searches for all MedicationRequest resources for a patient and returns a Bundle of all MedicationRequest and Medication resources for the specified patient.  [(how to search by reference)].


-----

  [(how to search by reference)]: http://build.fhir.org/search.html#reference
  [(how to search by token)]: http://build.fhir.org/search.html#token
  [Composite Search Parameters]: http://build.fhir.org/search.html#combining
  [(how to search by date)]: http://build.fhir.org/search.html#date
