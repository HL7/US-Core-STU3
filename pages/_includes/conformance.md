## US Core Conformance Requirements
{:.no_toc}

This section outlines conformance requirements for the US Core Servers and Client applications, identifying the specific profiles that need to be supported, the specific RESTful operations that need to be supported, and the search parameters that need to be supported. Note: The individual US Core profiles identify the structural constraints, terminology bindings and invariants, however, implementers must refer to the conformance requirements for details on the RESTful operations, specific profiles and the search parameters applicable to each of the US Core actors.

---

<!-- TOC  the css styling for this is \pages\assets\css\project.css under 'markdown-toc'-->
**Contents**

* Do not remove this line (it will not be displayed)
{:toc}

---

<!-- end TOC -->


### Conformance requirements for the US Core Server

Source Resource: [XML](CapabilityStatement-server.xml.html)/[JSON](CapabilityStatement-server.json.html)

1. FHIR Version: 3.0.1
1. Supported formats: xml, json
1. Published: 2017-03-08
1. Published by: Health Level Seven International US Realm Steering Committee

The Section describes the expected capabilities of the US Core Server actor which is responsible for providing responses to the queries submitted by the US Core Requestors. The complete list of FHIR profiles, RESTful operations, and search parameters supported by US Core Servers are defined. Systems implementing this capability statement should meet the ONC 2015 Common Clinical Data Set (CCDS) access requirement for Patient Selection 170.315(g)(7) and Application Access - Data Category Request 170.315(g)(8).  US Core Clients have the option of choosing from this list to access necessary data based on their local use cases and other contextual requirements.

#### Behavior

Description:

The US Core Server **SHALL**:

1. Support the US Core Patient resource profile.
1. Support at least one additional resource profile from the list of US Core Profiles.
1. Implement the RESTful behavior according to the FHIR specification.
1. Return the following response classes:
   - (Status 200): successful operation
   - (Status 400): invalid parameter
   - (Status 401/4xx): unauthorized request
   - (Status 403): insufficient scope
   - (Status 404): unknown resource
   - (Status 410): deleted resource.
1. Support *json* resource formats for all US Core interactions.
1. Declare a CapabilityStatement identifying the list of profiles, operations, search parameter supported.

The US Core Server **SHOULD**:

1. Support *xml* resource formats for all US Core interactions.
1. Identify the US Core profiles supported as part of the FHIR `meta.profile` attribute for each instance.

#### Security:

US Core Servers **SHALL**:

1. Implement the [security requirements](security.html) documented in the this IG.
1. A server has ensured that every API request includes a valid Authorization token, supplied via: `Authorization: Bearer {server-specific-token-here}`
1. A server has rejected any unauthorized requests by returning an `HTTP 401` Unauthorized response code.

#### Profile Interaction Summary:

