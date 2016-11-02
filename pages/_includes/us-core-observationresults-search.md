

-------------------------

**Clients**

-  A client has connected to a server and fetched all of a patient's laboratory results by searching by category using `GET [base]/Observation?patient=[id]&category=laboratory`.
- A client has connected to a server and fetched all of a patient's laboratory results searching by category code and date range using `GET [base]/Observation?patient=[id]&category=laboratory&date=[date]{&date=[date]}`.
- A client has connected to a server and fetched all of all of a patient's laboratory results searching by category and code using `GET [base]/Observation?patient=[id]&category=laboratory&code=[LOINC]`.


 - A client **SHOULD** be capable of connecting to a server and fetching any of a patient's laboratory results searching by category and one or more codes and date range using `GET [base]/Observation?patient=[id]&category=laboratory&code=[LOINC1{,LOINC2,LOINC3,...}]&date=[date]{&date=[date]}`.

**Servers**

- A server is capable of returning all of a patient's laboratory results queried by category using `GET [base]/Observation?patient=[id]&category=laboratory`.
 - A server is capable of returning all of a patient's laboratory results queried by category code and date range using`GET [base]/Observation?patient=[id]&category=laboratory&date=[date]{&date=[date]}`.
- A server is capable of returning all of a patient's laboratory results queried by category and code using `GET [base]/Observation?patient=[id]&category=laboratory&code=[LOINC]`.


- A server **SHOULD** be capable of returning all of a patient's laboratory results queried by category and one or more codes and date range using `GET [base]/Observation?patient=[id]&category=laboratory&code=[LOINC1{,LOINC2,LOINC3,...}]&date=[date]{&date=[date]}`.


- A server has ensured that every API request includes a valid Authorization token, supplied via:Authorization: Bearer {server-specific-token-here}
- A server has rejected any unauthorized requests by returning an HTTP 401 Unauthorized response code.

-----------

`GET [base]/Observation?patient=[id]&category=laboratory`

*Support:* Mandatory to support search by patient and category code = 'laboratory'.

*Implementation Notes:* Search based on laboratory category code = "laboratory". This fetches a bundle of all Observation resources with laboratory categories for the specified patient [(how to search by reference)] and [(how to search by token)].



*Response Class:*

-   (Status 200): successful operation
-   (Status 400): invalid parameter
-   (Status 401/4xx): unauthorized request
-   (Status 403): insufficient scope

**Example:**

GET https://fhir-open-api-dstu2.smarthealthit.org/Observation?patient=1134281&category=laboratory

-----------

`GET [base]/Observation?patient=[id]&code=[LOINC{,LOINC2,LOINC3,...}]`

*Support:* Mandatory support search by a laboratory LOINC code. SHOULD support search by multiple LOINC codes.

*Implementation Notes:* 1) Search based on laboratory LOINC code(s). This fetches a bundle of all Observation resources for a specific observation LOINC code(s) for the specified patient  [(how to search by reference)] and [(how to search by token)].   2) The Argonaut Observation "code" parameter has been defined to search both in both Observation.code and Observation.component.code.



*Response Class:*

-   (Status 200): successful operation
-   (Status 400): invalid parameter
-   (Status 401/4xx): unauthorized request
-   (Status 403): insufficient scope

**Example:**
Search for all blood glucose lab results for a patient:

GET https://fhir-open-api-dstu2.smarthealthit.org/Observation?patient=1134281&code=2339-0

**Example:**
Search for all blood glucose, urine glucose and urine ketones for a patient

GET https://fhir-open-api-dstu2.smarthealthit.org/Observation?patient=1134281&code=2339-0,25428-4,2514-8

-----------

`GET [base]/Observation?patient=[id]&category=laboratory&date=[date]{&date=[date]}`

*Support:*  Mandatory support search by category code ="laboratory" and date or period



*Implementation Notes:*  Search based on laboratory category code and date. This fetches a bundle of all Observation resources with category 'laboratory' for the specified patient for a specified time period  [(how to search by reference)], [(how to search by token)] amd [(how to search by date)].



*Response Class:*

-   (Status 200): successful operation
-   (Status 400): invalid parameter
-   (Status 401/4xx): unauthorized request
-   (Status 403): insufficient scope

**Example:**
Find all the laboratory results after 2013-03-14

GET http://fhir2.healthintersections.com.au/open/Observation?patient=555580&category=laboratory&date=ge2015-01-14

  [(how to search by reference)]: http://hl7.org/fhir/DSTU2/search.html#reference
  [(how to search by token)]: http://hl7.org/fhir/DSTU2/search.html#token
  [Composite Search Parameters]: http://hl7-fhir.github.io/search.html#combining
  [(how to search by date)]: http://hl7.org/fhir/DSTU2/search.html#date
