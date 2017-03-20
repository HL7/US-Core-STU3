
`GET /Condition?patient=[id]`

**Example:** GET [base]/Condition?patient=1032702

*Support:* Mandatory to support search by patient.

*Implementation Notes:*  Search for all problems and health concerns for a patient. Fetches a bundle of all Condition resources for the specified patient. [(how to search by reference)] and [(how to search by token)].


-----------

`GET /Condition?patient=[id]&clinicalstatus=active,recurrance,remission`

**Example:** GET [base]/Condition?patient=1032702&clinicalstatus=active,relapse,remission

*Support:* Optional to support search by status.

*Implementation Notes:* Search for all active problems and health concerns for a patient. Fetches a bundle of all Condition resources for the specified patient and all "active" statuses (active,relapse,remission)  [(how to search by reference)] and [(how to search by token)]. This will not return any "entered in error" resources because of the conditional presence of the clinicalStatus element.


-----------
`GET /Condition?patient=[id]&category=problem`

**Example:** GET [base]/Condition?patient=1032702&category=problem

*Support:* Optional to support search by patient and category.

*Implementation Notes:*  earch for all Problems for a patient. Fetches a bundle of all Condition resources for the specified patient with a category code of "problem" [(how to search by reference)] and [(how to search by token)].


-----------

`GET /Condition?patient=[id]&category=health-concern`


**Example:** GET [base]/Condition?patient=1032702&category=health-concern

*Support:* Optional to support search by patient and category.

*Implementation Notes:*  Search for all Health Concerns for a patient. Fetches a bundle of all Condition resources for the specified patient with a category code of "health-concern"[(how to search by reference)] and [(how to search by token)].


-----------


  [(how to search by reference)]: http://hl7.org/fhir/STU3/search.html#reference
  [(how to search by token)]: http://hl7.org/fhir/STU3/search.html#token
  [Composite Search Parameters]: http://hl7.org/fhir/STU3/search.html#combining
  [(how to search by date)]: http://hl7.org/fhir/STU3/search.html#date
  [(how to search by string)]: http://hl7.org/fhir/STU3/search.html#string