1. All servers **SHALL** make available the [read]({{site.data.fhir.path}}/http.html#read) and [search]({{site.data.fhir.path}}/http.html#search) interactions for the Profiles the server chooses to support.
1. All servers **SHOULD** make available the [vread]({{site.data.fhir.path}}/http.html#vread) and [history-instance]({{site.data.fhir.path}}/http.html#history) interactions for the Profiles the server chooses to support.

**Summary of US Core search criteria**

Specific server search capabilities are described in detail in each of the resource sections below.

|Resource Type|Supported Profiles|Supported Searches|Supported Includes|
|---|---|---|---|
|[Patient](#1-patient)|US Core Patient Profile |name , family , given , identifier , gender , birthdate , name + gender , name + birthdate , family + gender , given + gender||
|[AllergyIntolerance](#2-allergyintolerance)|US Core AllergyIntolerance Profile |patient ||
|[CarePlan](#3-careplan)|US Core CarePlan Profile |patient , category , status , date, patient + category , patient + category + date , patient + category + status , patient + category + status + date||
|[CareTeam](#4-careteam)|US Core CareTeam Profile |patient , status, patient + status||
|[Condition](#5-condition)|US Core Condition Profile |patient , category , clinicalstatus, patient + clinicalstatus , patient + category||
|[Device](#6-device)|US Core Device Profile |patient ||
|[DiagnosticReport](#7-diagnosticreport)|US Core DiagnosticReport Profile |patient , category , code , date, patient + category , patient + category + date , patient + category + code, patient + category + code + date||
|[DocumentReference](#8-documentreference)|US Core DocumentReference Profile |patient , patient + period + type , patient + date + $docref ||
|[Encounter](#9-encounter)|US Core Encounter Profile |patient , patient + date ||
|[Goal](#10-goal)|US Core Goal Profile |patient , date, patient + date||
|[Immunization](#11-immunization)|US Core Immunization Profile |patient ||
|[Location](#12-location)|US Core Location Profile |name , address ||
|[Medication](#13-medication)|US Core Medication Profile |||
|[MedicationStatement](#14-medicationstatement)|US Core MedicationStatement Profile |patient |MedicationStatement.medication|
|[MedicationRequest](#15-medicationrequest)|US Core MedicationRequest Profile |patient |MedicationRequest.medication|
|[Observation](#16-observation)|US Core Result Observation Profile, Vital Signs Profile, US Core Smoking Status Observation Profile |patient , category , code , date, patient + category , patient + category + date , patient + category + code, patient + category + code + date||
|[Organization](#17-organization)|US Core Organization Profile |identifier , name , address ||
|[Practitioner](#18-practitioner)|US Core Practitioner Profile |identifier , name ||
|[PractitionerRole](#19-practitionerrole)|US Core PractitionerRole Profile |identifier , family + given, specialty ||
|[Procedure](#20-procedure)|US Core Procedure Profile |patient , date , patient + date||
{:.grid}


#### Resource  Details:
{:.no_toc}

##### 1. Patient
{:.no_toc}

Supported Profiles:  [US Core Patient Profile]({{site.data.structuredefinitions.us-core-patient.path}})

Search Criteria:

1. A server **SHALL** be capable of returning a patient using:

  `GET [base]/Patient/[id]`.

1. A server **SHALL** be capable of returning a patient by identifier using

  `GET [base]/Patient?identifier=[system]|[code]`

1. A server **SHALL** be capbable of returning a patient by supporting at a minimum the following search parameters when at least 2 are present:
   - name
   - gender
   - birthdate

      - for example:

       `GET [base]/Patient?name=[name]&gender=[gender]`


Search Parameters:

|Conformance|Parameter|Type|
|---|---|---|
|SHALL|name|string|
|SHALL|identifier|token|
|SHALL|family  + gender|string  + token|
|SHALL|given  + gender|string  + token|
|SHALL|name + gender|string  + token|
|SHALL|name + birthdate|string + date|
{:.grid}

##### 2. AllergyIntolerance
{:.no_toc}

Supported Profiles:  [US Core AllergyIntolerance Profile]({{site.data.structuredefinitions.us-core-allergyintolerance.path}})

Search Criteria:

1. A server **SHALL** be capable of returning all patient's allergies using:

  `Get [base]/AllergyIntolerance?patient=[id]`

Search Parameters:

|Conformance|Parameter|Type|
|---|---|---|
|SHALL|patient|reference|
{:.grid}

##### 3. CarePlan
{:.no_toc}

Supported Profiles:  [US Core CarePlan Profile]({{site.data.structuredefinitions.us-core-careplan.path}})

Search Criteria:

1. A server **SHALL** be capable of returning all of a patient's Assessment and Plan of Treatment information using:

  `Get [base]/CarePlan?patient=[id]&category=assess-plan`

1. A server **SHALL** be capable of returning a patient's Assessment and Plan of Treatment information over a specified time period using:

  `Get [base]/CarePlan?patient=[id]&category=assess-plan&date=[date]`

1. A server **SHOULD** be capable returning all of a patient's active Assessment and Plan of Treatment information using

  `Get [base]/CarePlan?patient=[id]&category=assess-plan&status=active`

1. A server **SHOULD** be capable returning a patient's active Assessment and Plan of Treatment information over a specified time period using

  `Get [base]/CarePlan?patient=[id]&category=assess-plan&status=active&date=[date]`

Search Parameters:

|Conformance|Parameter|Type|Modifiers|
|---|---|---|---|
|SHALL|patient + category|reference + token||
|SHALL|patient + category + date|reference + token + date|date modifiers ‘ge',‘le','gt','lt' |
|SHOULD|patient + category + status|reference + token||
|SHOULD|patient + category + date + status|reference + token + date|date modifiers ‘ge',‘le','gt','lt' |
{:.grid}

##### 4. CareTeam
{:.no_toc}

Supported Profiles:  [US Core CareTeam Profile]({{site.data.structuredefinitions.us-core-careteam.path}})

Search Criteria:

1. A server **SHALL** be capable of returning  a patient's current care team members using:

  `Get [base]/CareTeam?patient=[id]&status=active`

Search Parameters:

|Conformance|Parameter|Type|
|---|---|---|
|SHALL|patient + status|reference + token|
{:.grid}

##### 5. Condition
{:.no_toc}

Supported Profiles:  [US Core Condition Profile]({{site.data.structuredefinitions.us-core-condition.path}})

Search Criteria:

1. A server **SHALL** be capable of returning all problems and health concerns for a patient, including current as well as historical problems and health concerns using:

  `Get [base]/Condition?patient=[id]`

1. A server **SHOULD** be capable returning all of a patient's *active* problems and health concerns using:

  `Get [base]/Condition?patient=[id]&clinicalstatus=active,recurrance,remission`

1. A server **SHOULD** be capable returning all of a patient's problems or all of patient's health concerns using:

  `Get [base]/Condition?patient=[id]&category=[problem|health-concern]`

Search Parameters:

|Conformance|Parameter|Type|
|---|---|---|
|SHALL|patient|reference|
|SHOULD|patient + category|reference + token|
|SHOULD|patient + clinicalstatus|reference + token|
{:.grid}

##### 6. Device
{:.no_toc}

Supported Profiles:  [US Core Device Profile]({{site.data.structuredefinitions.us-core-device.path}})

Search Criteria:

1. A server **SHALL** be capable of returning all Unique device identifier(s)(UDI) for a patient's implanted device(s):

  `Get [base]/Device?patient=[id]`

Search Parameters:

|Conformance|Parameter|Type|
|---|---|---|
|SHALL|patient|reference|
{:.grid}

##### 7. DiagnosticReport
{:.no_toc}

Supported Profiles:  [US Core DiagnosticReport Profile]({{site.data.structuredefinitions.us-core-diagnosticreport.path}})

Search Criteria:

1. A server **SHALL** be capable of returning all of a patient's laboratory diagnostic reports queried by category using:

  `Get [base]/DiagnosticReport?patient=[id]&category=LAB`

1. A server **SHALL** be capable of returning all of a patient's laboratory diagnostic reports queried by category code and date range using:

  `GET [base]/DiagnosticReport?patient=[id]&category=LAB&date=[date]{&date=[date]}`

1. A server **SHALL** be capable of returning all of a patient's laboratory diagnostic reports queried by category and code using:

  `GET [base]/DiagnosticReport?patient=[id]&category=LAB&code=[LOINC]`

1. A server **SHOULD** be capable of returning all of a patient's laboratory diagnostic reports queried by category and one or more codes and date range using:

  `GET [base]/DiagnosticReport?patient=[id]&category=LAB&code=[LOINC1{,LOINC2,LOINC3,…}]&date=[date]{&date=[date]}`

Search Parameters:

|Conformance|Parameter|Type|Modifiers|
|---|---|---|---|
|SHALL|patient + category|reference + token||
|SHALL|patient + category + code|reference + token||
|SHALL|patient + category + date|reference + token + date|date modifiers ‘ge',‘le','gt','lt' |
|SHOULD|patient + category + code + date|reference + token + date|date modifiers ‘ge',‘le','gt','lt' |
{:.grid}

##### 8. DocumentReference
{:.no_toc}

Supported Profiles:  [US Core DocumentReference Profile]({{site.data.structuredefinitions.us-core-documentreference.path}})

Search Criteria:

  1. A server **SHALL** be capable of returning all of a patient's DocumentReferences using:

  `GET [base]/DocumentReference?patient=[id]`

  1. A server **SHALL** be capable of responding to a [$docref](OperationDefinition-docref.html) operation. At minimum, it must return a reference to a CCD document.

  `GET [base]/DocumentReference/$docref?patient=[id]`

  1. A server **SHOULD** be capable of returning all of all of a patient's DocumentReferences for a given time period and document type:

  `GET [base]/DocumentReference?patient=[id]&type=[type]&period=[date]{&date=[date]}`

Search Parameters:

|Conformance|Parameter|Type|Modifiers|
|---|---|---|---|
|SHALL|patient|reference||
|SHALL|patient + $docref|reference + oepration||
|SHOULD|patient + type + period|reference + token + date|date modifiers ‘ge',‘le','gt','lt'|
{:.grid}

##### 9. Encounter
{:.no_toc}

Supported Profiles:  [US Core Encounter Profile]({{site.data.structuredefinitions.us-core-encounter.path}})

Search Criteria:

1. A server **SHALL** be capable of returning all of a patient's encounters using:

  `GET [base]/Encounter?patient=[id]`

1. A server **SHALL** be capable of returning all of all of a patient's encounters over a specified time period using:

  `GET [base]/Encounter?patient=[id]&date=[date]{&date=[date]}`

Search Parameters:

|Conformance|Parameter|Type|Modifiers|
|---|---|---|---|
|SHALL|patient|reference||
|SHALL|patient + date|reference + date|date modifiers ‘ge',‘le','gt','lt' |
{:.grid}

##### 10. Goal
{:.no_toc}

Supported Profiles:  [US Core Goal Profile]({{site.data.structuredefinitions.us-core-goal.path}})

Search Criteria:

1. A server **SHALL** be capable of returning all of a patient's goals using:

  `GET [base]/Goal?patient=[id]`

1. A server **SHALL** be capable of returning all of all of a patient's goals over a specified time period using:

  `GET [base]/Goal?patient=[id]&date=[date]{&date=[date]}`

Search Parameters:

|Conformance|Parameter|Type|Modifiers|
|---|---|---|---|
|SHALL|patient|reference||
|SHALL|patient + date|reference + date|date modifiers ‘ge',‘le','gt','lt' |
{:.grid}

##### 11. Immunization
{:.no_toc}

Supported Profiles:  [US Core Immunization Profile]({{site.data.structuredefinitions.us-core-immunization.path}})

Search Criteria:

1. A server **SHALL** be capable of returning all immunizations for a patient using:

  `Get [base]/Immunization?patient=[id]`

Search Parameters:

|Conformance|Parameter|Type|
|---|---|---|
|SHALL|patient|reference|
{:.grid}

##### 12. Location
{:.no_toc}

Supported Profiles:  [US Core Location Profile]({{site.data.structuredefinitions.us-core-location.path}})

Search Criteria:

1. A server **SHALL** be capable of returning a location by name using:

  `Get [base]/Location?name=[string]`

1. A server **SHALL** be capable of returning a location by address using:

  `GET [base]/Location?address=[string]`

Search Parameters:

|Conformance|Parameter|Type|
|---|---|---|
|SHALL|name|string|
|SHALL|address|string|
{:.grid}

##### 13. Medication
{:.no_toc}

Supported Profiles:  [US Core Medication Profile]({{site.data.structuredefinitions.us-core-medication.path}})


The MedicationStatement and MedicationRequest resources can represent a medication, using an external reference to a Medication resource. If an external Medication Resource is used in a MedicationStatement or a MedicationRequest, then the READ and SEARCH Criteria SHALL be supported.

##### 14. MedicationStatement
{:.no_toc}

Supported Profiles:  [US Core MedicationStatement Profile]({{site.data.structuredefinitions.us-core-medicationstatement.path}})

Search Criteria:

 The MedicationStatement resources can represent a medication using either a code or refer to the Medication resource.  When referencing a Medication resource, the resource may be [contained]({{site.data.fhir.path}}/references.html#contained) or an external resource. The server application **MAY** choose any one way or more than one method, but *if* an external reference to Medication is used, the server **SHALL** support the [`_include`]({{site.data.fhir.path}}/references.html#include) parameter for searching this element. The client application must support all methods.

A server **SHALL** be capable of returning all medications for a patient using one of or both:

  `GET /MedicationStatement?patient=[id]`

  `GET /MedicationStatement?patient=[id]&_include=MedicationStatement:medication`

Search Parameters:

| Conformance | Parameter | Type |  \_include(see documentation) |
| ---|---|---|---|--- |
| **SHALL** | patient | reference | MedicationStatement:medication
{:.grid}

##### 15. MedicationRequest
{:.no_toc}

Supported Profiles:  [US Core MedicationRequest Profile]({{site.data.structuredefinitions.us-core-medicationrequest.path}})

Search Criteria:

 The MedicationRequest resources can represent a medication using either a code or refer to the Medication resource.  When referencing a Medication resource, the resource may be [contained]({{site.data.fhir.path}}/references.html#contained) or an external resource. The server application **MAY** choose any one way or more than one method, but *if* an external reference to Medication is used, the server **SHALL** support the [`_include`]({{site.data.fhir.path}}/references.html#include) parameter for searching this element. The client application must support all methods.

A server **SHALL** be capable of returning all medications for a patient using one of or both:

  `GET /MedicationRequest?patient=[id]`

  `GET /MedicationRequest?patient=[id]&_include=MedicationRequest:medication`

Search Parameters:

| Conformance | Parameter | Type |  \_include(see documentation) |
| ---|---|---|---|--- |
| **SHALL** | patient | reference | MedicationRequest:medication
{:.grid}

##### 16. Observation
{:.no_toc}

Supported Profiles:
1. [US Core Result Observation Profile]({{site.data.structuredefinitions.us-core-observationresults.path}})

  Search Criteria:

  - A server **SHALL** be capable of  returning all of a patient's laboratory results queried by category using:

    `GET [base]/Observation?patient=[id]&category=laboratory`

  - A server **SHALL** be capable of  returning all of a patient's laboratory results queried by category code and date range using:

    `GET [base]/Observation?patient=[id]&category=laboratory&date=[date]{&date=[date]}`

  - A server **SHALL** be capable of  returning all of a patient's laboratory results queried by category and code using:

    `GET [base]/Observation?patient=[id]&category=laboratory&code=[LOINC]`

  - A server **SHOULD** be capable of returning all of a patient's laboratory results queried by category and one or more codes and date range using:

    `GET [base]/Observation?patient=[id]&category=laboratory&code=[LOINC1{,LOINC2,LOINC3,...}]&date=[date]{&date=[date]}`

1. [Vital Signs Profile]({{site.data.fhir.path}}/vitalsigns.html)

  Search Criteria

  - A server **SHALL** be capable of  returning all of a patient's vital signs that it supports using:

      `GET [base]/Observation?patient=[id]&category=vital-signs`

  - A server **SHALL** be capable of  returning all of a patient's vital signs queried by date range using:

    `GET [base]/Observation?patient=[id]&category=vital-signs&date=[date]{&date=[date]}`

  - A server **SHALL** be capable of  returning any of a patient's vital signs queried by one or more of the codes listed below using:

    `GET [base]/Observation?patient=[id]&code[vital sign LOINC{,LOINC2,LOINC3,…}]`

  - A server **SHOULD** be capable of returning any of a patient's vital signs queried by one or more of the codes listed below and date range using:

      `GET [base]/Observation?patient=[id]&code=[LOINC{,LOINC2…}]vital-signs&date=[date]{&date=[date]}`

1. [US Core Smoking Status Observation Profile]({{site.data.structuredefinitions.us-core-smokingstatus.path}})

  Search Criteria:

  - A server **SHALL** be capable of  returning a patient's smoking status using:

    `GET [base]/Observation?patient=[id]&code=72166-2`

Search Parameters:

|Conformance|Parameter|Type|Modifiers|
|---|---|---|---|
|SHALL|patient + category|reference + token||
|SHALL|patient + category + code|reference + token||
|SHALL|patient + category + date|reference + token + date|date modifiers ‘ge',‘le','gt','lt' |
|SHOULD|patient + category + code + date|reference + token + date|date modifiers ‘ge',‘le','gt','lt' |
{:.grid}

##### 17. Organization
{:.no_toc}

Supported Profiles:  [US Core Organization Profile]({{site.data.structuredefinitions.us-core-organization.path}})

Search Criteria:

1. A server **SHALL** be capable of  returning an organization by identifier using:

  `GET [base]/Organization?identifier=[system]|[code]'

1. A server **SHALL** be capable of  returning an organization by name using:

  `GET [base]/Organization?name=[string]`

1. A server **SHALL** be capable of  returning an organization by address using:

  `GET [base]/Organization?address=[string]`

Search Parameters:

|Conformance|Parameter|Type|
|---|---|---|
|SHALL|identifier|token|
|SHALL|name|string|
|SHALL|address|string|
{:.grid}

##### 18. Practitioner
{:.no_toc}

Supported Profiles:  [US Core Practitioner Profile]({{site.data.structuredefinitions.us-core-practitioner.path}})

Search Criteria:

1. A server **SHALL** be capable of  returning a practitioner by identifier using:

  `GET [base]/Practitioner?identifier=[system]|[code]`

1. A server **SHALL** be capable of  returning a practitioner by name using:

  `GET [base]/Practitioner?family=[string]&given=[string]`

Search Parameters:

|Conformance|Parameter|Type|
|---|---|---|
|SHALL|identifier|token|
|SHALL|name|string|
{:.grid}

##### 19. PractitionerRole
{:.no_toc}

Supported Profiles:  [US Core PractitionerRole Profile]({{site.data.structuredefinitions.us-core-practitionerrole.path}})

Search Criteria:

1. A server **SHALL** be capable of  returning PractitionerRoles by Practitioner.identifier using:

  `GET [base]/PractitionerRole?practitioner.identifier=[system]|[code]`

1. A server **SHALL** be capable of returning PractitionerRoles by Practitioner.family and Practitioner.given using:

  `GET [base]/PractitionerRole?practitioner.family=[string]&given=[string]`

 1. A server **SHALL** be capable of returning PractitionerRoles by specialty using:

  `GET [base]/PractitionerRole?specialty=[system]|[code]]`

Search Parameters:

|Conformance|Parameter|Type|
|---|---|---|
|SHALL|practitioner.identifier|reference + token|
|SHALL|practitioner.family + practitioner.given|reference + string + string|
|SHALL|specialty|token|
{:.grid}


##### 20. Procedure
{:.no_toc}

Supported Profiles:  [US Core Procedure Profile]({{site.data.structuredefinitions.us-core-procedure.path}})

Search Criteria:

1. A server **SHALL** be capable of  returning a patient's procedures using:
  `GET/Procedure?patient=[id]`

1. A server **SHALL** be capable of  returning all of a patient's procedures over a specified time period using:

  `GET /Procedure?patient=[id]&date=[date]{&date=[date]}`

Search Parameters:

|Conformance|Parameter|Type|Modifiers|
|---|---|---|---|
|SHALL|patient|reference||
|SHALL|patient + date|reference + date|date modifiers ‘ge',‘le','gt','lt' |
{:.grid}

<p></p>

### Conformance requirements for the US Core Client

Source Resource: [XML](CapabilityStatement-client.xml.html)/[JSON](CapabilityStatement-client.json.html)

1. FHIR Version: 3.0.1
1. Supported formats: xml, json
1. Published: 2017-03-08
1. Published by: Health Level Seven International US Realm Steering Committee

The Section describes the expected capabilities of the  US Core Client which is responsible for creating and initiating the queries for information about an individual patient. The complete list of FHIR profiles, RESTful operations, and search parameters supported by US Core Servers are defined in the [Conformance requirements for the US Core Server section](#conformance-requirements-for-the-us-core-server). US Core Clients have the option of choosing from this list to access necessary data based on their local use cases and other contextual requirements.

#### Behavior

Description:

The US Core Client **SHOULD**:

- Support fetching and querying of one or more US Core profile(s), using the supported RESTful interactions and search parameters declared in the US Core Server CapabilityStatement.

security:

The US Core Client **SHALL**:

- implement the [security requirements](security.html) documented in the US Core IG.

#### Resource  Details:

**Contents:**

1. [Patient](#1-patient-1)
1. [AllergyIntolerance](#2-allergyintolerance-1)
1. [CarePlan](#3-careplan-1)
1. [CareTeam](#4-careteam-1)
1. [Condition](#5-condition-1)
1. [Device](#6-device-1)
1. [DiagnosticReport](#7-diagnosticreport-1)
1. [DocumentReference](#8-documentreference-1)
1. [Encounter](#9-encounter-1)
1. [Goal](#10-goal-1)
1. [Immunization](#11-immunization-1)
1. [Location](#12-location-1)
1. [Medication](#13-medication-1)
1. [MedicationStatement](#14-medicationstatement-1)
1. [MedicationRequest](#15-medicationrequest-1)
1. [Observation](#16-observation-1)
1. [Organization](#17-organization-1)
1. [Practitioner](#18-practitioner-1)
1. [PractitionerRole](#19-practitionerrole-1)
1. [Procedure](#20-procedure-1)



##### 1. Patient
{:.no_toc}

Supported Profiles:  [US Core Patient Profile]({{site.data.structuredefinitions.us-core-patient.path}})

Search Criteria:

- A client **SHOULD** be capable of connecting to a server and fetching a patient using:

  `GET [base]/Patient/[id]`.

- A client **SHOULD** be capable of connecting to a server and fetching a patient by identifier using

  `GET [base]/Patient?identifier=[system]|[code]`

1. A client **SHOULD** be capable of connecting to a server and fetching a patient by supporting at a minimum the following search parameters when at least 2 are present. To limit overly broad search results, a client search with gender should include family and given name search parameters.:
   - name
   - gender
   - birthdate

      - for example:

       `GET [base]/Patient?family=[name]&?given=[name]&gender=[gender]`

##### 2. AllergyIntolerance
{:.no_toc}

Supported Profiles:  [US Core AllergyIntolerance Profile]({{site.data.structuredefinitions.us-core-allergyintolerance.path}})

Search Criteria:

1. A client **SHOULD** be capable of connecting to a server and fetching all patient's allergies using:

  `Get [base]/AllergyIntolerance?patient=[id]`

##### 3. CarePlan
{:.no_toc}

Supported Profiles:  [US Core CarePlan Profile]({{site.data.structuredefinitions.us-core-careplan.path}})

Search Criteria:

1. A client **SHOULD** be capable of connecting to a server and fetching all of a patient's Assessment and Plan of Treatment information using:

  `Get [base]/CarePlan?patient=[id]&category=assess-plan`

1. A client **SHOULD** be capable of connecting to a server and fetching a patient's Assessment and Plan of Treatment information over a specified time period using:

  `Get [base]/CarePlan?patient=[id]&category=assess-plan&date=[date]`

1. A client **SHOULD** be capable of connecting to a server and fetching all of a patient's active Assessment and Plan of Treatment information using

  `Get [base]/CarePlan?patient=[id]&category=assess-plan&status=active`

1. A client **SHOULD** be capable of connecting to a server and fetching a patient's active Assessment and Plan of Treatment information over a specified time period using

  `Get [base]/CarePlan?patient=[id]&category=assess-plan&status=active&date=[date]`




##### 4. CareTeam
{:.no_toc}

Supported Profiles:  [US Core CareTeam Profile]({{site.data.structuredefinitions.us-core-careteam.path}})

Search Criteria:

1. A client **SHOULD** be capable of connecting to a server and fetching  a patient's current care team members using:

  `Get [base]/CareTeam?patient=[id]&status=active`



##### 5. Condition
{:.no_toc}

Supported Profiles:  [US Core Condition Profile]({{site.data.structuredefinitions.us-core-condition.path}})

Search Criteria:

1. A client **SHOULD** be capable of fetching all problems and health concerns for a patient, including current as well as historical problems and health concerns using:

  `Get [base]/Condition?patient=[id]`

1. A client **SHOULD** be capable of connecting to a server and fetching all of a patient's *active* problems and health concerns using:

  `Get [base]/Condition?patient=[id]&clinicalstatus=active,recurrance,remission`

1. A client **SHOULD** be capable of connecting to a server and fetching all of a patient's problems *or* all of patient's health concerns using:

  `Get [base]/Condition?patient=[id]&category=[problem|health-concern]`



##### 6. Device
{:.no_toc}

Supported Profiles:  [US Core Device Profile]({{site.data.structuredefinitions.us-core-device.path}})

Search Criteria:

1. A client **SHOULD** be capable of connecting to a server and fetching all Unique device identifier(s)(UDI) for a patient's implanted device(s):

  `Get [base]/Device?patient=[id]`



##### 7. DiagnosticReport
{:.no_toc}

Supported Profiles:  [US Core DiagnosticReport Profile]({{site.data.structuredefinitions.us-core-diagnosticreport.path}})

Search Criteria:

1. A client **SHOULD** be capable of connecting to a server and fetching all of a patient's laboratory diagnostic reports queried by category using:

  `Get [base]/DiagnosticReport?patient=[id]&category=LAB`

1. A client **SHOULD** be capable of connecting to a server and fetching all of a patient's laboratory diagnostic reports queried by category code and date range using:

  `GET [base]/DiagnosticReport?patient=[id]&category=LAB&date=[date]{&date=[date]}`

1. A client **SHOULD** be capable of connecting to a server and fetching all of a patient's laboratory diagnostic reports queried by category and code using:

  `GET [base]/DiagnosticReport?patient=[id]&category=LAB&code=[LOINC]`

1. A client **SHOULD** be capable of connecting to a server and fetching all of a patient's laboratory diagnostic reports queried by category and one or more codes and date range using:

  `GET [base]/DiagnosticReport?patient=[id]&category=LAB&code=[LOINC1{,LOINC2,LOINC3,…}]&date=[date]{&date=[date]}`


##### 8. DocumentReference
{:.no_toc}

Supported Profiles:  [US Core DocumentReference Profile]({{site.data.structuredefinitions.us-core-documentreference.path}})

Search Criteria:

  1. A client **SHOULD** be capable of connecting to a server and fetching all of a patient's DocumentReferences using:

  `GET [base]/DocumentReference?patient=[id]`

  1. A client **SHOULD** be capable of connecting to a server to execute the [$docref](OperationDefinition-docref.html) operation:

  `GET [base]/DocumentReference/$docref?patient=[id]`

  1. A client **SHOULD** be capable of connecting to a server and fetching all of a patient's DocumentReferences for a given time period and document type:

  `GET [base]/DocumentReference?patient=[id]&type=[type]&period=[date]{&date=[date]}`

##### 9. Encounter
{:.no_toc}

Supported Profiles:  [US Core Encounter Profile]({{site.data.structuredefinitions.us-core-Encounter.path}})

Search Criteria:

1. A client **SHOULD** be capable of connecting to a server and fetching all of a patient's encounters using:

  `GET [base]/Encounter?patient=[id]`

1. A client **SHOULD** be capable of connecting to a server and fetching all of all of a patient's encounters over a specified time period using:

  `GET [base]/Encounter?patient=[id]&date=[date]{&date=[date]}`

##### 10. Goal
{:.no_toc}

Supported Profiles:  [US Core Goal Profile]({{site.data.structuredefinitions.us-core-goal.path}})

Search Criteria:

1. A client **SHOULD** be capable of connecting to a server and fetching all of a patient's goals using:

  `Get [base]/Goal?patient=[id]`

1. A client **SHOULD** be capable of connecting to a server and fetching all of all of a patient's goals over a specified time period using:

  `GET [base]/Goal?patient=[id]&date=[date]{&date=[date]}`


##### 11. Immunization
{:.no_toc}

Supported Profiles:  [US Core Immunization Profile]({{site.data.structuredefinitions.us-core-immunization.path}})

Search Criteria:

1. A client **SHOULD** be capable of connecting to a server and fetching all immunizations for a patient using:

  `Get [base]/Immunization?patient=[id]`



##### 12. Location
{:.no_toc}

Supported Profiles:  [US Core Location Profile]({{site.data.structuredefinitions.us-core-location.path}})

Search Criteria:

1. A client **SHOULD** be capable of connecting to a server and fetching a location by name using:

  `Get [base]/Location?name=[string]`

1. A client **SHOULD** be capable of connecting to a server and fetching a location by address using:

  `GET [base]/Location?address=[string]`


##### 13. Medication
{:.no_toc}

Supported Profiles:  [US Core Medication Profile]({{site.data.structuredefinitions.us-core-medication.path}})

The MedicationStatement and MedicationRequest resources can represent a medication, using an external reference to a Medication resource. If an external Medication Resource is used in a MedicationStatement or a MedicationRequest, then the READ and SEARCH Criteria SHOULD be supported.

##### 14. MedicationStatement
{:.no_toc}

Supported Profiles:  [US Core MedicationStatement Profile]({{site.data.structuredefinitions.us-core-medicationstatement.path}})

Search Criteria:

The MedicationStatement resources can represent a medication using either a code or refer to the Medication resource.  When referencing a Medication resource, the resource may be [contained]({{site.data.fhir.path}}/references.html#contained) or an external resource. IF, an external reference to Medication is used, the server **SHALL** support the [`_include`]({{site.data.fhir.path}}/references.html#include) parameter for searching this element. The client application **SHALL** support all methods.

A client **SHOULD** be capable of connecting to a server and fetching all medications for a patient using both:

  `GET /MedicationStatement?patient=[id]`

  and

  `GET /MedicationStatement?patient=[id]&_include=MedicationStatement:medication`



##### 15. MedicationRequest
{:.no_toc}

Supported Profiles:  [US Core MedicationRequest Profile]({{site.data.structuredefinitions.us-core-medicationrequest.path}})

Search Criteria:

 The MedicationRequest resources can represent a medication using either a code or refer to the Medication resource.  When referencing a Medication resource, the resource may be [contained]({{site.data.fhir.path}}/references.html#contained) or an external resource. If, an external reference to Medication is used, the server **SHALL** support the [`_include`]({{site.data.fhir.path}}/references.html#include) parameter for searching this element. The client application **SHALL** support all methods.

A client **SHOULD** be capable of connecting to a server and fetching all medications for a patient using both:

  `GET /MedicationRequest?patient=[id]`

  and

  `GET /MedicationRequest?patient=[id]&_include=MedicationRequest:medication`

##### 16. Observation
{:.no_toc}

Supported Profiles:
1. [US Core Result Observation Profile]({{site.data.structuredefinitions.us-core-observationresults.path}})

  Search Criteria:

  - A client **SHOULD** be capable of connecting to a server and fetching all of a patient's laboratory results queried by category using:

    `GET [base]/Observation?patient=[id]&category=laboratory`

  - A client **SHOULD** be capable of connecting to a server and fetching all of a patient's laboratory results queried by category code and date range using:

    `GET [base]/Observation?patient=[id]&category=laboratory&date=[date]{&date=[date]}`

  - A client **SHOULD** be capable of connecting to a server and fetching all of a patient's laboratory results queried by category and code using:

    `GET [base]/Observation?patient=[id]&category=laboratory&code=[LOINC]`

  - A client **SHOULD** be capable of connecting to a server and fetching all of a patient's laboratory results queried by category and one or more codes and date range using:

    `GET [base]/Observation?patient=[id]&category=laboratory&code=[LOINC1{,LOINC2,LOINC3,...}]&date=[date]{&date=[date]}`

1. [Vital Signs Profile]({{site.data.fhir.path}}/vitalsigns.html)

  Search Criteria

  - A client **SHOULD** be capable of connecting to a server and fetching all of a patient's vital signs that it supports using:

      `GET [base]/Observation?patient=[id]&category=vital-signs`

  - A client **SHOULD** be capable of connecting to a server and fetching all of a patient's vital signs queried by date range using:

    `GET [base]/Observation?patient=[id]&category=vital-signs&date=[date]{&date=[date]}`

  - A client **SHOULD** be capable of connecting to a server and fetching any of a patient's vital signs queried by one or more of the codes listed below using:

    `GET [base]/Observation?patient=[id]&code[vital sign LOINC{,LOINC2,LOINC3,…}]`

  - A client **SHOULD** be capable of connecting to a server and fetching any of a patient's vital signs queried by one or more of the codes listed below and date range using:

      `GET [base]/Observation?patient=[id]&code=[LOINC{,LOINC2…}]vital-signs&date=[date]{&date=[date]}`

1. [US Core Smoking Status Observation Profile]({{site.data.structuredefinitions.us-core-smokingstatus.path}})

  Search Criteria:

  - A client **SHOULD** be capable of connecting to a server and fetching a patient's smoking status using:

    `GET [base]/Observation?patient=[id]&code=72166-2`




##### 17. Organization
{:.no_toc}

Supported Profiles:  [US Core Organization Profile]({{site.data.structuredefinitions.us-core-organization.path}})

Search Criteria:

1. A client **SHOULD** be capable of connecting to a server and fetching an organization by identifier using:

  `GET [base]/Organization?identifier=[system]|[code]'

1. A client **SHOULD** be capable of connecting to a server and fetching an organization by name using:

  `GET [base]/Organization?name=[string]`

1. A client **SHOULD** be capable of connecting to a server and fetching an organization by address using:

  `GET [base]/Organization?address=[string]`


##### 18. Practitioner
{:.no_toc}

Supported Profiles:  [US Core Practitioner Profile]({{site.data.structuredefinitions.us-core-practitioner.path}})

Search Criteria:

1. A client **SHOULD** be capable of connecting to a server and fetching a practitioner by identifier using:

  `GET [base]/Practitioner?identifier=[system]|[code]`

1. A client **SHOULD** be capable of connecting to a server and fetching a practitioner by name using:

  `GET [base]/Practitioner?family=[string]&given=[string]`


##### 19. PractitionerRole
{:.no_toc}

Supported Profiles:  [US Core PractitionerRole Profile]({{site.data.structuredefinitions.us-core-practitionerrole.path}})

Search Criteria:

1. A client **SHOULD** be capable of connecting to a server and fetching PractitionerRoles by identifier using:

  `GET [base]/PractitionerRole?practitioner.identifier=[system]|[code]`

1. A client **SHOULD** be capable of connecting to a server and fetching a PractitionerRoles by name using:

  `GET [base]/PractitionerRole?practitioner.family=[string]&given=[string]`

1. A client **SHOULD** be capable of connecting to a server and fetching a PractitionerRoles by specialty using:

  `GET [base]/PractitionerRole?specialty=[system]|[code]]`


##### 20. Procedure
{:.no_toc}

Supported Profiles:  [US Core Procedure Profile]({{site.data.structuredefinitions.us-core-procedure.path}})

Search Criteria:

1. A client **SHOULD** be capable of connecting to a server and fetching a patient's procedures using:

  `GET/Procedure?patient=[id]`

1. A client **SHOULD** be capable of connecting to a server and fetching all of a patient's procedures over a specified time period using:

  `GET /Procedure?patient=[id]&date=[date]{&date=[date]}`

<p></p>
