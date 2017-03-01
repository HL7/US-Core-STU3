

`GET [base]/DiagnosticReport?patient=[id]&category=LAB`

**Example:** GET [base]/DiagnosticReport?patient=f201&category=LAB

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
-  Search for all metabolic panel reports (LOINC = 24323-8 *Comprehensive metabolic 2000 panel - Serum or Plasma*) for a patient
  - GET [base]/DiagnosticReport?patient=1032702&code=24323-8


- Search for all cbc (LOINC = 58410-2 *Complete blood count (hemogram) panel - Blood by Automated count*), metabolic panel, and urinalysis panels (LOINC = 24356-8 *Urinalysis complete panel - Urine*) for a patient
  - GET [base]/DiagnosticReport?patient=1032702&code=24323-8,58410-2,24356-8

*Support:* Mandatory support search by a laboratory order code. SHOULD support search by multiple order codes.

*Implementation Notes:* Search based on DiagnosticReport code(s). This fetches a bundle of all DiagnosticReport resources for a specific diagnostic order code(s) for the specified patient  [(how to search by reference)] and [(how to search by token)].

*Response Class:*

-   (Status 200): successful operation
-   (Status 400): invalid parameter
-   (Status 401/4xx): unauthorized request
-   (Status 403): insufficient scope
-----------

`GET [base]/DiagnosticReport?patient=[id]&category=LAB&date=[date]{&date=[date]}`

**Example:** Find all the lab reports issued after 2010-01-14

- GET [base]/DiagnosticReport?patient=f201&category=LAB&date=ge2010-01-14

*Support:*  Mandatory support search by category code = 'LAB' and date or period.

*Implementation Notes:*  Search based on laboratory category code and date. This fetches a bundle of all DiagnosticReport resources with category 'LAB' for the specified patient for a specified time period   [(how to search by reference)], [(how to search by token)] amd [(how to search by date)].

*Response Class:*

-   (Status 200): successful operation
-   (Status 400): invalid parameter
-   (Status 401/4xx): unauthorized request
-   (Status 403): insufficient scope

  [(how to search by reference)]: http://build.fhir.org/search.html#reference
  [(how to search by token)]: http://build.fhir.org/search.html#token
  [Composite Search Parameters]: http://build.fhir.org/search.html#combining
  [(how to search by date)]: http://build.fhir.org/search.html#date
