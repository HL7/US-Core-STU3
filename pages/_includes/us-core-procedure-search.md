
**GET /Procedure?patient=[id][edit]**

*Example:*

[GET https://fhir-open-api-dstu2.smarthealthit.org/Procedure?patient=1291938](https://fhir-open-api-dstu2.smarthealthit.org/Procedure?patient=1291938)

*Support:* Mandatory to support search by patient.

*Implementation Notes:* Search for all Procedures for a patient. Fetches a bundle of all Procedure resources for the specified patient. [(how to search by reference)].

*Response Class:*

-   (Status 200): successful operation
-   (Status 400): invalid parameter
-   (Status 401/4xx): unauthorized request
-   (Status 403): insufficient scope

-----------

**GET /Procedure?patient=[id]&date=[date]{&date=[date]}**

*Example:*

[GET http://fhir2.healthintersections.com.au/open/Procedure?example&date=ge2002](http://fhir2.healthintersections.com.au/open/Procedure?example&date=ge2002)

[GET http://fhir2.healthintersections.com.au/open/Procedure?example&date=ge2010$date=le2015](http://fhir2.healthintersections.com.au/open/Procedure?example&date=ge2010&date=le2015)

*Support:* Mandatory to support search by patient and date or period.

*Implementation Notes:* Search based on date. Fetches a bundle of all Procedure resources for the specified patient for a specified time period [(how to search by reference)] and [(how to search by date)].

*Response Class:*

-   (Status 200): successful operation
-   (Status 400): invalid parameter
-   (Status 401/4xx): unauthorized request
-   (Status 403): insufficient scope


  [(how to search by reference)]: http://build.fhir.org/search.html#reference
  [(how to search by token)]: http://build.fhir.org/search.html#token
   [(how to search by date)]: http://build.fhir.org/search.html#date
