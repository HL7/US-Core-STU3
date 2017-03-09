
`GET [base]/Organization?identifier=[system]|[code]`

**Example:** GET [base]/Organization?identifier=12354

*Support:* Mandatory

*Implementation Notes:*  Search based on Organization identifier  [(how to search by token)].

*Response Class:*

-   (Status 200): successful operation
-   (Status 400): invalid parameter
-   (Status 401/4xx): unauthorized request
-   (Status 403): insufficient scope

-----------

`GET [base]/Organization?name=[string]`

**Example:** GET [base]/Organization?name=Health

*Support:* Mandatory

*Implementation Notes:* Search based on text name [(how to search by string)]. May also support:
   - address-city
   - address-state
   - address-postalcode

*Response Class:*

-   (Status 200): successful operation
-   (Status 400): invalid parameter
-   (Status 401/4xx): unauthorized request
-   (Status 403): insufficient scope

-----

`GET [base]/Organization?address=[string]`

**Example:** GET [base]/Organization?address=Arbor

**Example:** GET [base]/Organization?address-postalcode=48104

*Support:* Mandatory

*Implementation Notes:* Search based on text address [(how to search by string)].

*Response Class:*

-   (Status 200): successful operation
-   (Status 400): invalid parameter
-   (Status 401/4xx): unauthorized request
-   (Status 403): insufficient scope


  [(how to search by reference)]: http://build.fhir.org/search.html#reference
  [(how to search by token)]: http://build.fhir.org/search.html#token
 [(how to search by date)]: http://build.fhir.org/search.html#date
 [(how to search by string)]: http://build.fhir.org/search.html#string
