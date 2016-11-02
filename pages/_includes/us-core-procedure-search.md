



-------------------------

**Clients**

-  A client connected to a server and fetched all procedures for a patient, including current as well as historical Procedures `GET/Procedure?patient=[id]`.
- A client has connected to a server and fetched all of a patient's procedures over a specified time period using `GET /Procedure?patient=[id]&date=[date]{&date=[date]}`.

**Servers**

-  A server is capable of returning a patient's procedures using `GET/Procedure?patient=[id]`.
- A server is capable of returning all of all of a patient's procedures over a specified time period using `GET /Procedure?patient=[id]&date=[date]{&date=[date]}`.


-   A server has ensured that every API request includes a valid Authorization token, supplied via:Authorization: Bearer {server-specific-token-here}
-   A server has rejected any unauthorized requests by returning an HTTP 401 Unauthorized response code.

-----------

**GET /Procedure?patient=[id][edit]**

*Support:* Mandatory to support search by patient.

*Implementation Notes:* Search for all Procedures for a patient. Fetches a bundle of all Procedure resources for the specified patient. [(how to search by reference)].

*Response Class:*

-   (Status 200): successful operation
-   (Status 400): invalid parameter
-   (Status 401/4xx): unauthorized request
-   (Status 403): insufficient scope

*Example:*

[GET https://fhir-open-api-dstu2.smarthealthit.org/Procedure?patient=1291938](https://fhir-open-api-dstu2.smarthealthit.org/Procedure?patient=1291938)

-----------


**GET /Procedure?patient=[id]&date=[date]{&date=[date]}**

*Support:* Mandatory to support search by patient and date or period.

*Implementation Notes:* Search based on date. Fetches a bundle of all Procedure resources for the specified patient for a specified time period [(how to search by reference)] and [(how to search by date)].

*Response Class:*

-   (Status 200): successful operation
-   (Status 400): invalid parameter
-   (Status 401/4xx): unauthorized request
-   (Status 403): insufficient scope

*Example:*

[GET http://fhir2.healthintersections.com.au/open/Procedure?example&date=ge2002](http://fhir2.healthintersections.com.au/open/Procedure?example&date=ge2002)

[GET http://fhir2.healthintersections.com.au/open/Procedure?example&date=ge2010$date=le2015](http://fhir2.healthintersections.com.au/open/Procedure?example&date=ge2010$date=le2015)



  [(how to search by reference)]: http://hl7.org/fhir/DSTU2/search.html#reference
  [(how to search by token)]: http://hl7.org/fhir/DSTU2/search.html#token
   [(how to search by date)]: http://hl7.org/fhir/DSTU2/search.html#date
