

-------------------------

**Clients**

-  A client has connected to a server and fetched all Unique device identifier(s)(UDI)for a patient’s implantable device(s)using `GET /Device?patient=[id]`.


**Servers**

- A server is capable of returning all Unique device identifier(s)(UDI) for a patient’s implantable device(s) using `GET /Device?patient=[id]`.


- A server has ensured that every API request includes a valid Authorization token, supplied via:Authorization: Bearer {server-specific-token-here}
- A server has rejected any unauthorized requests by returning an HTTP 401 Unauthorized response code.

-----------

`GET /Device?patient=[id]`

*Support:* Mandatory to support search by patient.

*Implementation Notes:* Search for all implantable device UDIs for a patient. Fetches a bundle of all Device resources for the specified patient [(how to search by reference)].



*Response Class:*

-   (Status 200): successful operation
-   (Status 400): invalid parameter
-   (Status 401/4xx): unauthorized request
-   (Status 403): insufficient scope

**Example:**

GET http://fhir2.healthintersections.com.au/open/Device/argo-udi-1


  [(how to search by reference)]: http://hl7.org/fhir/DSTU2/search.html#reference
  [(how to search by token)]: http://hl7.org/fhir/DSTU2/search.html#token
  [Composite Search Parameters]: http://hl7-fhir.github.io/search.html#combining
  [(how to search by date)]: http://hl7.org/fhir/DSTU2/search.html#date
