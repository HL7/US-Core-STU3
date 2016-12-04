

-------------------------
**Clients**

-  A client has connected to a server and fetched a patient's medications using:

1. `GET /MedicationRequest?patient=[id]` or
1. `GET /MedicationRequest?patient=[id]&_include=MedicationRequest:medication`

**Servers**

- A server is capable of returning a patient's medications using one of or both

1. `GET /MedicationRequest?patient=[id]`
1. `GET /MedicationRequest?patient=[id]&_include=MedicationRequest:medication`


- A server has ensured that every API request includes a valid Authorization token, supplied via:Authorization: Bearer {server-specific-token-here}
- A server has rejected any unauthorized requests by returning an HTTP 401 Unauthorized response code.

-----------

`GET /MedicationRequest?patient={id}`

*Support:* Mandatory for client to support search by patient.  Optional for server to support.

*Implementation Notes:*  Used when the server application represents the medication using either an inline code or a contained Medication resource. This searches for all MedicationRequest resources for a patient and returns a Bundle of all MedicationRequest resources for the specified patient.  [(how to search by reference)].

*Response Class:*

-   (Status 200): successful operation
-   (Status 400): invalid parameter
-   (Status 401/4xx): unauthorized request
-   (Status 403): insufficient scope

**Example:**

[GET http://fhirtest.uhn.ca/baseDstu2/MedicationRequest?patient=14676](http://fhirtest.uhn.ca/baseDstu2/MedicationRequest?patient=14676)

-----------

`GET /MedicationRequest?patient={id}&_include=MedicationRequest:medication`

*Support:* Mandatory for client to support search by patient using the include parameter.  Optional for server to support.

*Implementation Notes:*  Used when the server application represents the medication with an external reference to  a Medication resource. This searches for all MedicationRequest resources for a patient and returns a Bundle of all MedicationRequest and Medication resources for the specified patient.  [(how to search by reference)].

*Response Class:*

-   (Status 200): successful operation
-   (Status 400): invalid parameter
-   (Status 401/4xx): unauthorized request
-   (Status 403): insufficient scope

**Example:**

[GET http://fhirtest.uhn.ca/baseDstu2/MedicationRequest?patient=14676&_include=MedicationRequest:medication](http://fhirtest.uhn.ca/baseDstu2/MedicationRequest?patient=14676&_include=MedicationRequest:medication)

-----

  [(how to search by reference)]: http://build.fhir.org/search.html#reference
  [(how to search by token)]: http://build.fhir.org/search.html#token
  [Composite Search Parameters]: http://build.fhir.org/search.html#combining
  [(how to search by date)]: http://build.fhir.org/search.html#date
