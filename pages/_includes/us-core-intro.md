

## Introduction

The data elements, extension, and terminology used in the *US Core Implemenation Guide* Version 1.0.0 are based upon FHIR STU3 API. These requirements were Originally developed, balloted, and published in FHIR DSTU2 as part of the [ONC] sponsored [Data Access Framework (DAF)] project. THey were subsequently updated to define the minimum mandatory conformance requirements needed for accessing patient data as defined by the [Argonaut] pilot implementations and to meet the [ONC 2015 Edition Common Clinical Data Set (CCDS)] as well as essential administrative and conformance requirements.  In addition to Argonaut, these profiles are used by the [DAF-Research], [QI-Core], and [CIMI] and are intended to be a common core for other US Realm guides.

## US Core Actors

The following actors are part of the US Core IG.

* US Core Requestor: An application that initiates a data access request to retrieve patient data. This can be thought of as the client in a client-server interaction.
* US Core Responder: A product that responds to the data access request providing patient data. This can be thought of as the server in a client-server interaction.


## US Core Profiles

The list of US Core Profiles is shown below.  Each profile defines the minimum mandatory elements, extensions and terminology requirements that **MUST** be present. For each profile requirements and guidance are given in a simple narrative summary. A formal hierarchical table that presents a [logical view] of the content in both a differential and snapshot view is also provided along with references to appropriate terminologies and examples.  In addition each profile has a "Quick Start" section which is intended as an implementer friendly overview of the required search and read operations.

{% include list-simple-profiles.xhtml %}
- [Vitals Signs Profile](us-core-vitalsigns.html) (From FHIR Core Profiles for Observation)

*Note on Searches based on a date or date range:*

- Allergies, Immunizations, Medications, Problems and Health Concerns, UDI, Smoking Status do not require a date range search since a system should return all relevant resources.
- Date range search requirements are included in the Quick Start section for the following resources - Vital Signs, Laboratory Results, Goals, Procedures, and Assessment and Plan of Treatment.

### 2015 Edition Common Clinical Data Set

The US Core Profiles are intended to meet the 2015 Edition certification criterion for Patient Selection 170.315(g)(7) and Application Access – Data Category Request 170.315(g)(8). They were created for each of the 2015 Edition Common Clinical Data Set.  The Location, Organization and Practitioner Profiles are not called out specifically in the certification criteria but are included because they are directly referenced by other profiles.  Where applicable the US Core Profiles are based on the HL7 U.S. Data Access Framework ([DAF]) FHIR DSTU2 Implementation Guide. However, the requirements per resource are a subset of those of the DAF implementation guide.


The table below lists the US Core Profile and FHIR Resources used for the corresponding 2015 Edition Common Clinical Data Set (CCDS) Data elements:

No| CCDS Data Element | US Core Profile | FHIR Resource
---|---|---|
(1) |  Patient Name | US Core Patient Profile| Patient
(2) |  Sex | US Core Patient Profile | Patient
(3) |  Date of birth | US Core Patient Profile | Patient
(4) |  Race | US Core Patient Profile | Patient
(5) |  Ethnicity | US Core Patient Profile | Patient
(6) |  Preferred language | US Core Patient Profile | Patient
(7) |  Smoking status | US Core Smoking Status Observation Profile | Observation
(8) |  Problems | US Core Condition Profile | Condition
(9) |  Medications | US Core Medication Profile, US Core Medication Statement Profile, US Core Medication Request Profile | Medication, MedicationStatement, MedicationRequest
(10) |  Medication allergies | US Core Allergies Profile | AllergyIntolerance
(11) |  Laboratory test(s) | US Core Result Observation Profile, US Core Diagnostic Report Profile| Observation, DiagnosticReport
(12) |  Laboratory value(s)/result(s) |  US Core Result Observation Profile, US Core Diagnostic Report Profile | Observation, DiagnosticReport
(13) |  Vital signs | Vital Signs Profile(From FHIR Core Profiles for Observation) | Observation
(14) |  (no longer required) | -
(15) |  Procedures | US Core Procedure Profile | Procedure
(16) |  Care team member(s) | US Core CareTeam Profile | CareTeam
(17) |  Immunizations | US Core Immunization Profile | Immunization
(18) |  Unique device identifier(s) for a patient’s implantable device(s) | US Core Implanted Device Profile | Device
(19) |  Assessment and plan of treatment | US Core CarePlan Profile | CarePlan
(20) |  Goals | US Core Goal Profile | Goal
(21) |  Health concerns | US Core Condition Profile  | Condition



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
[profiles]: http://build.fhir.orgprofiling.html
[logical view]: http://build.fhir.orgformats.html#table
[StructureDefinitions]: http://build.fhir.orgstructuredefinition.html
[Value sets]: http://build.fhir.org/valueset.html
[CodeSystem]: http://build.fhir.orgcodesystem.html
[ConceptMap]: http://build.fhir.orgconceptmap.html
[NamingSystem]: http://build.fhir.orgnamingsystem.html
[FHIR Conformance Rules]: http://build.fhir.orgCapabilityStatement-rules.html
[dataAbsentReason]: http://build.fhir.orgextension-data-absent-reason.html
[FHIR Terminology]: http://build.fhir.orgterminologies.html
[FHIR RESTful API]: http://build.fhir.orghttp.html
[HTTP]: http://build.fhir.orghttp.html
[FHIR Data Types]: http://build.fhir.orgdatatypes.html
[FHIR Search]: http://build.fhir.orgsearch.html
[FHIR Resource]: http://build.fhir.orgformats.html
