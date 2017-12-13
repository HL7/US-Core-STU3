#### Complete Summary of the Mandatory Requirements 

1.  One status in `Encounter.status`  
2.  A class in `Encounter.class` from [EncounterCode]({{site.data.fhir.path}}/v3/ActEncounterCode/vs.html) value set.
3.  At least one type in `Encounter.type` from [US Core Encounter Type](valueSet-us-core-encounter-type.html) value set.
4.  One patient reference in `Encounter.subject`


#### Summary of the Must Support Requirements

Additionally your system must Support:

1.  One or more Encounter numbers in `Encounter.identifier`
2.  One or more participants in `Encounter.participant`
3.  An `Encounter.period`
4.  One or more reasons in `Encounter.reason` from [EncounterReason]({{site.data.fhir.path}}/valueset-encounter-reason.html) value set.
5.  One or more `Encounter.diagnosis.condition`
6.  A disposition in `Encounter.hospitlization.dischargeDisposition` from example [dischargeDisposition]({{site.data.fhir.path}}/valueset-encounter-discharge-disposition.html) value set.
7.  One or more locations in `Encounter.location`



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
