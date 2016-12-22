
**GET [base]/Location?name=[string]**

*Example:*

[GET https://fhir-open-api-dstu2.smarthealthit.org/Location?name=Health](https://fhir-open-api-dstu2.smarthealthit.org/Location?name=Health)


*Support:* Mandatory

*Implementation Notes:*  Search based on text name [(how to search by string)]. May also support:
   - address-city
   - address-state
   - address-postalcode

*Response Class:*

-   (Status 200): successful operation
-   (Status 400): invalid parameter
-   (Status 401/4xx): unauthorized request
-   (Status 403): insufficient scope


-----------


**GET [base]/Location?address=[string]**

*Example:*

[GET https://fhir-open-api-dstu2.smarthealthit.org/Location?address=Arbor](https://fhir-open-api-dstu2.smarthealthit.org/Location?address=Arbor)

[GET https://fhir-open-api-dstu2.smarthealthit.org/Location?address-postalcode=48104](https://fhir-open-api-dstu2.smarthealthit.org/Location?address-postalcode=48104)

*Support:* Mandatory

*Implementation Notes:* Search based on text address [(how to search by string)].

SHOULD support:
   - address-city
   - address-state
   - address-postalcod

*Response Class:*

-   (Status 200): successful operation
-   (Status 400): invalid parameter
-   (Status 401/4xx): unauthorized request
-   (Status 403): insufficient scope

  [(how to search by reference)]: http://hl7.org/fhir/2017Jan/search.html#reference
  [(how to search by token)]: http://hl7.org/fhir/2017Jan/search.html#token
 [(how to search by date)]: http://hl7.org/fhir/2017Jan/search.html#date
 [(how to search by string)]: http://hl7.org/fhir/2017Jan/search.html#string
