#### Complete Summary of the Mandatory Requirements 


1.  One or more Encounter numbers in `Encounter.identifier`
    -   each Encounter.identifier must have:
        -   an `identifier.system`
        -   an `identifier.value` that is unique within the system.

2.  One status in `Encounter.status`
  
3.  At least one type in `Encounter.type` *ADD VALUE SET*

4.  One patient reference in `Encounter.subject`


#### Summary of the Must Support Requirements

Additionally your system must Support:

1.  The class of the Encounter in `Encounter.class` from [EncounterCode]({{site.data.fhir.path}}/v3/ActEncounterCode/vs.html) value set
2.  Participant
3.  Period
4.  Reason
5.  Diagnosis.condition
6.  Hospitlization - dischargeDisposition
7.  Location





  [Patient.birthDate]: {{site.data.fhir.path}}/us/daf/daf-patient-guidance.html#daf-patient.Patient.birthDate
  [Patient.communication.language]: {{site.data.fhir.path}}/us/daf/daf-patient-guidance.html#daf-patient.Patient.communication.language
  [All Language codes with language and optionally a region modifier]: ValueSet-simple-language.html
  [All Languages]: {{site.data.fhir.path}}/valueset-all-languages.html
  [US Core Patient Birth Sex]:StructureDefinition-us-core-birthsex.html
  [US Core Birth Sex]: ValueSet-us-core-birthsex.html
  [US Core Patient Race]: StructureDefinition-us-core-race.html
  [OMB Race Categories]: ValueSet-omb-race-category.html
  [US Core Race Extension]:StructureDefinition-us-core-race.html
  [CDC Race Codes]:ValueSet-detailed-race.html
 [CDC Ethnicity Codes]: ValueSet-detailed-ethnicity.html
 [US Core ethnicity Extension]:StructureDefinition-us-core-ethnicity.html
 [OMB Ethnicity Categories]: ValueSet-omb-ethnicity-category.html
