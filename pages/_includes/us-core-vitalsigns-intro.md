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
1.  a numeric result value and standard UCUM unit which is taken from the “UCUM Unit Code” column in the table below.
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
			<th>Vital Sign Name</th>
			<th>LOINC Code</th>
			<th>LOINC Name and Comments</th>
			<th>UCUM Unit Code</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>Vital Signs Panel</td>
			<td>85353-1</td>
			<td>
				<em>Vital signs, weight, height, head circumference, oxygen saturation and BMI panel</em> - It represent a panel of vital signs listed in this table.  All members of the panel are optional and note that querying for the panel may miss individual results that are not part of the actual panel.    When used, Observation.valueQuantity is not present ; instead, related links (with type=has-member) reference the vital signs observations  (e.g. respiratory rate, heart rate, BP, etc).   Note that querying for the panel may miss individual results that are not part of an actual panel.  This code replaces the deprecated code 8716-3  - <em>Vital signs</em>  which is used in the Argonaut Data Query Implementation Guide. </td>
			<td>-</td>
		</tr>
		<tr>
			<td>Respiratory Rate</td>
			<td>9279-1</td>
			<td>
				<em>Respiratory Rate</em>
			</td>
			<td>/min</td>
		</tr>
		<tr>
			<td>Heart rate</td>
			<td>8867-4</td>
			<td>
				<em>Heart rate</em> - To supplement this vital sign observation, 8887-2  -<em> Heart rate device type</em> MAY be used as an additional observation.</td>
			<td>/min</td>
		</tr>
		<tr>
			<td>Oxygen saturation</td>
			<td>59408-5</td>
			<td>
				<em>Oxygen saturation in Arterial blood by Pulse oximetry</em> - This code replaces the deprecated code 2710-2 -<em> Deprecated Oxygen saturation in Capillary blood by Oximetry</em> which had been listed in C-CDA.</td>
			<td>%</td>
		</tr>
		<tr>
			<td>Body temperature</td>
			<td>8310-5</td>
			<td>
				<em>Body temperature</em> - o supplement this vital sign observation, 8327-9 - <em>Body temperature measurement site</em> (oral, forehead, rectal, etc.)  and 8326-1  -<em>Type of body temperature device</em> MAY be used as additional observations</td>
			<td>Cel, [degF]</td>
		</tr>
		<tr>
			<td>Body height</td>
			<td>8302-2</td>
			<td>
				<em>Body height</em>
			</td>
			<td>cm, [in_i]</td>
		</tr>
		<tr>
			<td>Body length</td>
			<td>8306-3</td>
			<td>
				<em>Body height --lying</em> - Like height, but lying down, typically this is used for infants</td>
			<td>cm, [in_i]</td>
		</tr>
		<tr>
			<td>Head circumference</td>
			<td>8287-5</td>
			<td>
				<em>Head Occipital-frontal circumference by Tape measure</em>
			</td>
			<td>cm, [in_i]</td>
		</tr>
		<tr>
			<td>Body weight</td>
			<td>29463-7</td>
			<td>
				<em>Body weight</em> - To supplement this vital sign observation, 8352-7  - <em>Clothing worn during measure</em>  and  8361-8 - <em>Body position with respect to gravity</em> MAY be used as additional observations.</td>
			<td>g, kg,[lb_av]</td>
		</tr>
		<tr>
			<td>Body mass index</td>
			<td>39156-5</td>
			<td>
				<em>Body mass index (BMI) [Ratio]</em>
			</td>
			<td>kg/m2</td>
		</tr>
		<tr>
			<td>Blood pressure systolic and diastolic</td>
			<td>55284-4</td>
			<td>
				<em>Blood pressure systolic and diastolic</em> - This is component observation.  It has no value in Observation.valueQuantity and  contains at least one component (systolic and/or diastolic).  To supplement this vital sign observation, 8478-0  - <em>Mean blood pressure</em>, 8357-6 - <em>Blood pressure method</em>, 41904-4 - <em>Blood pressure measurement site</em>, 8358-4 - <em>Blood pressure device cuff size</em>, 41901-0 - <em>Type of blood pressure device</em>  MAY be used as additional observations.</td>
			<td>-</td>
		</tr>
		<tr>
			<td>Systolic blood pressure</td>
			<td>8480-6</td>
			<td>
				<em>Systolic blood pressure</em> - Observation.component code for a blood pressure Observation</td>
			<td>mm[Hg]</td>
		</tr>
		<tr>
			<td>Diastolic blood pressure</td>
			<td>8462-4</td>
			<td>
				<em>Diastolic blood pressure</em> - Observation.component code for a blood pressure Observation</td>
			<td>mm[Hg]</td>
		</tr>
	</tbody>
</table>
		
---

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


[Observation]: http://hl7.org/fhir/2017Jan/observation.html
[extensible]: http://hl7.org/fhir/2017Jan/terminologies.html#extensible
[Conformance requirements for the US-Core Server]: CapabilityStatement-server.html
[General Guidance Section]: definitions.html
