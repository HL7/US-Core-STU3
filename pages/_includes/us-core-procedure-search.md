
**`GET /Procedure?patient=[id][edit]`**

**Example:** GET [base]/Procedure?patient=1291938

*Support:* Mandatory to support search by patient.

*Implementation Notes:* Search for all Procedures for a patient. Fetches a bundle of all Procedure resources for the specified patient. [(how to search by reference)].


-----------
**`GET /Procedure?patient=[id]&date=[date]{&date=[date]}`**

**Example:** [GET [base]Procedure?example&date=ge2002](http://fhir2.healthintersections.com.au/open/Procedure?example&date=ge2002)

**Example:** [GET [base]Procedure?example&date=ge2010$date=le2015](http://fhir2.healthintersections.com.au/open/Procedure?example&date=ge2010&date=le2015)

*Support:* Mandatory to support search by patient and date or period.

*Implementation Notes:* Search based on date. Fetches a bundle of all Procedure resources for the specified patient for a specified time period [(how to search by reference)] and [(how to search by date)].



  [(how to search by reference)]: http://hl7.org/fhir/STU3/search.html#reference
  [(how to search by token)]: http://hl7.org/fhir/STU3/search.html#token
   [(how to search by date)]: http://hl7.org/fhir/STU3/search.html#date
