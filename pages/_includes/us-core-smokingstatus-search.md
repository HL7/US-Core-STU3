
`GET [base]/Observation?patient=[id]&code=72166-2`

*Support:* Mandatory to support search by patient and code = '72166-2'.

**Example:** GET [base]/Observation?patient=1032702&code=72166-2

*Implementation Notes:*  Search based on smoking status LOINC code. Fetches a bundle of all Observation resources with Observation.code of Tobacco Smoking Status for the specified patient [(how to search by reference)] and [(how to search by token)].

  [(how to search by reference)]: http://build.fhir.org/search.html#reference
  [(how to search by token)]: http://build.fhir.org/search.html#token
  [Composite Search Parameters]: http://build.fhir.org/search.html#combining
  [(how to search by date)]: http://build.fhir.org/search.html#date
  [(how to search by string)]: http://build.fhir.org/search.html#string

