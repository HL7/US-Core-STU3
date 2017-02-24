---
# jekyll header
---
{% include header.html %}

  <!-- ============BreadCrumb=============== -->

{% include container-start.html %}

  <!-- ============CONTENT CONTENT=============== -->


## ValueSets, CodeSystems, and ConceptMaps defined as part of the US-Core implementation Guide:

See the [guidance section](guidance.html) in this guide as well in the [FHIR specification](file://hl7.fhir.org/terminologies.html) for using codes in resources.

## Value Sets

The [FHIR terminology section](file://hl7.fhir.org/terminologies-valuesets.html) lists of all the value sets defined as part of the FHIR specification. These additional value sets have been defined for this implementation guide.

|URI|Source|Comment|OID (for non-FHIR systems)
|---|---|---|---|
|**Externally Published code systems**||||
|http://snomed.info/sct|SNOMED CT (IHTSDO)|See Using SNOMED CT with FHIR|2.16.840.1.113883.6.96
|**US Core defined code systems**||||
|http://snomed.info/sct|SNOMED CT (IHTSDO)|See Using SNOMED CT with FHIR|2.16.840.1.113883.6.96

### Code Systems

See the [FHIR terminology section](file://hl7.fhir.org/terminologies-systems.html) for a complete discussion on code systems and a list of codes system names used in FHIR. The following additional names (URIs) have been identified for this implementation guide,   If a URI is listed here, it **SHALL** be used in the US Core profiles in preference to any other code system name.

|URI|Source|Comment|OID (for non-FHIR systems)
|---|---|---|---|
|**Externally Published code systems**||||
|http://snomed.info/sct|SNOMED CT (IHTSDO)|See Using SNOMED CT with FHIR|2.16.840.1.113883.6.96
|**US Core defined code systems**||||
|http://snomed.info/sct|SNOMED CT (IHTSDO)|See Using SNOMED CT with FHIR|2.16.840.1.113883.6.96

### ConceptMaps

The following concept mappings have been defined as part of the this guide.

  {% include list-simple-conceptmaps.xhtml %}
<p>
</p>

  <!-- ==============END CONTENT END CONTENT=================== -->

{% include container-end.html %}

    {% include footer.html %}
