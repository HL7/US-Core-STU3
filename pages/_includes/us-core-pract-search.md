


-----------

**GET [base]/Practitioner?identifier=[system]|[code]**

*Example:*

[GET https://fhir-open-api-dstu2.smarthealthit.org/Practitioner?identifier=http://hl7.org/fhir/sid/us-npi%7C1497860456](https://fhir-open-api-dstu2.smarthealthit.org/Practitioner?identifier=http://hl7.org/fhir/sid/us-npi%7C1497860456)

*Support:* Mandatory

*Implementation Notes:*  Search based on practitioner identifier  [(how to search by token)].

*Response Class:*

-   (Status 200): successful operation
-   (Status 400): invalid parameter
-   (Status 401/4xx): unauthorized request

-----------


**GET [base]/Practitioner?family=[string]&given=[string]**

*Example:*

[GET https://fhir-open-api-dstu2.smarthealthit.org/Practitioner?family=Smith&given=John](https://fhir-open-api-dstu2.smarthealthit.org/Practitioner?family=Smith&given=John)

*Support:* Mandatory

*Implementation Notes:* Search based on text name [(how to search by string)].

*Response Class:*

-   (Status 200): successful operation
-   (Status 400): invalid parameter
-   (Status 401/4xx): unauthorized request

  [(how to search by reference)]: http://hl7.org/fhir/2017Jan/search.html#reference
  [(how to search by token)]: http://hl7.org/fhir/2017Jan/search.html#token
 [(how to search by date)]: http://hl7.org/fhir/2017Jan/search.html#date
 [(how to search by string)]: http://hl7.org/fhir/2017Jan/search.html#string
