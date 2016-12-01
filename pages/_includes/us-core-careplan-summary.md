#### Complete Summary of the Mandatory Requirements

1.  A narrative summary in `CarePlan.text`
    -   `[CarePlan.text.status]` is either “generated” or “additional”
1.  One status in `CarePlan.status`
    -   CarePlan.status is bound to [CarePlanStatus] Value set (Code set)
1.  One category in `Careplan.category` which must have:
    -   a fixed `Careplan.category.coding.system`= "http://hl7.org/fhir/us/CodeSystem/careplan-category"
    -   a fixed 'Careplan.category.coding.code'=“assess-plan”
1.  One reference to a patient in `CarePlan.subject`


  [CarePlan.text.status]: http://hl7.org/fhir/valueset-narrative-status.html
  [CarePlanStatus]: http://hl7.org/fhir/valueset-care-plan-status.html
 [http://hl7.org/fhir/us/daf/CodeSystem/careplan-category]: CodeSystem-careplan-category.html
