

-------------------------

**Clients**

-  A client is able to connect to a server and fetch all current care team members for a patient using `GET[base]/CareTeam?patient=[id]&status=active`

**Servers**

-  A server is capable of returning a patient's current care team members using `GET[base]/CareTeam?patient=[id]&status=active`


- A server has ensured that every API request includes a valid Authorization token, supplied via:Authorization: Bearer {server-specific-token-here}
- A server has rejected any unauthorized requests by returning an HTTP 401 Unauthorized response code.

-----------

`GET/CareTeam?patient=[id]&status=active`

*Support:* Mandatory to support search by patient and status.

*Implementation Notes:* Search for all current care team members for a patient. Fetches a bundle of all current CareTeam resource(s) and the participants referenced by the CareTeam resource(s) for the specified patient. [(how to search by reference)], [(how to search by token)] and [(how to include referenced resources in search result)](http://hl7.org/fhir/2017Jan/search.html#include).



*Response Class:*

-   (Status 200): successful operation
-   (Status 400): invalid parameter
-   (Status 401/4xx): unauthorized request
-   (Status 403): insufficient scope

**Example:**

[GET https://fhir-open-api-dstu2.smarthealthit.org/CareTeam?patient=1137192&category=assess-plan](https://fhir-open-api-dstu2.smarthealthit.org/CareTeam?patient=1137192&category=assess-plan)



  [(how to search by reference)]: http://hl7.org/fhir/2017Jan/search.html#reference
  [(how to search by token)]: http://hl7.org/fhir/2017Jan/search.html#token
  [Composite Search Parameters]: http://hl7.org/fhir/2017Jan/search.html#combining
  [(how to search by date)]: http://hl7.org/fhir/2017Jan/search.html#date

l#date





-------------------------

**Clients**

-   A client has connected to a server and fetched all of a patient's Assessment and Plan of Treatment information using `GET /CareTeam?patient=[id]&category=assess-plan`.
-   A client has connected to a server and fetched all of a patient's Assessment and Plan of Treatment information over a specified time period using `GET /CareTeam?patient=[id]&category=assess-plan&date=[date]`.


- A client **SHOULD** be capable of connecting to a server and fetching all of a patient's active Assessment and Plan of Treatment information using `GET /CareTeam?patient=[id]&category=assess-plan&status=active`.
- A client **SHOULD** be capable of connecting to a server and fetching all of a patient's active Assessment and Plan of Treatment information over a specified time period using `GET /CareTeam?patient=[id]&category=assess-plan&status=active&date=[date]`.

**Servers**

-  A server is capable of returning all of a patient's Assessment and Plan of Treatment information using `GET /CareTeam?patient=[id]&category=assess-plan`.
- A server is capable of returning a patient's Assessment and Plan of Treatment information over a specified time period using `GET /CareTeam?patient=[id]&category=assess-plan&date=[date]`.


- A server **SHOULD** be capable returning all of a patient's active Assessment and Plan of Treatment information using `GET /CareTeam?patient=[id]&category=assess-plan&status=active`.
- A server **SHOULD** be capable returning a patient's active Assessment and Plan of Treatment information over a specified time period using `GET /CareTeam?patient=[id]&category=assess-plan&status=active&date=[date]`.


- A server has ensured that every API request includes a valid Authorization token, supplied via:Authorization: Bearer {server-specific-token-here}
- A server has rejected any unauthorized requests by returning an HTTP 401 Unauthorized response code.

-----------

`GET /CareTeam?patient=[id]&category=assess-plan`

*Support:* Mandatory to support search by patient.

*Implementation Notes:* Search for all patient assessments and plans of treatment for a patient. Fetches a bundle of all CareTeam resources for the specified patient [(how to search by reference)] and [(how to search by token)].

.

*Response Class:*

-   (Status 200): successful operation
-   (Status 400): invalid parameter
-   (Status 401/4xx): unauthorized request
-   (Status 403): insufficient scope

**Example:**

[GET https://fhir-open-api-dstu2.smarthealthit.org/CareTeam?patient=1137192&category=assess-plan](https://fhir-open-api-dstu2.smarthealthit.org/CareTeam?patient=1137192&category=assess-plan)

-----------

`GET /CareTeam?patient=[id]&category=assess-plan&date=[date]`

*Support:* Mandatory to support search by date

*Implementation Notes:* Search for all assessment and plan of treatment for a patient within a time period. Fetches a bundle of all CareTeam resources for the specified patient for a specified time period.  [(how to search by reference)], [(how to search by token)] and [(how to search by date)].

.

*Response Class:*

-   (Status 200): successful operation
-   (Status 400): invalid parameter
-   (Status 401/4xx): unauthorized request
-   (Status 403): insufficient scope

**Example:**

[GET https://fhir-open-api-dstu2.smarthealthit.org/CareTeam?patient=1137192&category=assess-plan&date=ge2015-01-14](https://fhir-open-api-dstu2.smarthealthit.org/CareTeam?patient=1137192&category=assess-plan&date=ge2015-01-14)

[GET https://fhir-open-api-dstu2.smarthealthit.org/CareTeam?patient=1137192&category=assess-plan&date=ge2015-01-14&date=le2016-01-14](https://fhir-open-api-dstu2.smarthealthit.org/CareTeam?patient=1137192&category=assess-plan&date=ge2015-01-14&date=le2016-01-14)

-----------

`GET /CareTeam?patient=[id]&category=assess-plan&status=active`

*Support:* SHOULD support search by patient and status = 'active'.

*Implementation Notes:* SHOULD support search by reference and status. [(how to search by reference)], [(how to search by token)].

.

*Response Class:*

-   (Status 200): successful operation
-   (Status 400): invalid parameter
-   (Status 401/4xx): unauthorized request
-   (Status 403): insufficient scope

**Example:**

 [GET https://fhir-open-api-dstu2.smarthealthit.org/CareTeam?patient=1137192&status=active](https://fhir-open-api-dstu2.smarthealthit.org/CareTeam?patient=1137192&status=active)


-----------

`GET /CareTeam?patient=[id]&category=assess-plan&status=active&date=[date]`

*Support:* SHOULD support search by patient and status = 'active' and date.

*Implementation Notes:* Search for all active assessment and plan of treatment for a patient within a time period. Fetches a bundle of all active (CareTeam = "active") CareTeam resources for the specified patient for a specified time period.  [(how to search by reference)], [(how to search by token)] and [(how to search by date)].
.

*Response Class:*

-   (Status 200): successful operation
-   (Status 400): invalid parameter
-   (Status 401/4xx): unauthorized request
-   (Status 403): insufficient scope

**Example:**

 [GET https://fhir-open-api-dstu2.smarthealthit.org/CareTeam?patient=1137192&category=assess-plan&datatus=active&date=ge2015-01-14](https://fhir-open-api-dstu2.smarthealthit.org/CareTeam?patient=1137192&category=assess-plan&datatus=active&date=ge2015-01-14)




  [(how to search by reference)]: http://hl7.org/fhir/2017Jan/search.html#reference
  [`https://fhir-open-api-dstu2.smarthealthit.org/AllergyIntolerance?patient=1137192`]: https://fhir-open-api-dstu2.smarthealthit.org/AllergyIntolerance?patient=1137192
  [(how to search by token)]: http://hl7.org/fhir/2017Jan/search.html#token
  [Composite Search Parameters]: http://hl7.org/fhir/2017Jan/search.html#combining
  [`https://fhir-open-api-dstu2.smarthealthit.org/AllergyIntolerance?patient=1137192&status=active,unconfirmed,confirmed`]: https://fhir-open-api-dstu2.smarthealthit.org/AllergyIntolerance?patient=1137192&status=active,unconfirmed,confirmed
   [(how to search by date)]: http://hl7.org/fhir/2017Jan/search.html#date
date)]: http://hl7.org/fhir/2017Jan/search.html#date
