Both the [MedicationRequest] and [MedicationStatement] resources can be used to record a patient's medication.   For more information about the context for their usages, refer to the medication domains's [boundaries section].  This profile sets minimum expectations for the MedicationRequest resource to record, search and fetch medications associated with a patient. It identifies which core elements, extensions, vocabularies and value sets **SHALL** be present in the resource when using this profile.

**Example Usage Scenarios:**

The following are example usage scenarios for the US Core-MedicationRequest
profile:

-   Query for medications that have been prescribed to a particular
    patient
-   Record medications that have been prescribed to a particular
    patient

##### Mandatory Data Elements and Terminology


The following data-elements are mandatory (i.e data MUST be present). These are presented below in a simple human-readable explanation.  Profile specific guidance and examples are provided as well.  The [**Formal Profile Definition**](#profile) below provides the  formal summary, definitions, and  terminology requirements.  

**Each MedicationRequest must have:**

1.  a status
1.  a medication
1.  a patient
1.  a date for when written
1.  a prescriber


**Profile specific implementation guidance:**

*  The MedicationStatement and MedicationRequest resources can represent a medication, using either a code or refer to a [Medication] resource.
    *  When referencing a Medication resource,  the resource may be [contained] or an external resource.
    *  The server application can choose any one way or more than one method,  but if the an external reference to Medication is used, the server SHALL support the [include] parameter for searching this element.
    *  The client application must support both methods.  
    *  Additional guidance is provided below in the Search section and in the [CapabilityStatement] section.

#### Examples

- [MedicationRequest-uscore-mo1](MedicationRequest-uscore-mo1.html) This example uses an inline medication code to represent the medication.
- [MedicationRequest-uscore-mo2](MedicationRequest-uscore-mo2.html)  This example references a [contained](http://build.fhir.org/references.html#contained) Medication resource.
- [MedicationRequest-uscore-mo3](Bundle-uscore-mo3.html) This example is a search [Bundle](http://build.fhir.org/bundle.html) with a MedicationRequest and an included Medication resource in the Bundle.

  [Medication Clinical Drug (RxNorm)]: ValueSet-us-core-medication-codes.html
  [MedicationRequestStatus]: http://build.fhir.orgus/daf/ValueSet-medication-request-status.html
[MedicationStatementStatus]: http://build.fhir.orgus/daf/ValueSet-medication-statement-status.html
[MedicationStatement]:http://build.fhir.org/medicationstatement.html
 [MedicationRequest]: http://build.fhir.org/medicationrequest.html
 [Medication]:http://build.fhir.org/medication.html
 [CapabilityStatement]: capstmnts.html
 [boundaries section]: http://build.fhir.org/medicationrequest.html#bnr
 [include]: http://build.fhir.org/search.html#include
 [contained]: http://build.fhir.org/references.html#contained
