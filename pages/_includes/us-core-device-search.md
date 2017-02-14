
`GET /Device?patient=[id]`

**Example:**

[GET http://fhir2.healthintersections.com.au/open/Device/uscore-udi-1](http://fhir2.healthintersections.com.au/open/Device/uscore-udi-1)



*Support:* Mandatory to support search by patient.

*Implementation Notes:* Search for all implantable device UDIs for a patient. Fetches a bundle of all Device resources for the specified patient [(how to search by reference)].



*Response Class:*

-   (Status 200): successful operation
-   (Status 400): invalid parameter
-   (Status 401/4xx): unauthorized request
-   (Status 403): insufficient scope


  [(how to search by reference)]: http://build.fhir.org/search.html#reference
  [(how to search by token)]: http://build.fhir.org/search.html#token
  [Composite Search Parameters]: http://build.fhir.org/search.html#combining
  [(how to search by date)]: http://build.fhir.org/search.html#date
