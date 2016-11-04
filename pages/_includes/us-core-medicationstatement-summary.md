#### Complete Summary of the Mandatory Requirements


1.  One status in `MedicationStatement.status` which has an [required](http://build.fhir.org/terminologies.html#required) binding to:
-   [MedicationStatementStatus] value set.
1.  One medication via `MedicationStatement.medicationCodeableConcept` or `MedicationStatement.medicationReference`   
-  `MedicationStatement.medicationCodeableConcept` has an [extensible](http://build.fhir.org/terminologies.html#extensible) binding to [Medication Clinical Drug (RxNorm)] value set.
1.  One patient reference in `MedicationStatement.patient`
1.  One date or period in `MedicationStatement.effectiveDateTime` or `MedicationStatment.effectivePeriod`


  [Medication Clinical Drug (RxNorm)]: valueset-us-core-medication-codes.html
  [MedicationStatusStatus]: http://build.fhir.org/valueset-medication-request-status.html
[MedicationStatementStatus]: http://build.fhir.org/valueset-medication-statement-status.html


