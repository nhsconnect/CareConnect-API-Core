---
title: Introduction to the Care Connect Core API
keywords: homepage
tags: [overview]
sidebar: overview_sidebar
permalink: index.html
toc: false
summary: A brief introduction to the Care Connect Core API
---

{% include important.html content="This site is under active development by NHS Digital in collaboration with INTEROPen and is intended to provide all the technical resources you need to successfully develop the Care Connect Core API. This project is being developed using an agile methodology so iterative updates to content will be added on a regular basis." %}

<!-- include important.html content="This site is under active development by NHS Digital on behalf of INTEROPen and is intended to provide all the technical resources you need to successfully develop the Care Connect Core API. This project is being developed using an agile methodology so iterative updates to content will be added on a regular basis." -->

# Introduction #

<!--
This is the Care Connect Get Unstructured Document RESTful FHIR STU3 ‘Read Only’ experimental API implementation guide. It is a component specification of the Care Connect API (CCAPI) suite. 
-->

The Care Connect RESTful APIs have been developed by NHS Digital in collaboration with the INTEROPen community. These APIs aim to  better support the delivery of care by opening up information and data held across different clinical care settings through the use of nationally defined INTEROPen FHIR® resources.
<!--
The Care Connect RESTful APIs have been developed collaboratively by NHS Digital and the INTEROPen community. These APIs aim to  better support the delivery of care by opening up information and data held across different clinical care settings through the use of nationally defined INTEROPen FHIR® resources.
-->

The Care Connect RESTful APIs are Based on FHIR STU3 and define the minimum conformance requirements and standards for retrieving patient data and records.

The INTEROPen vision is to create a library of nationally defined HL7® FHIR® resources and interaction patterns that implementers can adopt to simplify integration and interoperability within UK health and social care.

Find out more on the [INTEROPen website](http://interopen.org/).


# Care Connect Core API #

The Care Connect Core API RESTful FHIR STU3 Implementation Guide is a component of the Care Connect API specification suite. 

The initial core API has been created to provide read only access to fine grained information represented in FHIR resources.

The resources in scope for this API are:


<table style="min-width:100%;width:100%">
<tr id="clinical">
<th style="width:33%;">Clinical</th>
<th style="width:33%;">&nbsp;</th>
<th style="width:33%;">&nbsp;</th>
</tr>
<tr id="clinicald">
<th>Summary</th>
<th>Diagnostics</th>
<th>Medications</th>
</tr>
<tr>
<td><a href="api_clinical_allergyintolerance.html">AllergyIntolerance</a></td>
<td><a href="api_diagnostics_observation.html">Observation</a></td>
<td><a href="api_medication_medication.html">Medication</a></td>
</tr>
<tr>
<td><a href="api_clinical_condition.html">Condition</a> (Problem)</td>
<td>&nbsp;</td>
<td><a href="api_medication_medicationorder.html">MedicationOrder</a></td>
</tr>
<tr>
<td><a href="api_clinical_procedure.html">Procedure</a></td>
<td>&nbsp;</td>
<td><a href="api_medication_medicationstatement.html">MedicationStatement</a></td>
</tr>
<tr>
<td>&nbsp;</td>
<td>&nbsp;</td>
<td><a href="api_medication_immunization.html">Immunization</a></td>
</tr>
</table>

<table style="min-width:100%;width:100%">
<tr id="base">
<th style="width:33%;">Base</th>
<th style="width:33%;">&nbsp;</th>
<th style="width:33%;">&nbsp;</th>
</tr>
<tr id="based">
<th>Individuals</th>
<th>Entities</th>
<th>Management</th>
</tr>
<tr>
<td><a href="api_entity_patient.html">Patient</a></td>
<td><a href="api_entity_organisation.html">Organization</a></td>
<td><a href="api_management_encounter.html">Encounter</a></td><td></td>
</tr>
<tr>
<td><a href="api_entity_practitioner.html">Practitioner</a></td>
<td><a href="api_entity_location.html">Location</a></td>
<td>&nbsp;</td>
</tr>
<tr>
<td><a href="api_entity_practitioner_role.html">PractitionerRole</a></td>
<td>&nbsp;</td>
<td>&nbsp;</td>
</tr>
</table>




<!--
-	AllergyIntolerance
-	Condition
-	Encounter
-	Immunization
-	Location
-	Medication
-	MedicationRequest
-	MedicationStatement
-	Observation
-	Organization
-	Patient
-	Practitioner
-	PractitionerRole
-	Procedure
-->

# API Query Mechanism and Conformance #

The API intends to mandate a minimal set of the query mechanism to ensure the maximum number of systems can implement the API.

 Query parameters conformance will be categorised as:

- <b>MUST</b> – these search parameters MUST be implemented for the specified resource type
- <b>SHOULD</b> – these search parameters are expected to be implemented, if the data to support the query is present in the host system

Additional search parameters MAY be added to reflect local requirements.

To be conformant, provider systems are required to implement all of the MUST parameters.

All search parameters MUST be described in the FHIR CapabilityStatement.

<!--
# Core API Roadmap #

The diagram outlines the development roadmap for the Core API.
-->

<!-- include custom/under.construction.html content="Please check back later for any updates to this section." -->

<!--
<img src="images/roadmap/CoreAPIRoadmapv0.2.png">
-->



<!--
[CoreAPIRoadmapv0.1](CoreAPIRoadmapv0.1.PNG)
-->




<!--

# Using this guide #

This guide has been created to support the adoption of the "your project here" profiles and FHIR resources. As such the site is structured around stakeholders including API users, developers and architects, who have an interest in implementing the "your project here"

Need to add include here....

-->
