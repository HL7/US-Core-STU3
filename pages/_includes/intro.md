## {{ page.title }}

## Introduction

The *US Core Implementation Guide version 1.0.0* defines the minimum conformance requirements for accessing patient data as defined by the [Argonaut] pilot implementations and the [ONC 2015 Edition Common Clinical Data Set (CCDS)]. These requirements were originally developed, balloted, and published in FHIR DSTU2 as part of the [ONC] sponsored [Data Access Framework] (DAF) project. In addition to Argonaut, these profiles are used by [DAF-Research], [QI-Core], and [CIMI], and are intended to be the foundation for future US Realm guides.

US Core version 1.0.0 is based on the FHIR STU3. HL7 will expand and publish future versions of US Core under the guidance of the HL7 US Realm Steering Committee.

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
- Vital Signs, Laboratory Results, Goals, Procedures, and Assessment and Plan of Treatment include date range search requirements in the Quick Start section on the profile page.

See [2015 Edition Common Clinical Data Set] for a mapping to the CCDS.

{% capture my-include %}{% include conformance.md %}{% endcapture %}{{ my-include | markdownify }}

----


Primary Authors: Brett Marquard, Nagesh Bashyam, Eric Haas

Secondary Authors: Grahame Grieve, Lloyd McKenzie



[QI-Core]:https://oncprojectracking.healthit.gov/wiki/display/TechLabSC/CQF+Home
[CIMI]:http://www.opencimi.org
[Argonaut]: http://argonautwiki.hl7.org/index.php?title=Main_Page
[DAF-Research]: http://hl7.org/fhir/us/daf-research/index.html
[US Core Security]: US Core-security.html
[ONC]: http://www.healthit.gov/newsroom/about-onc
[Data Access Framework]: http://wiki.siframework.org/Data+Access+Framework+Homepage
[Argonaut]: http://argonautwiki.hl7.org/index.php?title=Main_Page
[ONC 2015 Edition Common Clinical Data Set (CCDS)]: https://www.healthit.gov/sites/default/files/2015Ed_CCG_CCDS.pdf
[profiles]: http://build.fhir.orgprofiling.html
[logical view]: http://build.fhir.org/formats.html#table
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
[2015 Edition Common Clinical Data Set]: guidance.html#edition-common-clinical-data-set
