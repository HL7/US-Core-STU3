

-------------------------

**Clients**

-  A client has connected to a server and fetched a patient using GET [base]/Patient/[id].
- A client has connected to a server and searched through available Patients using at least 2 (example name and gender) of the following search parameters:
   - name
   - gender
   - birthdate

To limit overly broad search results, a client search with gender **SHOULD** include family and given name search parameters.




**Servers**

- A server is capable of returning a patient using GET [base]/Patient/[id].
- A server returns valid FHIR Patient resources according to the Data Access Framework (DAF) Patient Profile..
- A server has exposed a FHIR Patient search endpoint supporting at a minimum the following search parameters:
   - identifier
- A server has exposed a FHIR Patient search endpoint supporting at a minimum the following search parameters when at least 2 (example name and gender) are present:
   - name
   - gender
   - birthdate
- A server has ensured that every API request includes a valid Authorization token, supplied via:Authorization: Bearer {server-specific-token-here}
- A server has rejected any unauthorized requests by returning an HTTP 401 Unauthorized response code.

-----------
`GET [base]/Patient/[id]`

*Support:* Mandatory

*Implementation Notes:*  Fetches a single Patient

*Response Class:*

-   (Status 200): successful operation
-   (Status 400): invalid parameter
-   (Status 401/4xx): unauthorized request
-   (Status 403): insufficient scope
-   (Status 404): unknown resource
-   (Status 410): deleted resource

**Example:**

GET https://fhir-open-api.smarthealthit.org/Patient/1032702

-----------

`GET [base]/Patient?name=[string]&birthdate=[date]`

*Support:* Mandatory

*Implementation Notes:*  Search based on at least 2 patient elements -text name [(how to search by string)] and birthdate [(how to search by date)]


*Response Class:*

-   (Status 200): successful operation
-   (Status 400): invalid parameter
-   (Status 401/4xx): unauthorized request
-   (Status 403): insufficient scope
-   (Status 404): unknown resource
-   (Status 410): deleted resource

**Example:**

GET https://fhir-open-api-dstu2.smarthealthit.org/Patient?name=Shaw&birthdate=2007-03-20

-----------
`GET [base]/Patient?name=[string]&gender=[code]`

*Support:* Mandatory

*Implementation Notes:*  Search based on at least 2 patient elements -text name [(how to search by string)] and gender [(how to search by token)].


*Response Class:*

-   (Status 200): successful operation
-   (Status 400): invalid parameter
-   (Status 401/4xx): unauthorized request
-   (Status 403): insufficient scope
-   (Status 404): unknown resource
-   (Status 410): deleted resource

**Example:**

GET  https://fhir-open-api-dstu2.smarthealthit.org/Patient?name=Shaw&gender=female

-----------

`GET [base]/Patient?family=[string]&gender=[code]`

*Support:* SHOULD support Patient search by family name and gender

*Implementation Notes:*  Search based on at least 2 patient elements -text family name [(how to search by string)] and gender [(how to search by token)].

*Response Class:*

-   (Status 200): successful operation
-   (Status 400): invalid parameter
-   (Status 401/4xx): unauthorized request
-   (Status 403): insufficient scope
-   (Status 404): unknown resource
-   (Status 410): deleted resource

**Example:**

GET  https://fhir-open-api-dstu2.smarthealthit.org/Patient?family=shaw&gender=female

-----------

`GET [base]/Patient?given=[string]&gender=[code]`

*Support:* SHOULD support Patient search by given name and gender

*Implementation Notes:*  Search based on at least 2 patient elements -text given name [(how to search by string)] and gender [(how to search by token)]

*Response Class:*

-   (Status 200): successful operation
-   (Status 400): invalid parameter
-   (Status 401/4xx): unauthorized request
-   (Status 403): insufficient scope
-   (Status 404): unknown resource
-   (Status 410): deleted resource

**Example:**

GET  https://fhir-open-api-dstu2.smarthealthit.org/Patient?given=amy&gender=female

-----------




  [(how to search by reference)]: http://hl7.org/fhir/DSTU2/search.html#reference
  [(how to search by token)]: http://hl7.org/fhir/DSTU2/search.html#token
  [Composite Search Parameters]: http://hl7-fhir.github.io/search.html#combining
  [(how to search by date)]: http://hl7.org/fhir/DSTU2/search.html#date
  [(how to search by string)]: http://hl7.org/fhir/DSTU2/search.html#string
