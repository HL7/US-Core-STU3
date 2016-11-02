

-------------------------

**Clients**

- A client has connected to a server and fetched a patient's smoking status using `GET [base]/Observation?patient=[id]&code=72166-2`.


**Servers**

- A server is capable of returning a a patient's smoking status using `GET [base]/Observation?patient=[id]&code=72166-2`.


- A server has ensured that every API request includes a valid Authorization token, supplied via:Authorization: Bearer {server-specific-token-here}
- A server has rejected any unauthorized requests by returning an HTTP 401 Unauthorized response code.

-----------
`GET [base]/Observation?patient=[id]&code=72166-2[edit]`

*Support:* Mandatory to support search by patient and LOINC = '72166-2'.

*Implementation Notes:*  Search based on smoking status LOINC code. Fetches a bundle of all Observation resources with Observation.code of Tobacco Smoking Status for the specified patient [(how to search by reference)] and [(how to search by token)].

*Response Class:*

-   (Status 200): successful operation
-   (Status 400): invalid parameter
-   (Status 401/4xx): unauthorized request
-   (Status 403): insufficient scope


**Example:**

GET https://fhir-open-api-dstu2.smarthealthit.org/Observation?patient=1032702&code=72166-2


  [(how to search by reference)]: http://hl7.org/fhir/DSTU2/search.html#reference
  [(how to search by token)]: http://hl7.org/fhir/DSTU2/search.html#token
  [Composite Search Parameters]: http://hl7-fhir.github.io/search.html#combining
  [(how to search by date)]: http://hl7.org/fhir/DSTU2/search.html#date
  [(how to search by string)]: http://hl7.org/fhir/DSTU2/search.html#string
