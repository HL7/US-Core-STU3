
`GET /Device?patient=[id]`

**Example:** GET [base]/Device?patient=1032702


*Support:* Mandatory to support search by patient.

*Implementation Notes:* Search for all implantable device UDIs for a patient. Fetches a bundle of all Device resources for the specified patient [(how to search by reference)].




  [(how to search by reference)]: http://hl7.org/fhir/STU3/search.html#reference
  [(how to search by token)]: http://hl7.org/fhir/STU3/search.html#token
  [Composite Search Parameters]: http://hl7.org/fhir/STU3/search.html#combining
  [(how to search by date)]: http://hl7.org/fhir/STU3/search.html#date
