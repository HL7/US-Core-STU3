#### Summary of the Mandatory Requirements

1.  Conditionally One clinical status in `AllergyIntolerance.clinicalStatus`
    - [Invariants](http://hl7.org/fhir/STU3/allergyintolerance.html#invs)
    - `AllergyIntolerance.clinicalStatus` has a [required](http://hl7.org/fhir/STU3/terminologies.html#required) binding to [AllergyIntoleranceStatus](http://hl7.org/fhir/STU3/valueset-allergy-clinical-status.html) value set
1.  One code in `AllergyIntolerance.verificationStatus` which has a [required](http://hl7.org/fhir/STU3/terminologies.html#required) binding to:
    -   [AllergyIntoleranceVerificationStatus](http://hl7.org/fhir/STU3/valueset-allergy-verification-status.html) value set
1.  One Identification of a substance, or a class of substances, that is considered to be responsible for the adverse reaction risk in `AllergyIntolerance.code` which has an [extensible](http://hl7.org/fhir/STU3/terminologies.html#extensible) binding to:
    -    [US Core Core Substance-Reactant for Intolerance and Negation Codes](ValueSet-us-core-substance.html) value set
1.  One patient reference in `AllergyIntolerance.patient`
