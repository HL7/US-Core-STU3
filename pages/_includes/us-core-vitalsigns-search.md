
`GET [base]/Observation?patient=[id]&category=vital-signs`

**Example:**

[GET https://fhir-open-api-dstu2.smarthealthit.org/Observation?patient=1186747&category=vital-signs](https://fhir-open-api-dstu2.smarthealthit.org/Observation?patient=1186747&category=vital-signs)



*Support:*  Mandatory to support search by category code.

*Implementation Notes:*   Search based on vital sign category code. This search fetches a bundle of all Observation resources with category 'vital-signs' for the specified patient  [(how to search by reference)] and [(how to search by token)].  The table above is the minimum set, additional vital signs are allowed.

*Response Class:*

-   (Status 200): successful operation
-   (Status 400): invalid parameter
-   (Status 401/4xx): unauthorized request
-   (Status 403): insufficient scope

-----------

`GET [base]/Observation?patient=[id]&code=[vital sign LOINC{,LOINC2,LOINC3,...}]`

**Example:**
Search for all heart rate observations for a patient:

[GET https://fhir-open-api-dstu2.smarthealthit.org/Observation?patient=1186747&code=8867-4](https://fhir-open-api-dstu2.smarthealthit.org/Observation?patient=1186747&code=8867-4)

**Example:**
Search for all heart rate, respiratory rate and blood pressure observations for a patient

[GET https://fhir-open-api-dstu2.smarthealthit.org/Observation?patient=1186747&code=8867-4,9279-1,55284-4](https://fhir-open-api-dstu2.smarthealthit.org/Observation?patient=1186747&code=8867-4,9279-1,55284-4)

*Support:*  Mandatory to support search by vital sign LOINC(s) listed above.

*Implementation Notes:*   1)Search based on vital sign LOINC code(s). This fetches a bundle of all Observation resources for specific vital sign(s) listed in the table above for the specified patient [(how to search by reference)] and [how to search by token)]. 2) The Observation "code" parameter searches both in both Observation.code and Observation.component.code. For example when fetching blood pressures the same resources will be returned whether the search is based on 55284-4(Systolic and Diastolic BP), or the component codes 8480-6(Systolic BP) or 8462-4 (Diastolic BP).


*Response Class:*

-   (Status 200): successful operation
-   (Status 400): invalid parameter
-   (Status 401/4xx): unauthorized request
-   (Status 403): insufficient scope

-----------

`GET [base]/Observation?patient=[id]&category=vital-signs&date=[date]{&date=[date]}`

**Example:**
Find all the blood pressures after 2013-03-14

[GET http://fhir2.healthintersections.com.au/open/Observation?patient=555580&code=55284-4&date=ge2015-01-14](http://fhir2.healthintersections.com.au/open/Observation?patient=555580&code=55284-4&date=ge2015-01-14)

*Support:*  Mandatory to support search by category code and date

*Implementation Notes:*  Search based on vital sign category code and date. This fetches a bundle of all Observation resources with category 'vital-signs' for the specified patient for a specified time period  [(how to search by reference)] and [(how to search by token)].

*Response Class:*

-   (Status 200): successful operation
-   (Status 400): invalid parameter
-   (Status 401/4xx): unauthorized request
-   (Status 403): insufficient scope

--------


  [(how to search by reference)]: http://build.fhir.org/search.html#reference
  [(how to search by token)]: http://build.fhir.org/search.html#token
  [Composite Search Parameters]: http://build.fhir.org/search.html#combining
  [(how to search by date)]: http://build.fhir.org/search.html#date
  [(how to search by string)]: http://build.fhir.org/search.html#string
