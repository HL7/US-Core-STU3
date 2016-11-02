



-------------------------

**Clients**

-   A client has connected to a server and fetched all of a patient's Assessment and Plan of Treatment information using `GET /CarePlan?patient=[id]&category=assess-plan`.
-   A client has connected to a server and fetched all of a patient's Assessment and Plan of Treatment information over a specified time period using `GET /CarePlan?patient=[id]&category=assess-plan&date=[date]`.


- A client **SHOULD** be capable of connecting to a server and fetching all of a patient's active Assessment and Plan of Treatment information using `GET /CarePlan?patient=[id]&category=assess-plan&status=active`.
- A client **SHOULD** be capable of connecting to a server and fetching all of a patient's active Assessment and Plan of Treatment information over a specified time period using `GET /CarePlan?patient=[id]&category=assess-plan&status=active&date=[date]`.

**Servers**

-  A server is capable of returning all of a patient's Assessment and Plan of Treatment information using `GET /CarePlan?patient=[id]&category=assess-plan`.
- A server is capable of returning a patient's Assessment and Plan of Treatment information over a specified time period using `GET /CarePlan?patient=[id]&category=assess-plan&date=[date]`.


- A server **SHOULD** be capable returning all of a patient's active Assessment and Plan of Treatment information using `GET /CarePlan?patient=[id]&category=assess-plan&status=active`.
- A server **SHOULD** be capable returning a patient's active Assessment and Plan of Treatment information over a specified time period using `GET /CarePlan?patient=[id]&category=assess-plan&status=active&date=[date]`.


- A server has ensured that every API request includes a valid Authorization token, supplied via:Authorization: Bearer {server-specific-token-here}
- A server has rejected any unauthorized requests by returning an HTTP 401 Unauthorized response code.

-----------

`GET /CarePlan?patient=[id]&category=assess-plan`

*Support:* Mandatory to support search by patient.

*Implementation Notes:* Search for all patient assessments and plans of treatment for a patient. Fetches a bundle of all CarePlan resources for the specified patient [(how to search by reference)] and [(how to search by token)].

.

*Response Class:*

-   (Status 200): successful operation
-   (Status 400): invalid parameter
-   (Status 401/4xx): unauthorized request
-   (Status 403): insufficient scope

**Example:**

GET https://fhir-open-api-dstu2.smarthealthit.org/CarePlan?patient=1137192&category=assess-plan

-----------

`GET /CarePlan?patient=[id]&category=assess-plan&date=[date]`

*Support:* Mandatory to support search by date

*Implementation Notes:* Search for all assessment and plan of treatment for a patient within a time period. Fetches a bundle of all CarePlan resources for the specified patient for a specified time period.  [(how to search by reference)], [(how to search by token)] and [(how to search by date)].

.

*Response Class:*

-   (Status 200): successful operation
-   (Status 400): invalid parameter
-   (Status 401/4xx): unauthorized request
-   (Status 403): insufficient scope

**Example:**

GET https://fhir-open-api-dstu2.smarthealthit.org/CarePlan?patient=1137192&category=assess-plan&date=ge2015-01-14

GET https://fhir-open-api-dstu2.smarthealthit.org/CarePlan?patient=1137192&category=assess-plan&date=ge2015-01-14&date=le2016-01-14

-----------

`GET /CarePlan?patient=[id]&category=assess-plan&status=active`

*Support:* SHOULD support search by patient and status = 'active'.

*Implementation Notes:* SHOULD support search by reference and status. [(how to search by reference)], [(how to search by token)].

.

*Response Class:*

-   (Status 200): successful operation
-   (Status 400): invalid parameter
-   (Status 401/4xx): unauthorized request
-   (Status 403): insufficient scope

**Example:**

 GET https://fhir-open-api-dstu2.smarthealthit.org/CarePlan?patient=1137192&status=active


-----------

`GET /CarePlan?patient=[id]&category=assess-plan&status=active&date=[date]`

*Support:* SHOULD support search by patient and status = 'active' and date.

*Implementation Notes:* Search for all active assessment and plan of treatment for a patient within a time period. Fetches a bundle of all active (careplan = "active") CarePlan resources for the specified patient for a specified time period.  [(how to search by reference)], [(how to search by token)] and [(how to search by date)].
.

*Response Class:*

-   (Status 200): successful operation
-   (Status 400): invalid parameter
-   (Status 401/4xx): unauthorized request
-   (Status 403): insufficient scope

**Example:**

 GET https://fhir-open-api-dstu2.smarthealthit.org/CarePlan?patient=1137192&category=assess-plan&datatus=active&date=ge2015-01-14




  [(how to search by reference)]: http://hl7.org/fhir/DSTU2/search.html#reference
  [`https://fhir-open-api-dstu2.smarthealthit.org/AllergyIntolerance?patient=1137192`]: https://fhir-open-api-dstu2.smarthealthit.org/AllergyIntolerance?patient=1137192
  [(how to search by token)]: http://hl7.org/fhir/DSTU2/search.html#token
  [Composite Search Parameters]: http://hl7-fhir.github.io/search.html#combining
  [`https://fhir-open-api-dstu2.smarthealthit.org/AllergyIntolerance?patient=1137192&status=active,unconfirmed,confirmed`]: https://fhir-open-api-dstu2.smarthealthit.org/AllergyIntolerance?patient=1137192&status=active,unconfirmed,confirmed
   [(how to search by date)]: http://hl7.org/fhir/DSTU2/search.html#date
