

`GET [base]/DiagnosticReport?patient=[id]&category=LAB`

**Example:**

[GET http://spark.furore.com/fhir/DiagnosticReport?patient=f201&category=LAB](http://spark.furore.com/fhir/DiagnosticReport?patient=f201&category=LAB)


*Support:* Mandatory to support search by patient and category code = 'LAB'.

*Implementation Notes:* Search based on diagnostic report category code = 'LAB'. This fetches a bundle of all lab related DiagnosticReport resources for the specified patient  [(how to search by reference)] and [(how to search by token)].



*Response Class:*

-   (Status 200): successful operation
-   (Status 400): invalid parameter
-   (Status 401/4xx): unauthorized request
-   (Status 403): insufficient scope


-----------

`GET [base]/DiagnosticReport?patient=[id]&code=[LOINC{,LOINC2,LOINC3,...}]`
**Example:**
Search for all metabolic panel reports for a patient

[GET https://fhir-open-api-dstu2.smarthealthit.org/DiagnosticReport?patient=1032702&code=24323-8](https://fhir-open-api-dstu2.smarthealthit.org/DiagnosticReport?patient=1032702&code=24323-8)

**Example:**
Search for all cbc, metabolic panel, and urinalysis panels for a patient

[GET https://fhir-open-api-dstu2.smarthealthit.org/DiagnosticReport?patient=1032702&code=24323-8,58410-2,24356-8](https://fhir-open-api-dstu2.smarthealthit.org/DiagnosticReport?patient=1032702&code=24323-8,58410-2,24356-8)

*Support:* Mandatory support search by a laboratory order code. SHOULD support search by multiple order codes.

*Implementation Notes:* Search based on DiagnosticReport code(s). This fetches a bundle of all DiagnosticReport resources for a specific diagnostic order code(s) for the specified patient  [(how to search by reference)] and [(how to search by token)].

*Response Class:*

-   (Status 200): successful operation
-   (Status 400): invalid parameter
-   (Status 401/4xx): unauthorized request
-   (Status 403): insufficient scope
-----------

`GET [base]/DiagnosticReport?patient=[id]&category=LAB&date=[date]{&date=[date]}`

**Example:**
Find all the lab reports issued after 2010-01-14

[GET http://spark.furore.com/fhir/DiagnosticReport?patient=f201&category=LAB&date=ge2010-01-14](http://spark.furore.com/fhir/DiagnosticReport?patient=f201&category=LAB&date=ge2010-01-14)

*Support:*  Mandatory support search by category code = 'LAB' and date or period.

*Implementation Notes:*  Search based on laboratory category code and date. This fetches a bundle of all DiagnosticReport resources with category 'LAB' for the specified patient for a specified time period   [(how to search by reference)], [(how to search by token)] amd [(how to search by date)].

*Response Class:*

-   (Status 200): successful operation
-   (Status 400): invalid parameter
-   (Status 401/4xx): unauthorized request
-   (Status 403): insufficient scope

  [(how to search by reference)]: http://hl7.org/fhir/2017Jan/search.html#reference
  [(how to search by token)]: http://hl7.org/fhir/2017Jan/search.html#token
  [Composite Search Parameters]: http://hl7.org/fhir/2017Jan/search.html#combining
  [(how to search by date)]: http://hl7.org/fhir/2017Jan/search.html#date
