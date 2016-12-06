#### Complete Summary of the Mandatory Requirements


1.  One or more medical record numbers in `Patient.identifier`
    -   each Patient.identifier must have:
        -   an `identifier.system`
        -   an `identifier.value` that is unique within the system.

2.  One or more names in `Patient.name`
    -   each Patient.name must have:
        -   a `name.family`
        -   a `name.given`

3.  One administrative gender in `Patient.gender`
    -   Patient.gender is bound to [AdministrativeGender] Value set (Code Set)

  [AdministrativeGender]: http://hl7.org/fhir/2017Jan/valueset-administrative-gender.html


#### Summary of the Must Suport Requirements

Additionally your system must return:

1.  A date of birth in `Patient.birthDate`
2.  One or more languages spoken in `Patient.communication.language` which has an [extensible](http://hl7.org/fhir/2017Jan/terminologies.html#extensible) binding to:
    -    [Common Languages] with the extensbility limited to [All Languages]
3.  One or more race codes in  `Patient.extension`= [US Core Race Extension] which:
    - Must include at least one code from [OMB Race Categories]
    - May include additional race codes from [CDC Race Codes]

4.  One or more ethnicity codes in  `Patient.extension`=[US Core ethnicity Extension] which:
    - Must include one code from [OMB Ethnicity Categories]
    - May include additional race codes from [CDC Ethnicity Codes]

5.  One Birth Sex in `Patient.extension`= [US Core Patient Birth Sex] which has an [required](http://hl7.org/fhir/2017Jan/terminologies.html#required) binding to:
    -   [US Core Birth Sex]


  [Patient.birthDate]: http://hl7.org/fhir/us/daf/daf-patient-definitions.html#daf-patient.Patient.birthDate
  [Patient.communication.language]: http://hl7.org/fhir/us/daf/daf-patient-definitions.html#daf-patient.Patient.communication.language
  [Common Languages]: http://hl7.org/fhir/2017Jan/valueset-languages.html
  [All Languages]: http://hl7.org/fhir/2017Jan/valueset-all-languages.html
  [US Core Patient Birth Sex]:StructureDefinition-us-core-birthsex.html
  [US Core Birth Sex]: ValueSet-us-core-birthsex.html
  [US Core Patient Race]: StructureDefinition-us-core-race.html
  [OMB Race Categories]: ValueSet-omb-race.html
  [US Core Race Extension]:StructureDefinition-us-core-race.html
  [CDC Race Codes]:ValueSet-detailed-race.html
 [CDC Ethnicity Codes]: ValueSet-detailed-ethnicity.html
 [US Core ethnicity Extension]:StructureDefinition-us-core-ethnicity.html
 [OMB Ethnicity Categories]: ValueSet-omb-ethnicity.html
