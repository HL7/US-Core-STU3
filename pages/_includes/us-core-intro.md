

## Introduction

The data elements, extension, and terminology used in the US Core Implemenation Guide are based upon [ONC 2015 Edition Common Clinical Data Set (CCDS)] as well as essential administrative and conformance requirements.   These requirements were originally developed, balloted, and published in FHIR DSTU2 as part of the [ONC] sponsored [Data Access Framework (DAF)] project and were subsequently updated to define the minimum mandatory conformance requirements needed for accessing patient data as defined by the [Argonaut] pilot implementations.  In addition to Argonaut, these profiles are used by the [DAF-Research], [QI-Core], and [CIMI] and are intended to be a common core for other US Realm guides.

## US Core Actors

The following actors are part of the US Core IG.

* US Core Requestor: An application that initiates a data access request to retrieve patient data. This can be thought of as the client in a client-server interaction.
* US Core Responder: A product that responds to the data access request providing patient data. This can be thought of as the server in a client-server interaction.


## US Core Profiles

The US Core Profiles are intended to meet the 2015 Edition certification criterion for Patient Selection 170.315(g)(7) and Application Access – Data Category Request 170.315(g)(8). They were created for each of the 2015 Edition Common Clinical Data Set.  The Location, Organization and Practitioner Profiles are not called out specifically in the certification criteria but are included because they are directly referenced by other profiles.  Where applicable the US Core Profiles are based on the HL7 U.S. Data Access Framework ([DAF]) FHIR DSTU2 Implementation Guide. However, the requirements per resource are a subset of those of the DAF implementation guide.


The table below lists the FHIR Resources used for the corresponding 2015 Edition Common Clinical Data Set (CCDS) Data elements:

No| CCDS Data Element | FHR Resource
---|---|---|
(1) |  Patient Name | Patient
(2) |  Sex | Patient
(3) |  Date of birth | Patient
(4) |  Race | Patient
(5) |  Ethnicity | Patient
(6) |  Preferred language | Patient
(7) |  Smoking status | Observation
(8) |  Problems | Condition
(9) |  Medications | Medication, MedicationStatement, MedicationRequest
(10) |  Medication allergies | AllergyIntolerance
(11) |  Laboratory test(s) | Observation, DiagnosticReport
(12) |  Laboratory value(s)/result(s) | Observation, DiagnosticReport
(13) |  Vital signs | Observation
(14) |  (no longer required) | -
(15) |  Procedures | Procedure
(16) |  Care team member(s) | CareTeam
(17) |  Immunizations | Immunization
(18) |  Unique device identifier(s) for a patient’s implantable device(s) | Device
(19) |  Assessment and plan of treatment | CarePlan
(20) |  Goals | Goal
(21) |  Health concerns | Condition

*Note on Searches based on a date or date range:*

Allergies, Immunizations, Medications, Problems and Health Concerns, UDI, Smoking Status do not require a date range search since a system should return all relevant resources.

Date range search requirements are included in the Quick Start section for the following resources - Vital Signs, Laboratory Results, Goals, Procedures, and Assessment and Plan of Treatment.


The list of US Core Profiles is shown below.  Each profile defines the minimum mandatory elements, extensions and terminology requirements that **MUST** be present. For each profile requirements and guidance are given in a simple narrative summary. A formal hierarchical table that presents a [logical view] of the content in both a differential and snapshot view is also provided along with references to appropriate terminologies and examples.


{% include list-profiles.xhtml %}


{% capture my-include %}{% include conformance.md %}{% endcapture %}{{ my-include | markdownify }}

----


Primary Authors: Brett Marquard, Nagesh Bashyam, Eric Haas

Secondary Authors: Grahame Grieve, Lloyd McKenzie



[QI-Core]:https://oncprojectracking.healthit.gov/wiki/display/TechLabSC/CQF+Home
[CIMI]:http://www.opencimi.org
[Argonaut]: http://argonautwiki.hl7.org/index.php?title=Main_Page
[US Core]: US Core.html
[US Core]: US Core.html
[US Core-Research]: US Core-research.html
[US Core Security]: US Core-security.html
[ONC]: http://www.healthit.gov/newsroom/about-onc
[Data Access Framework (DAF)]: http://wiki.siframework.org/Data+Access+Framework+Homepage
[PCORnet]: http://www.pcornet.org/
[Argonaut]: http://argonautwiki.hl7.org/index.php?title=Main_Page
[ONC 2015 Edition Common Clinical Data Set (CCDS)]: https://www.healthit.gov/sites/default/files/2015Ed_CCG_CCDS.pdf
[profiles]: http://hl7.org/fhir/profiling.html
[logical view]: http://hl7.org/fhir/formats.html#table
[StructureDefinitions]: http://hl7.org/fhir/structuredefinition.html
[Value sets]: http://build.fhir.org/valueset.html
[CodeSystem]: http://hl7.org/fhir/codesystem.html
[ConceptMap]: http://hl7.org/fhir/conceptmap.html
[NamingSystem]: http://hl7.org/fhir/namingsystem.html
[FHIR Conformance Rules]: http://hl7.org/fhir/capabilitystatement-rules.html
[dataAbsentReason]: http://hl7.org/fhir/extension-data-absent-reason.html
[FHIR Terminology]: http://hl7.org/fhir/terminologies.html
[FHIR RESTful API]: http://hl7.org/fhir/http.html
[HTTP]: http://hl7.org/fhir/http.html
[FHIR Data Types]: http://hl7.org/fhir/datatypes.html
[FHIR Search]: http://hl7.org/fhir/search.html
[FHIR Resource]: http://hl7.org/fhir/formats.html
