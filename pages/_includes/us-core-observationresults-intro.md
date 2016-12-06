Laboratory results are grouped and summarized using the [DiagnosticReport] resource which reference [Observation] resources.  Each Observation resource represents an individual laboratory test and result value, a “nested” panel (such as a microbial susceptibility panel) which references other observations, or rarely a laboratory test with component result values. This profile sets minimum expectations for the Observation resource resource to record, search and fetch laboratory test results associated with a patient.  It identifies which core elements, extensions, vocabularies and value sets **SHALL** be present in the resource when using this profile.

**Example Usage Scenarios:**

The following are example usage scenarios for the US Core-Results profile:

-   Query for lab results belonging to a Patient
-   Record lab results belonging to a Patient

##### Mandatory Data Elements and Terminology


The following data-elements are mandatory (i.e data MUST be present). These are presented below in a simple human-readable explanation.  Profile specific guidance and examples are provided as well.  The [**Formal Profile Definition**](#profile) below provides the  formal summary, definitions, and  terminology requirements.  

**Each Observation must have:**

1.   a status
1.   a category code of 'laboratory'
1.   a [LOINC] code, if available, which tells you what is being measured
1.   a patient
1.   a result value and, if the result value is a numeric quantity, a standard [UCUM] unit


Each Observation *should* have:

1.   a time indicating when the measurement was taken
1.   a reference range if available


**Profile specific implementation guidance:**

* Additional codes that translate or map to the Observation code or category codes are allowed.  For example:
   -  providing both a local system codes and a LOINC code that it map to
   -  providing a more specific category codes such as "chemistry', [SNOMED CT] concepts, or system specific codes in addition to the "laboratory" category code.
* If there is no result then you have to supply a reason unless Observation is being used to group other results then there is no value. Instead, it includes composite values or references to other Observations
* See the [General Guidance Section] for further guidance on using UCUM

#### Examples

 - [observation-usg]Observation-usg.html)
 - [observation-urobilinogen]Observation-urobilinogen.html)
 - [observation-urine-wbcs]Observation-urine-wbcs.html)
 - [observation-urine-sediment]Observation-urine-sediment.html)
 - [observation-urine-rbcs]Observation-urine-rbcs.html)
 - [observation-urine-protein]Observation-urine-protein.html)
 - [observation-urine-ph]Observation-urine-ph.html)
 - [observation-urine-nitrite]Observation-urine-nitrite.html)
 - [observation-urine-leukocyte-esterase]Observation-urine-leukocyte-esterase.html)
 - [observation-urine-ketone]Observation-urine-ketone.html)
 - [observation-urine-hemoglobin]Observation-urine-hemoglobin.html)
 - [observation-urine-glucose]Observation-urine-glucose.html)
 - [observation-urine-epi-cells]Observation-urine-epi-cells.html)
 - [observation-urine-color]Observation-urine-color.html)
 - [observation-urine-clarity]Observation-urine-clarity.html)
 - [observation-urine-cells]Observation-urine-cells.html)
 - [observation-urine-bilirubin]Observation-urine-bilirubin.html)
 - [observation-urine-bacteria]Observation-urine-bacteria.html)
 - [observation-serum-total-bilirubin]Observation-serum-total-bilirubin.html)
 - [observation-serum-sodium]Observation-serum-sodium.html)
 - [observation-serum-potassium]Observation-serum-potassium.html)
 - [observation-serum-creatinine]Observation-serum-creatinine.html)
 - [observation-serum-co2]Observation-serum-co2.html)
 - [observation-serum-chloride]Observation-serum-chloride.html)
 - [observation-serum-calcium]Observation-serum-calcium.html)
 - [observation-oxygen-saturation]Observation-oxygen-saturation.html)
 - [observation-neutrophils]Observation-neutrophils.html)
 - [observation-mchc]Observation-mchc.html)
 - [observation-hemoglobin]Observation-hemoglobin.html)
 - [observation-erythrocytes]Observation-erythrocytes.html)
 - [observation-BUN]Observation-BUN.html)
 - [observation-blood-pressure]Observation-blood-pressure.html)
 - [observation-blood-glucose]Observation-blood-glucose.html)

 [SNOMED CT]: http://snomed.info/sct
  [Observation Value Absent Reason]: http://hl7.org/fhir/2017Jan/valueset-observation-valueabsentreason.html
  [UCUM]: http://unitsofmeasure.org
  [LOINC]: http://loinc.org
[Observation]:  http://hl7.org/fhir/2017Jan/observation.html
[DiagnosticReport]:  http://hl7.org/fhir/2017Jan/diagnosticreport.html
[General Guidance Section]: definitions.html
