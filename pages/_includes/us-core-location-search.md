
**GET [base]/Location?name=[string]**

*Example:*

GET [base]/Location?name=Health


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

GET [base]/Location?address=Arbor

GET [base]/Location?address-postalcode=48104

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

  [(how to search by reference)]: http://build.fhir.org/search.html#reference
  [(how to search by token)]: http://build.fhir.org/search.html#token
 [(how to search by date)]: http://build.fhir.org/search.html#date
 [(how to search by string)]: http://build.fhir.org/search.html#string
