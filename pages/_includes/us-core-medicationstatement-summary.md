#### Complete Summary of the Mandatory Requirements


1.  One status in `MedicationStatement.status` which has a [required](http://hl7.org/fhir/2017Jan/terminologies.html#required) binding to:
-   [MedicationStatementStatus] value set.
1.  One medication via `MedicationStatement.medicationCodeableConcept` or `MedicationStatement.medicationReference`   
-  `MedicationStatement.medicationCodeableConcept` has an [extensible](http://hl7.org/fhir/2017Jan/terminologies.html#extensible) binding to [Medication Clinical Drug (RxNorm)] value set.
1.  One date `MedicationStatement.dateAsserted`
1.  One patient reference in `MedicationStatement.subject`
1.  One medication taken code in `MedicationStatement.taken` which has a [required](http://hl7.org/fhir/2017Jan/terminologies.html#required) binding to:
-   [MedicationStatementTaken] value set.

#### Summary of the Must Support Requirements

1.  One date or period in `MedicationStatement.effectiveDateTime` or `MedicationStatment.effectivePeriod`


  [Medication Clinical Drug (RxNorm)]: ValueSet-us-core-medication-codes.html
  [MedicationStatusStatus]: http://hl7.org/fhir/2017Jan/valueset-medication-request-status.html

[MedicationStatementStatus]: http://hl7.org/fhir/valueset-medication-statement-status.html
[MedicationStatementTaken]: http://hl7.org/fhir/valueset-medication-statement-taken.html
