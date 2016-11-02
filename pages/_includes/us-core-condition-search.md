

-------------------------

**Clients**

- A client connected to a server and fetched all problems and health concerns for a patient, including current as well as historical problems and health concerns using `GET/Condition?patient=[id]`.


**Servers**

- A server is capable of returning a patient's conditions list using `GET/Condition?patient=[id]`.
- A server has ensured that every API request includes a valid Authorization token, supplied via:Authorization: Bearer {server-specific-token-here}
- A server has rejected any unauthorized requests by returning an HTTP 401 Unauthorized response code.

-----------
`GET /Condition?patient=[id]`

*Support:* Mandatory to support search by patient.

*Implementation Notes:*  Search for all problems and health concerns for a patient. Fetches a bundle of all Condition resources for the specified patient. [(how to search by reference)] and [(how to search by token)].

*Response Class:*

-   (Status 200): successful operation
-   (Status 400): invalid parameter
-   (Status 401/4xx): unauthorized request
-   (Status 403): insufficient scope


**Example:**

GET https://fhir-open-api-dstu2.smarthealthit.org/Condition?patient=1032702

-----------

`GET /Condition?patient=[id]&clinicalstatus=active,relapse,remission`

*Support:* Optional to support search by status.

*Implementation Notes:* Search for all active problems and health concerns for a patient. Fetches a bundle of all Condition resources for the specified patient and all "active" statuses (active,relapse,remission)  [(how to search by reference)] and [(how to search by token)].  This will not return any "entered in error" resources because of the conditional presence of the clinicalStatus element.



*Response Class:*

-   (Status 200): successful operation
-   (Status 400): invalid parameter
-   (Status 401/4xx): unauthorized request
-   (Status 403): insufficient scope


**Example:**

GET https://fhir-open-api-dstu2.smarthealthit.org/Condition?patient=1032702&clinicalstatus=active,relapse,remission

-----------
`GET /Condition?patient=[id]&category=problem`

*Support:* Optional to support search by patient and category.

*Implementation Notes:*  earch for all Problems for a patient. Fetches a bundle of all Condition resources for the specified patient with a category code of "problem" [(how to search by reference)] and [(how to search by token)].


*Response Class:*

-   (Status 200): successful operation
-   (Status 400): invalid parameter
-   (Status 401/4xx): unauthorized request
-   (Status 403): insufficient scope


**Example:**

GET https://fhir-open-api-dstu2.smarthealthit.org/Condition?patient=1032702&category=problem

-----------


`GET /Condition?patient=[id]&category=health-concern`

*Support:* Optional to support search by patient and category.

*Implementation Notes:*  Search for all Health Concerns for a patient. Fetches a bundle of all Condition resources for the specified patient with a category code of "health-concern"[(how to search by reference)] and [(how to search by token)].

*Response Class:*

-   (Status 200): successful operation
-   (Status 400): invalid parameter
-   (Status 401/4xx): unauthorized request
-   (Status 403): insufficient scope


**Example:**

GET https://fhir-open-api-dstu2.smarthealthit.org/Condition?patient=1032702&category=health-concern

-----------


  [(how to search by reference)]: http://hl7.org/fhir/DSTU2/search.html#reference
  [(how to search by token)]: http://hl7.org/fhir/DSTU2/search.html#token
  [Composite Search Parameters]: http://hl7-fhir.github.io/search.html#combining
  [(how to search by date)]: http://hl7.org/fhir/DSTU2/search.html#date
  [(how to search by string)]: http://hl7.org/fhir/DSTU2/search.html#string
