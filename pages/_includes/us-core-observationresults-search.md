
`GET [base]/Observation?patient=[id]&category=laboratory`

**Example:**

[GET https://fhir-open-api-dstu2.smarthealthit.org/Observation?patient=1134281&category=laboratory](https://fhir-open-api-dstu2.smarthealthit.org/Observation?patient=1134281&category=laboratory)

*Support:* Mandatory to support search by patient and category code = 'laboratory'.

*Implementation Notes:* Search based on laboratory category code = "laboratory". This fetches a bundle of all Observation resources with laboratory categories for the specified patient [(how to search by reference)] and [(how to search by token)].



*Response Class:*

-   (Status 200): successful operation
-   (Status 400): invalid parameter
-   (Status 401/4xx): unauthorized request
-   (Status 403): insufficient scope

-----------

`GET [base]/Observation?patient=[id]&code=[LOINC{,LOINC2,LOINC3,...}]`


**Example:**
Search for all blood glucose lab results (LOINC = 2339-0 *Glucose [Mass/volume] in Blood*) for a patient:

[GET https://fhir-open-api-dstu2.smarthealthit.org/Observation?patient=1134281&code=2339-0](https://fhir-open-api-dstu2.smarthealthit.org/Observation?patient=1134281&code=2339-0)

**Example:**
Search for all blood glucose, urine glucose (LOINC = 25428-4 *Glucose [Presence] in Urine by Test strip*) and urine ketones (LOINC = 2339-0 *Ketones [Presence] in Urine by Test strip*) for a patient

[GET https://fhir-open-api-dstu2.smarthealthit.org/Observation?patient=1134281&code=2339-0,25428-4,2514-8](https://fhir-open-api-dstu2.smarthealthit.org/Observation?patient=1134281&code=2339-0,25428-4,2514-8)

*Support:* Mandatory support search by a laboratory LOINC code. SHOULD support search by multiple LOINC codes.

*Implementation Notes:* 1) Search based on laboratory LOINC code(s). This fetches a bundle of all Observation resources for a specific observation LOINC code(s) for the specified patient  [(how to search by reference)] and [(how to search by token)].   2) The Observation "code" parameter searches both in both Observation.code and Observation.component.code.

*Response Class:*

-   (Status 200): successful operation
-   (Status 400): invalid parameter
-   (Status 401/4xx): unauthorized request
-   (Status 403): insufficient scope

-----------

`GET [base]/Observation?patient=[id]&category=laboratory&date=[date]{&date=[date]}`

**Example:**
Find all the laboratory results after 2013-03-14

[GET http://fhir2.healthintersections.com.au/open/Observation?patient=555580&category=laboratory&date=ge2015-01-14](http://fhir2.healthintersections.com.au/open/Observation?patient=555580&category=laboratory&date=ge2015-01-14)

*Support:*  Mandatory support search by category code ="laboratory" and date or period

*Implementation Notes:*  Search based on laboratory category code and date. This fetches a bundle of all Observation resources with category 'laboratory' for the specified patient for a specified time period  [(how to search by reference)], [(how to search by token)] amd [(how to search by date)].

*Response Class:*

-   (Status 200): successful operation
-   (Status 400): invalid parameter
-   (Status 401/4xx): unauthorized request
-   (Status 403): insufficient scope

  [(how to search by reference)]: http://build.fhir.org/search.html#reference
  [(how to search by token)]: http://build.fhir.org/search.html#token
  [Composite Search Parameters]: http://build.fhir.org/search.html#combining
  [(how to search by date)]: http://build.fhir.org/search.html#date
