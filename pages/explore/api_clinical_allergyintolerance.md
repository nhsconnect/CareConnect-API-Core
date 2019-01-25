---
title: Clinical | Allergy Intolerance
keywords: getcarerecord, structured, rest, allergy, intolerance
tags: [fhir, clinical, allergyintolerance, rest, api]
sidebar: accessrecord_rest_sidebar
permalink: api_clinical_allergyintolerance.html
summary: Risk of harmful or undesirable, physiological response which is unique to an individual and associated with exposure to a substance.
---
{% include custom/search.warnbanner.html %}

<!-- include custom/fhir.referencemin.html resource="[AllergyIntolerance](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-AllergyIntolerance-1)" userlink="" page="" fhirname="AllergyIntolerance" fhirlink="[AllergyIntolerance](https://www.hl7.org/fhir/STU3/AllergyIntolerance.html)" content="User Stories" userlink="engage_michaelsstory.html" -->


{% include custom/fhir.STU3.reference.html resource="Allergy Intolerance" page="CareConnect-AllergyIntolerance-1" fhirname="AllergyIntolerance" fhirlink = "allergyintolerance.html" content="User Stories" userlink="engage_michaelsstory.html" %}


## 1. Read ##

<div markdown="span" class="alert alert-success" role="alert">
GET [baseUrl]/AllergyIntolerence/[id]</div>

{% include custom/read.response.html resource="AllergyIntolerance" content="" %}

## 2. Search ##

<div markdown="span" class="alert alert-success" role="alert">
GET [baseUrl]/AllergyIntolerence?[searchParameters]</div>

Search for all allergies for a patient. Fetches a bundle of all `AllergyIntolerance` resources for the specified patient.

{% include custom/search.header.html resource="Allergy Intolerance" %}

### 2.1. Search Parameters ###

{% include custom/search.parameters.html resource="AllergyIntolerance"  link="allergyintolerance.html#search" %}

<table style="min-width:100%;width:100%">
<tr id="clinical">
    <th style="width:10%;">Name</th>
    <th style="width:15%;">Type</th>
    <th style="width:30%;">Description</th>
    <th style="width:5%;">Conformance</th>
    <th style="width:40%;">Path</th>
</tr>
<tr>
    <td><code class="highlighter-rouge">clinical-status</code></td>
    <td><code class="highlighter-rouge">token</code></td>
    <td>active | inactive | resolved</td>
    <td>SHOULD</td>
    <td>AllergyIntolerance.clinicalStatus</td>
</tr>
<tr>
    <td><code class="highlighter-rouge">code</code></td>
    <td><code class="highlighter-rouge">token</code></td>
    <td>Code that identifies the allergy or intolerance</td>
    <td>SHOULD</td>
    <td>AllergyIntolerance.code</td>
</tr>
<tr>
    <td><code class="highlighter-rouge">patient</code></td>
    <td><code class="highlighter-rouge">reference</code></td>
    <td>Who the sensitivity is for</td>
    <td>MUST</td>
    <td>AllergyIntolerance.patient<br>(Patient)</td>
</tr>
<tr>
    <td><code class="highlighter-rouge">verification-status</code></td>
    <td><code class="highlighter-rouge">token</code></td>
    <td>unconfirmed | confirmed</td>
    <td>MUST</td>
    <td>AllergyIntolerance.verificationStatus</td>
</tr>
</table>

<!--
<tr>
    <td><code class="highlighter-rouge">date</code></td>
    <td><code class="highlighter-rouge">date</code></td>
    <td>When recorded</td>
    <td>MAY</td>
    <td>AllergyIntolerance.assertedDate</td>
</tr>
-->

Systems MUST support the following search combinations:

* patient + verification-status

Systems SHOULD support the following search combinations:

* patient + code
* patient + clinical-status

{% include custom/search.status.plus.html para="2.1.1." name="clinical-status" content="AllergyIntolerance" options="active | inactive | resolved" selected="active" %}

<!--
{% include custom/search.date.plus.html para="2.1.2." content="AllergyIntolerance" name="date" %}
-->

{% include custom/search.code.allergyIntolerance.html para="2.1.2." content="AllergyIntolerance" name="code" %}

{% include custom/search.patient.html para="2.1.3." content="AllergyIntolerance" %}

{% include custom/search.verificationstatus.plus.html para="2.1.4." name="verification-status" content="AllergyIntolerance" options="unconfirmed | confirmed" selected="unconfirmed" %}


{% include custom/search.response.html resource="AllergyIntolerance" %}


## 3. Example ##

<h3 id="32-response-headers">3.1 cURL</h3>

Return all AllergyIntolerance resources for Patient with an id of 1, the format of the response body will be xml. Replace 'baseUrl' with the actual base Url of the FHIR Server.

{% include custom/embedcurl.html title="Search AllergyIntolerance" command="curl -X GET -H 'Accept: application/fhir+xml' -H 'Authorisation: BEARER [token]' -v 'https://data.developer.nhs.uk/ccri-fhir/STU3/AllergyIntolerance?patient=1'" %}


<h3 id="32-response-headers">3.2 Explore the Response</h3>

Explore the response in XML & JSON on the Reference Implementation below
<div class="language-http highlighter-rouge">
<pre class="highlight">
<p style="font-size: 110%;">Reference Implementation</p>
XML <a target="_blank" href="{{ site.fhir_ref_impl }}search?serverId=home&pretty=true&resource=AllergyIntolerance&param.0.0=&param.0.1=1&param.0.name=patient&param.0.type=reference&resource-search-limit=&encoding=xml">Patient id search RI viewer</a>
JSON <a target="_blank" href="{{ site.fhir_ref_impl }}search?serverId=home&pretty=true&resource=AllergyIntolerance&param.0.0=&param.0.1=1&param.0.name=patient&param.0.type=reference&resource-search-limit=&encoding=json">Patient id search RI viewer</a>
</pre>
</div>
