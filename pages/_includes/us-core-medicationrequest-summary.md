#### Complete Summary of the Mandatory Requirements

1.  One status in `MedicationRequest.status` which has a [required](http://build.fhir.org/terminologies.html#required) binding to:
-   [MedicationRequestStatus] value set
1.  One medication via `MedicationRequest.medicationCodeableConcept` or `MedicationRequest.medicationReference`   
     -  `MedicationRequest.medicationCodeableConcept` has an [extensible](http://build.fhir.org/terminologies.html#extensible) binding to [Medication Clinical Drug (RxNorm)]
1.  One patient reference in `MedicationRequest.patient`
1.  One date in `MedicationRequest.authoredOn`
1.  One practitioner in `MedicationRequest.requester`


  [Medication Clinical Drug (RxNorm)]: ValueSet-us-core-medication-codes.html
  [MedicationRequestStatus]: http://build.fhir.org/valueset-medication-request-status.html
[MedicationStatementStatus]: http://build.fhir.org/valueset-medication-statement-status.html
