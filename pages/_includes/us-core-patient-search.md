
`GET [base]/Patient/[id]`

**Example:** GET [base]/Patient/1032702


*Support:* Mandatory

*Implementation Notes:*  Fetches a single Patient

*Response Class:*

-   (Status 200): successful operation
-   (Status 400): invalid parameter
-   (Status 401/4xx): unauthorized request
-   (Status 403): insufficient scope
-   (Status 404): unknown resource
-   (Status 410): deleted resource

-----------

**`GET [base]/Patient/identifier=[system]|[code]`**

**Example:** GET [base]/Patient?identifier=http://hospital.smarthealthit.org|1032702

*Support:* Mandatory

*Implementation Notes:*  Fetches a single Patient by an Identifier such as a MPI

*Response Class:*

-   (Status 200): successful operation
-   (Status 400): invalid parameter
-   (Status 401/4xx): unauthorized request
-   (Status 403): insufficient scope
-   (Status 404): unknown resource
-   (Status 410): deleted resource

-----------

`GET [base]/Patient?name=[string]&birthdate=[date]`

**Example:** GET [base]/Patient?name=Shaw&birthdate=2007-03-20


*Support:* Mandatory

*Implementation Notes:*  Search based on at least 2 patient elements -text name [(how to search by string)] and birthdate [(how to search by date)]


*Response Class:*

-   (Status 200): successful operation
-   (Status 400): invalid parameter
-   (Status 401/4xx): unauthorized request
-   (Status 403): insufficient scope
-   (Status 404): unknown resource
-   (Status 410): deleted resource

-----------
`GET [base]/Patient?name=[string]&gender=[code]`

**Example:** GET [base]/Patient?name=Shaw&gender=female

*Support:* Mandatory

*Implementation Notes:*  Search based on at least 2 patient elements -text name [(how to search by string)] and gender [(how to search by token)].

*Response Class:*

-   (Status 200): successful operation
-   (Status 400): invalid parameter
-   (Status 401/4xx): unauthorized request
-   (Status 403): insufficient scope
-   (Status 404): unknown resource
-   (Status 410): deleted resource

-----------

`GET [base]/Patient?family=[string]&gender=[code]`

**Example:** GET [base]/Patient?family=shaw&gender=female

*Support:* SHOULD support Patient search by family name and gender

*Implementation Notes:*  Search based on at least 2 patient elements -text family name [(how to search by string)] and gender [(how to search by token)].

*Response Class:*

-   (Status 200): successful operation
-   (Status 400): invalid parameter
-   (Status 401/4xx): unauthorized request
-   (Status 403): insufficient scope
-   (Status 404): unknown resource
-   (Status 410): deleted resource

-----------

`GET [base]/Patient?given=[string]&gender=[code]`

**Example:** GET [base]/Patient?given=amy&gender=female

*Support:* SHOULD support Patient search by given name and gender

*Implementation Notes:*  Search based on at least 2 patient elements -text given name [(how to search by string)] and gender [(how to search by token)]

*Response Class:*

-   (Status 200): successful operation
-   (Status 400): invalid parameter
-   (Status 401/4xx): unauthorized request
-   (Status 403): insufficient scope
-   (Status 404): unknown resource
-   (Status 410): deleted resource

-----------

  [(how to search by reference)]: http://build.fhir.org/search.html#reference
  [(how to search by token)]: http://build.fhir.org/search.html#token
  [Composite Search Parameters]: http://build.fhir.org/search.html#combining
  [(how to search by date)]: http://build.fhir.org/search.html#date
  [(how to search by string)]: http://build.fhir.org/search.html#string
