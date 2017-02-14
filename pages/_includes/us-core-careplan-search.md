

`GET /CarePlan?patient=[id]&category=assess-plan`

**Example:**

[GET https://fhir-open-api-dstu2.smarthealthit.org/CarePlan?patient=1137192&category=assess-plan](https://fhir-open-api-dstu2.smarthealthit.org/CarePlan?patient=1137192&category=assess-plan)](https://fhir-open-api-dstu2.smarthealthit.org/CarePlan?patient=1137192&category=assess-plan](https://fhir-open-api-dstu2.smarthealthit.org/CarePlan?patient=1137192&category=assess-plan)

*Support:* Mandatory to support search by patient.

*Implementation Notes:* Search for all patient assessments and plans of treatment for a patient. Fetches a bundle of all CarePlan resources for the specified patient [(how to search by reference)] and [(how to search by token)].

.

*Response Class:*

-   (Status 200): successful operation
-   (Status 400): invalid parameter
-   (Status 401/4xx): unauthorized request
-   (Status 403): insufficient scope

-----------

`GET /CarePlan?patient=[id]&category=assess-plan&date=[date]`

**Example:**

[GET https://fhir-open-api-dstu2.smarthealthit.org/CarePlan?patient=1137192&category=assess-plan&date=ge2015-01-14](https://fhir-open-api-dstu2.smarthealthit.org/CarePlan?patient=1137192&category=assess-plan&date=ge2015-01-14)](https://fhir-open-api-dstu2.smarthealthit.org/CarePlan?patient=1137192&category=assess-plan&date=ge2015-01-14](https://fhir-open-api-dstu2.smarthealthit.org/CarePlan?patient=1137192&category=assess-plan&date=ge2015-01-14)


[GET https://fhir-open-api-dstu2.smarthealthit.org/CarePlan?patient=1137192&category=assess-plan&date=ge2015-01-14&date=le2016-01-14](https://fhir-open-api-dstu2.smarthealthit.org/CarePlan?patient=1137192&category=assess-plan&date=ge2015-01-14&date=le2016-01-14)](https://fhir-open-api-dstu2.smarthealthit.org/CarePlan?patient=1137192&category=assess-plan&date=ge2015-01-14&date=le2016-01-14](https://fhir-open-api-dstu2.smarthealthit.org/CarePlan?patient=1137192&category=assess-plan&date=ge2015-01-14&date=le2016-01-14)

*Support:* Mandatory to support search by date

*Implementation Notes:* Search for all assessment and plan of treatment for a patient within a time period. Fetches a bundle of all CarePlan resources for the specified patient for a specified time period.  [(how to search by reference)], [(how to search by token)] and [(how to search by date)].

.

*Response Class:*

-   (Status 200): successful operation
-   (Status 400): invalid parameter
-   (Status 401/4xx): unauthorized request
-   (Status 403): insufficient scope

-----------

`GET /CarePlan?patient=[id]&category=assess-plan&status=active`

**Example:**

 [GET https://fhir-open-api-dstu2.smarthealthit.org/CarePlan?patient=1137192&status=active](https://fhir-open-api-dstu2.smarthealthit.org/CarePlan?patient=1137192&status=active)

*Support:* SHOULD support search by patient and status = 'active'.

*Implementation Notes:* SHOULD support search by reference and status. [(how to search by reference)], [(how to search by token)].

.

*Response Class:*

-   (Status 200): successful operation
-   (Status 400): invalid parameter
-   (Status 401/4xx): unauthorized request
-   (Status 403): insufficient scope

-----------

`GET /CarePlan?patient=[id]&category=assess-plan&status=active&date=[date]`

**Example:**

 [GET https://fhir-open-api-dstu2.smarthealthit.org/CarePlan?patient=1137192&category=assess-plan&datatus=active&date=ge2015-01-14](https://fhir-open-api-dstu2.smarthealthit.org/CarePlan?patient=1137192&category=assess-plan&datatus=active&date=ge2015-01-14)

*Support:* SHOULD support search by patient and status = 'active' and date.

*Implementation Notes:* Search for all active assessment and plan of treatment for a patient within a time period. Fetches a bundle of all active (careplan = "active") CarePlan resources for the specified patient for a specified time period.  [(how to search by reference)], [(how to search by token)] and [(how to search by date)].
.

*Response Class:*

-   (Status 200): successful operation
-   (Status 400): invalid parameter
-   (Status 401/4xx): unauthorized request
-   (Status 403): insufficient scope


  [(how to search by reference)]: http://build.fhir.org/search.html#reference
  [`https://fhir-open-api-dstu2.smarthealthit.org/AllergyIntolerance?patient=1137192`]: https://fhir-open-api-dstu2.smarthealthit.org/AllergyIntolerance?patient=1137192
  [(how to search by token)]: http://build.fhir.org/search.html#token
  [Composite Search Parameters]: http://build.fhir.org/search.html#combining
  [`https://fhir-open-api-dstu2.smarthealthit.org/AllergyIntolerance?patient=1137192&status=active,unconfirmed,confirmed`]: https://fhir-open-api-dstu2.smarthealthit.org/AllergyIntolerance?patient=1137192&status=active,unconfirmed,confirmed
   [(how to search by date)]: http://build.fhir.org/search.html#date
