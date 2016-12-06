This profile sets minimum expectations for the [Observation] resource to record, search and fetch vital signs associated with a patient. It identifies which core elements, extensions, vocabularies and value sets **SHALL** be present in the resource when using this profile.

**Example Usage Scenarios:**

The following are example usage scenarios for the US Core-VitalSigns
profile:

-   Query for vital signs of a particular patient
-   Record vital signs of a particular patient

##### Mandatory Data Elements and Terminology


The following data-elements are mandatory (i.e data MUST be present). These are presented below in a simple human-readable explanation.  Profile specific guidance and examples are provided as well.  The [**Formal Profile Definition**](#profile) below provides the  formal summary, definitions, and  terminology requirements.  

**Each Observation must have:**

1.  a status
1.  a category code of 'vital-signs'
1.  a LOINC code which tells you what is being measured and is taken from the “LOINC Code” column in the table below.
    -   note: If a more specific code is recorded, the generic code and the translated coded must be sent - e.g. method specific LOINC Codes, SNOMED CT concepts, system specific codes
1.  a patient
1.  a time indicating when the measurement was taken
1.  a numeric result value and standard UCUM unit which is taken from the “LOINC Code” column in the table below.
    -   note: if there is no numeric result then you have to supply a reason

**Profile specific implementation guidance:**

* This table represents a minimum set of vital sign concepts, the required LOINC codes, and UCUM units of measure codes used for representing vitals signs observations (See the [General Guidance Section] for further guidance on using UCUM). These are [extensible] bindings and require that when a system support of any of these vital signs concepts, they must represent them using these codes. In addition, if you have a blood pressure observation, you must have both a systolic and a diastolic component, though one or both may have dataAbsentReason instead of a value.

* This profile may be referenced by different capability statements, such as the [Conformance requirements for the US-Core Server].

* Alternate codes may be provided in addition to the standard LOINC and UCUM codes defined here.The examples illustrate using other codes as translations.

* Other profiles may make rules about which vital sign must be present or must be present as part of a panel.

---

<table class="grid">
<thead>
<tr>
<th style="text-align:left">Vital Sign Name</th>
<th style="text-align:center">LOINC Code</th>
<th style="text-align:center">UCUM Unit Code</th>
<th style="text-align:left">Notes</th>
</tr>
</thead>
<tbody>
<tr>
<td style="text-align:left">Vital Signs Panel</td>
<td style="text-align:center">8716-3</td>
<td style="text-align:center">-</td>
<td style="text-align:left">This is the top-level grouping structure for a set of vital signs.  It has no value in Observation.valueQuantity ; instead, it just includes related links (with type=has-member) to the Observations in this set (e.g. respiratory rate, heart rate, BP).  Note that querying for the panel may miss individual results that are not part of an actual panel.</td>
</tr>
<tr>
<td style="text-align:left">Respiratory Rate</td>
<td style="text-align:center">9279-1</td>
<td style="text-align:center">/min</td>
<td style="text-align:left"></td>
</tr>
<tr>
<td style="text-align:left">Heart rate</td>
<td style="text-align:center">8867-4</td>
<td style="text-align:center">/min</td>
<td style="text-align:left"></td>
</tr>
<tr>
<td style="text-align:left">Oxygen saturation</td>
<td style="text-align:center">59408-5</td>
<td style="text-align:center">%</td>
<td style="text-align:left">59408-5 (Oxygen saturation in Arterial blood by Pulse oximetry) replaces the deprecated code 2710-2 which had been listed in C-CDA.</td>
</tr>
<tr>
<td style="text-align:left">Body temperature</td>
<td style="text-align:center">8310-5</td>
<td style="text-align:center">Cel, [degF]</td>
<td style="text-align:left"></td>
</tr>
<tr>
<td style="text-align:left">Body height</td>
<td style="text-align:center">8302-2</td>
<td style="text-align:center">cm, [in_i]</td>
<td style="text-align:left"></td>
</tr>
<tr>
<td style="text-align:left">Body length</td>
<td style="text-align:center">8306-3</td>
<td style="text-align:center">cm, [in_i]</td>
<td style="text-align:left">Like height, but lying down, typically this is used for infants</td>
</tr>
<tr>
<td style="text-align:left">Head circumference</td>
<td style="text-align:center">8287-5</td>
<td style="text-align:center">cm, [in_i]</td>
<td style="text-align:left"></td>
</tr>
<tr>
<td style="text-align:left">Body weight</td>
<td style="text-align:center">29463-7</td>
<td style="text-align:center">g, kg,[lb_av]</td>
<td style="text-align:left"></td>
</tr>
<tr>
<td style="text-align:left">Body mass index</td>
<td style="text-align:center">39156-5</td>
<td style="text-align:center">kg/m2</td>
<td style="text-align:left"></td>
</tr>
<tr>
<td style="text-align:left">Blood pressure systolic and diastolic</td>
<td style="text-align:center">55284-4</td>
<td style="text-align:center">-</td>
<td style="text-align:left">This is a grouping structure. It has no value in Observation.valueQuantity but contains at least one component (systolic and/or diastolic).</td>
</tr>
<tr>
<td style="text-align:left">Systolic blood pressure</td>
<td style="text-align:center">8480-6</td>
<td style="text-align:center">mm[Hg]</td>
<td style="text-align:left">Observation.component code for a blood pressure Observation</td>
</tr>
<tr>
<td style="text-align:left">Diastolic blood pressure</td>
<td style="text-align:center">8462-4</td>
<td style="text-align:center">mm[Hg]</td>
<td style="text-align:left">Observation.component code for a blood pressure Observation</td>
</tr>
</tbody>
</table>

---

#### Examples

 - [observation-vitals-panel]Observation-vitals-panel.html)
 - [observation-weight]Observation-weight.html)
 - [observation-temperature]Observation-temperature.html)
 - [observation-heart-rate]Observation-heart-rate.html)
 - [observation-respiratory-rate]Observation-respiratory-rate.html)
 - [observation-oxygen-saturation]Observation-oxygen-saturation.html)
 - [observation-length]Observation-length.html)
 - [observation-height]Observation-height.html)
 - [observation-head-circumference]Observation-head-circumference.html)
 - [observation-bmi]Observation-bmi.html)
 - [observation-blood-pressure]Observation-blood-pressure.html)
 - [observation-bp-data-absent]Observation-bp-data-absent.html)


[Observation]: http://hl7.org/fhir/2017Jan/observation.html
[extensible]: http://hl7.org/fhir/2017Jan/terminologies.html#extensible
[Conformance requirements for the US-Core Server]: CapabilityStatement-server.html
[General Guidance Section]: definitions.html
