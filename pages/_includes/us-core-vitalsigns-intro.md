This Implementation Guide uses the [Vital Signs Profile] formal definitions from the FHIR [Observation] resource. However, this Implementation Guide provides the following additional guidance which sets the minimum expectations for recording, searching and fetching vital signs associated with a patient. Together they identify which elements, extensions, vocabularies and value sets **SHALL** be present in the resource when using this profile.

**Example Usage Scenarios:**

The following are example usage scenarios for the Vital Signs
Profile:

-   Query for vital signs of a particular patient
-   Record vital signs of a particular patient

##### Mandatory Data Elements and Terminology


The following data-elements are mandatory (i.e data MUST be present). These are presented below in a simple human-readable explanation.  Profile specific guidance and examples are provided as well.  The [**Formal Profile Definition**](#profile) are provided as links in the table below to view the formal summary, definitions, and  terminology requirements.  

**Each Observation must have:**

1.  a status
1.  a category code of 'vital-signs'
1.  a LOINC code which tells you what is being measured and is taken from the “LOINC Code” column in the table below.
    -   note: If a more specific code is recorded, the generic code and the translated coded must be sent - e.g. method specific LOINC Codes, SNOMED CT concepts, system specific codes
1.  a patient
1.  a time indicating when the measurement was taken
1.  a numeric result value and standard UCUM unit which is taken from the “UCUM Unit Code” column in the table below.
    -   note: if there is no numeric result then you have to supply a reason

**Profile specific implementation guidance:**

* This table represents a minimum set of vital sign concepts, the required LOINC codes, and UCUM units of measure codes used for representing vitals signs observations (See the [General Guidance Section] for further guidance on using UCUM). These are [extensible] bindings and require that when a system support of any of these vital signs concepts, they must represent them using these codes. In addition, if you have a blood pressure observation, you must have both a systolic and a diastolic component, though one or both may have dataAbsentReason instead of a value.

* This profile may be referenced by different capability statements, such as the [Conformance requirements for the US-Core Server].

* Alternate codes may be provided in addition to the standard LOINC and UCUM codes defined here.The examples illustrate using other codes as translations.

* Other profiles may make rules about which vital sign must be present or must be present as part of a panel.


#### Examples

 - [observation-vitals-panel](Observation-vitals-panel.html)
 - [observation-weight](Observation-weight.html)
 - [observation-temperature](Observation-temperature.html)
 - [observation-heart-rate](Observation-heart-rate.html)
 - [observation-respiratory-rate](Observation-respiratory-rate.html)
 - [observation-oxygen-saturation](Observation-oxygen-saturation.html)
 - [observation-length](Observation-length.html)
 - [observation-height](Observation-height.html)
 - [observation-head-circumference](Observation-head-circumference.html)
 - [observation-bmi](Observation-bmi.html)
 - [observation-blood-pressure](Observation-blood-pressure.html)
 - [observation-bp-data-absent](Observation-bp-data-absent.html)


[Vital Signs Profile]: observation-profiles.html
[Observation]: http://build.fhir.org/observation.html
[extensible]: http://build.fhir.org/terminologies.html#extensible
[Conformance requirements for the US-Core Server]: CapabilityStatement-server.html
[General Guidance Section]: guidance.html
[Vital Signs]: http://build.fhir.org/vitalsigns.html
[Vital Signs Panel]: http://build.fhir.org/vitalspanel.html
[Respiratory Rate]: http://build.fhir.org/resprate.html
[Heart rate]: http://build.fhir.org/heartrate.html
[Oxygen saturation]: http://build.fhir.org/oxygensat.html
[Body temperature]: http://build.fhir.org/bodytemp.html
[Body height]: http://build.fhir.org/bodyheight.html
[Body length]: http://build.fhir.org/bodylength.html
[Head circumference]: http://build.fhir.org/headcircum.html
[Body weight]: http://build.fhir.org/bodyweight.html
[Body mass index]: http://build.fhir.org/bmi.html
[Blood pressure systolic and diastolic]: http://build.fhir.org/bp.html
[Systolic blood pressure]: http://build.fhir.org/bp.html
[Diastolic blood pressure]: http://build.fhir.org/bp.html
