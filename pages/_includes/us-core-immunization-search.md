
`GET /Immunization?patient=[id]`

**Example:**

[GET https://fhir-open-api-dstu2.smarthealthit.org/Immunization?patient=1032702](https://fhir-open-api-dstu2.smarthealthit.org/Immunization?patient=1032702)

*Support:* Mandatory to support search by patient.

*Implementation Notes:* Search for all Immunization resources for a patient. Fetches a bundle of all Immunization resources for the specified patient  [(how to search by reference)].

*Response Class:*

-   (Status 200): successful operation
-   (Status 400): invalid parameter
-   (Status 401/4xx): unauthorized request
-   (Status 403): insufficient scope

  [(how to search by reference)]: http://hl7.org/fhir/2017Jan/search.html#reference
  [(how to search by token)]: http://hl7.org/fhir/2017Jan/search.html#token
  [Composite Search Parameters]: http://hl7.org/fhir/2017Jan/search.html#combining
  [(how to search by date)]: http://hl7.org/fhir/2017Jan/search.html#date
