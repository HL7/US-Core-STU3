
`GET /AllergyIntolerance?patient=[id]`

**Example:** GET [base]/AllergyIntolerance?patient=1137192


*Support:* Mandatory to support search by patient.

*Implementation Notes:* Search for all allergies for a patient. Fetches a bundle of all AllergyIntolerance resources for the specified patient [(how to search by reference)].




  [(how to search by reference)]: http://hl7.org/fhir/STU3/search.html#reference
  [`https://fhir-open-api-dstu2.smarthealthit.org/AllergyIntolerance?patient=1137192`]: https://fhir-open-api-dstu2.smarthealthit.org/AllergyIntolerance?patient=1137192
  [(how to search by token)]: http://hl7.org/fhir/STU3/search.html#token
  [Composite Search Parameters]: http://hl7.org/fhir/STU3/search.html#combining
  [`https://fhir-open-api-dstu2.smarthealthit.org/AllergyIntolerance?patient=1137192&status=active,unconfirmed,confirmed`]: https://fhir-open-api-dstu2.smarthealthit.org/AllergyIntolerance?patient=1137192&status=active,unconfirmed,confirmed
