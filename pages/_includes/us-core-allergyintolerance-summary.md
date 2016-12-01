#### Summary of the Mandatory Requirements

1.  One status in `AllergyIntolerance.clinicalStatus` which has an [required](http://build.fhir.org/terminologies.html#required) binding to:
    -   [AllergyIntoleranceStatus](http://build.fhir.org/valueset-allergy-clinical-status.html) value set
1.  One Identification of a substance, or a class of substances, that is considered to be responsible for the adverse reaction risk in `AllergyIntolerance.code` which has an [extensible](http://build.fhir.org/terminologies.html#extensible) binding to:
    -    [US Core Core Substance-Reactant for Intolerance and Negation Codes](valueset-us-core-substance.html) value set
1.  One patient reference in `AllergyIntolerance.patient`
  
