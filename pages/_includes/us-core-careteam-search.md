

-----------

`GET/CareTeam?patient=[id]&status=active`


**Example:**

[GET https://fhir-open-api-dstu2.smarthealthit.org/CareTeam?patient=1137192&status=active](https://fhir-open-api-dstu2.smarthealthit.org/CareTeam?patient=1137192&status=active)


*Support:* Mandatory to support search by patient and status.

*Implementation Notes:* Search for all current care team members for a patient. Fetches a bundle of all current CareTeam resource(s) and the participants referenced by the CareTeam resource(s) for the specified patient. [(how to search by reference)], [(how to search by token)].


*Response Class:*

-   (Status 200): successful operation
-   (Status 400): invalid parameter
-   (Status 401/4xx): unauthorized request
-   (Status 403): insufficient scope



  [(how to search by reference)]: http://hl7.org/fhir/2017Jan/search.html#reference
  [(how to search by token)]: http://hl7.org/fhir/2017Jan/search.html#token
  [Composite Search Parameters]: http://hl7.org/fhir/2017Jan/search.html#combining
  [(how to search by date)]: http://hl7.org/fhir/2017Jan/search.html#date
  [(how to include referenced resources in search result)]: (http://hl7.org/fhir/2017Jan/search.html#include)
