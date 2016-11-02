

-------------------------

**Clients**

-  A client has connected to a server and fetched all of a patient's laboratory diagnostic reports by searching by category using `GET [base]/DiagnosticReport?patient=[id]&category=LAB`.
- A client has connected to a server and fetched all of a patient's laboratory diagnostic reports searching by category code and date range using `GET [base]/DiagnosticReport?patient=[id]&category=LAB&date=[date]{&date=[date]}`.
- A client has connected to a server and fetched all of all of a patient's laboratory diagnostic reports searching by category and code using `GET [base]/DiagnosticReport?patient=[id]&category=LAB&code=[LOINC]`.


- A client **SHOULD** be capable of connecting to a server and fetching any of a patient's laboratory diagnostic reports searching by category and one or more codes and date range using `GET [base]/DiagnosticReport?patient=[id]&category=LAB&code=[LOINC1{,LOINC2,LOINC3,...}]&date=[date]{&date=[date]}`.

**Servers**

- A server is capable of returning all of a patient's laboratory diagnostic reports queried by category using `GET [base]/DiagnosticReport?patient=[id]&category=LAB`.
- A server is capable of returning all of a patient's laboratory diagnostic reports queried by category code and date range using `GET [base]/DiagnosticReport?patient=[id]&category=LAB&date=[date]{&date=[date]}`.
- A server is capable of returning all of a patient's laboratory diagnostic reports queried by category and code using `GET [base]/DiagnosticReport?patient=[id]&category=LAB&code=[LOINC]`.


- A server **SHOULD** be capable of returning all of a patient's laboratory diagnostic reports queried by category and one or more codes and date range using `GET [base]/DiagnosticReport?patient=[id]&category=LAB&code=[LOINC1{,LOINC2,LOINC3,...}]&date=[date]{&date=[date]}`.


- A server has ensured that every API request includes a valid Authorization token, supplied via:Authorization: Bearer {server-specific-token-here}
- A server has rejected any unauthorized requests by returning an HTTP 401 Unauthorized response code.

-----------

`GET [base]/DiagnosticReport?patient=[id]&category=LAB`

*Support:* Mandatory to support search by patient and category code = 'LAB'.

*Implementation Notes:* Search based on diagnostic report category code = 'LAB'. This fetches a bundle of all lab related DiagnosticReport resources for the specified patient  [(how to search by reference)] and [(how to search by token)].



*Response Class:*

-   (Status 200): successful operation
-   (Status 400): invalid parameter
-   (Status 401/4xx): unauthorized request
-   (Status 403): insufficient scope

**Example:**

GET http://spark.furore.com/fhir/DiagnosticReport?patient=f201&category=LAB

-----------

`GET [base]/DiagnosticReport?patient=[id]&code=[LOINC{,LOINC2,LOINC3,...}]`

*Support:* Mandatory support search by a laboratory order code. SHOULD support search by multiple order codes.

*Implementation Notes:* Search based on DiagnosticReport code(s). This fetches a bundle of all DiagnosticReport resources for a specific diagnostic order code(s) for the specified patient  [(how to search by reference)] and [(how to search by token)].



*Response Class:*

-   (Status 200): successful operation
-   (Status 400): invalid parameter
-   (Status 401/4xx): unauthorized request
-   (Status 403): insufficient scope

**Example:**
Search for all metabolic panel reports for a patient

GET https://fhir-open-api-dstu2.smarthealthit.org/DiagnosticReport?patient=1032702&code=24323-8

**Example:**
Search for all cbc, metabolic panel, and urinalysis panels for a patient

GET https://fhir-open-api-dstu2.smarthealthit.org/DiagnosticReport?patient=1032702&code=24323-8,58410-2,24356-8


-----------

`GET [base]/DiagnosticReport?patient=[id]&category=LAB&date=[date]{&date=[date]}`

*Support:*  Mandatory support search by category code = 'LAB' and date or period.

*Implementation Notes:*  Search based on laboratory category code and date. This fetches a bundle of all DiagnosticReport resources with category 'LAB' for the specified patient for a specified time period   [(how to search by reference)], [(how to search by token)] amd [(how to search by date)].



*Response Class:*

-   (Status 200): successful operation
-   (Status 400): invalid parameter
-   (Status 401/4xx): unauthorized request
-   (Status 403): insufficient scope

**Example:**
Find all the lab reports issued after 2010-01-14

GET http://spark.furore.com/fhir/DiagnosticReport?patient=f201&category=LAB&date=ge2010-01-14


  [(how to search by reference)]: http://hl7.org/fhir/DSTU2/search.html#reference
  [(how to search by token)]: http://hl7.org/fhir/DSTU2/search.html#token
  [Composite Search Parameters]: http://hl7-fhir.github.io/search.html#combining
  [(how to search by date)]: http://hl7.org/fhir/DSTU2/search.html#date
