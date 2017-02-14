
`GET /Condition?patient=[id]`


**Example:**

[GET https://fhir-open-api-dstu2.smarthealthit.org/Condition?patient=1032702](https://fhir-open-api-dstu2.smarthealthit.org/Condition?patient=1032702)

*Support:* Mandatory to support search by patient.

*Implementation Notes:*  Search for all problems and health concerns for a patient. Fetches a bundle of all Condition resources for the specified patient. [(how to search by reference)] and [(how to search by token)].

*Response Class:*

-   (Status 200): successful operation
-   (Status 400): invalid parameter
-   (Status 401/4xx): unauthorized request
-   (Status 403): insufficient scope

-----------

`GET /Condition?patient=[id]&clinicalstatus=active,recurrance,remission'`
**Example:**

[GET https://fhir-open-api-dstu2.smarthealthit.org/Condition?patient=1032702&clinicalstatus=active,relapse,remission](https://fhir-open-api-dstu2.smarthealthit.org/Condition?patient=1032702&clinicalstatus=active,relapse,remission)

*Support:* Optional to support search by status.

*Implementation Notes:* Search for all active problems and health concerns for a patient. Fetches a bundle of all Condition resources for the specified patient and all "active" statuses (active,relapse,remission)  [(how to search by reference)] and [(how to search by token)].  This will not return any "entered in error" resources because of the conditional presence of the clinicalStatus element.


*Response Class:*

-   (Status 200): successful operation
-   (Status 400): invalid parameter
-   (Status 401/4xx): unauthorized request
-   (Status 403): insufficient scope

-----------
`GET /Condition?patient=[id]&category=problem`

**Example:**

[GET https://fhir-open-api-dstu2.smarthealthit.org/Condition?patient=1032702&category=problem](https://fhir-open-api-dstu2.smarthealthit.org/Condition?patient=1032702&category=problem)

*Support:* Optional to support search by patient and category.

*Implementation Notes:*  earch for all Problems for a patient. Fetches a bundle of all Condition resources for the specified patient with a category code of "problem" [(how to search by reference)] and [(how to search by token)].


*Response Class:*

-   (Status 200): successful operation
-   (Status 400): invalid parameter
-   (Status 401/4xx): unauthorized request
-   (Status 403): insufficient scope

-----------

`GET /Condition?patient=[id]&category=health-concern`


**Example:**

[GET https://fhir-open-api-dstu2.smarthealthit.org/Condition?patient=1032702&category=health-concern](https://fhir-open-api-dstu2.smarthealthit.org/Condition?patient=1032702&category=health-concern)

*Support:* Optional to support search by patient and category.

*Implementation Notes:*  Search for all Health Concerns for a patient. Fetches a bundle of all Condition resources for the specified patient with a category code of "health-concern"[(how to search by reference)] and [(how to search by token)].

*Response Class:*

-   (Status 200): successful operation
-   (Status 400): invalid parameter
-   (Status 401/4xx): unauthorized request
-   (Status 403): insufficient scope


-----------


  [(how to search by reference)]: http://build.fhir.org/search.html#reference
  [(how to search by token)]: http://build.fhir.org/search.html#token
  [Composite Search Parameters]: http://build.fhir.org/search.html#combining
  [(how to search by date)]: http://build.fhir.org/search.html#date
  [(how to search by string)]: http://build.fhir.org/search.html#string
