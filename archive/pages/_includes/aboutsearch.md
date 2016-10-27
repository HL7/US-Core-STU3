



-------------------------

**Clients**

-   A client has connected to a server and fetched a patient's profile using [GET /Profile?patient=\[id]\].

**Servers**

-   A server is capable of returning a patient's profile list using [GET /AllergyIntolerance?patient=\[id]\].
-   A server has ensured that every API request includes a valid Authorization token, supplied via:Authorization: Bearer {server-specific-token-here}
-   A server has rejected any unauthorized requests by returning an HTTP 401 Unauthorized response code.

-----------

`GET /AllergyIntolerance?patient=\[id\]`

*Support:* Mandatory to support search by patient.

*Implementation Notes:* Search for all allergies for a patient. Fetches a bundle of all AllergyIntolerance resources for the specified patient [(how to search by reference)].

*Response Class:*

-   (Status 200): successful operation
-   (Status 400): invalid parameter
-   (Status 401/4xx): unauthorized request
-   (Status 403): insufficient scope

**Example:**

GET https://fhir-open-api-dstu2.smarthealthit.org/AllergyIntolerance?patient=1137192


  [(how to search by reference)]: http://hl7.org/fhir/DSTU2/search.html#reference
  [`https://fhir-open-api-dstu2.smarthealthit.org/AllergyIntolerance?patient=1137192`]: https://fhir-open-api-dstu2.smarthealthit.org/AllergyIntolerance?patient=1137192
  [(how to search by token)]: http://hl7.org/fhir/DSTU2/search.html#token
  [Composite Search Parameters]: http://hl7-fhir.github.io/search.html#combining
  [`https://fhir-open-api-dstu2.smarthealthit.org/AllergyIntolerance?patient=1137192&status=active,unconfirmed,confirmed`]: https://fhir-open-api-dstu2.smarthealthit.org/AllergyIntolerance?patient=1137192&status=active,unconfirmed,confirmed

