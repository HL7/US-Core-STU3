#### Complete Summary of the Mandatory Requirements

1.  At least one (non-local) identifier in `Practitioner.identifier`
    -   NPI preferred
    -   Tax id is allowed
    -   Local id is allowed in addition to 'authoritative' identifier
1.  One name in `Practitioner.name`
1.  At least one practitioner role in `Practitioner.role`
    which must include a
    -   `Practitioner.role.organization`
    -   `Practitioner.role.code` which has an [required](http://build.fhir.org/terminologies.html#required) binding to:
        - [NUCC - Classification]
    -   `Practitioner.role.specialty` which has an [required](http://build.fhir.org/terminologies.html#required) binding to:
        - [NUCC - Specialization]
    -   `Practitioner.role.telecom`
    -   `Practitioner.role.location`
    -   `Practitioner.role.endpoint`
    


[NUCC - Classification]: valueset-us-core-provider-role.html
[NUCC - Specialization]: valueset-us-core-provider-specialty.html