#### Complete Summary of the Mandatory Requirements


1.  One status in `DiagnosticReport.status` which has an [required](http://build.fhir.org/terminologies.html#required) binding to:
    -   [DiagnosticReportStatus] value set.
1.  One category in `DiagnosticReport.category` which must have:
    -   a fixed `DiagnosticReport.category.coding.system`= "http://hl7.org/fhir/DiagnosticReport-category”
    -   a fixed `DiagnosticReport.category.coding.code`= "LAB"
1.  One code in `DiagnosticReport.code` which has an [extensible](http://build.fhir.org/terminologies.html#extensible) binding to:
    -   [LOINC Diagnostic Report Codes]
    -   Other additional codes are allowed - e.g. system specific codes. All codes *SHALL* have an system value
1.  One patient in `DiagnosticReport.subject`
1.  A date and time in `DiagnosticReport.effectiveDateTime` or `DiagnosticReport.effectivePeriod`
1.  A date and time in `DiagnosticReport.issued`
1.  One or more `DiagnosticReport.result` and/or one or more `DiagnosticReport.presentedForm`

Each DiagnosticReport *SHOULD* have:

1.  A practitioner or organization in `DiagnosticReport.performer`

[DiagnosticReportStatus]: http://build.fhir.org/valueset-diagnostic-report-status.html
[Observation]: http://build.fhir.org/observation.html
[LOINC Diagnostic Report Codes]: http://build.fhir.org/valueset-report-codes.html
