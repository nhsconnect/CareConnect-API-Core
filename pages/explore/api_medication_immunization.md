---
title: Medication | Immunization
keywords: getcarerecord, structured, rest, immunization
tags: [fhir]
sidebar: accessrecord_rest_sidebar
permalink: api_medication_immunization.html
summary: Describes the event of a patient being administered a vaccination or a record of a vaccination as reported by a patient, a clinician or another party and may include vaccine reaction information and what vaccination protocol was followed.
---
{% include custom/search.warnbanner.html %}

{% include custom/fhir.STU3.reference.html resource="Immunization" page="CareConnect-Immunization-1" fhirname="Immunization" fhirlink="immunization.html" content="User Stories" userlink="engage_michaelsstory.html" %}



## 1. Read ##

<div markdown="span" class="alert alert-success" role="alert">
GET [baseUrl]/Immunization/[id]</div>

{% include custom/read.response.html resource="Immunization" content="" %}

## 2. Search ##

<div markdown="span" class="alert alert-success" role="alert">
GET [baseUrl]/Immunization?[searchParameters]</div>

Search for all immunization resources for a patient. Fetches a bundle of all `Immunization` resources for the specified patient.

{% include custom/search.header.html resource="Immunization" %}

### 2.1. Search Parameters ###

{% include custom/search.parameters.combinations.html resource="Immunization" link="immunization.html#search" %}

<table style="min-width:100%;width:100%">
<tr id="clinical">
    <th style="width:10%;">Name</th>
    <th style="width:15%;">Type</th>
    <th style="width:40%;">Description</th>
    <th style="width:5%;">Conformance</th>
    <th style="width:30%;">Path</th>
</tr>
<tr>
    <td><code class="highlighter-rouge">notgiven</code></td>
    <td><code class="highlighter-rouge">token</code></td>
    <td>Administrations which were not given</td>
    <td>MUST</td>
    <td>Immunization.notGiven</td>
</tr>
<tr>
    <td><code class="highlighter-rouge">patient</code></td>
    <td><code class="highlighter-rouge">reference</code></td>
    <td>The patient for the vaccination record</td>
    <td>MUST</td>
    <td>Immunization.patient<br>(Patient)</td>
</tr>
<tr>
    <td><code class="highlighter-rouge">status</code></td>
    <td><code class="highlighter-rouge">token</code></td>
    <td>Immunization event status</td>
    <td>MUST</td>
    <td>Immunization.status</td>
</tr>
<tr>
    <td><code class="highlighter-rouge">vaccination-procedure-code</code></td>
    <td><code class="highlighter-rouge">token</code></td>
    <td>Procedure code to identify the stage in the immunisation schedule</td>
    <td>SHOULD</td>
    <td>Immunization.vaccinationProcedure</td>
</tr>
</table>

<!--
<tr>
    <td><code class="highlighter-rouge">date</code></td>
    <td><code class="highlighter-rouge">date</code></td>
    <td>Vaccination (non)-Administration Date</td>
    <td>SHOULD</td>
    <td>Immunization.date</td>
</tr>
-->


{% include custom/search.parameters.combos.html resource="Immunization"  link="immunization.html#search" %}

<!--
Systems MUST support the following search combinations:

* patient + notgiven
* patient + status

Systems SHOULD support the following search combinations:

* patient + vaccination-procedure-code
-->
<table style="min-width:100%;width:100%">
<tr i
d="clinical">
    <th style="width:40%;">Parameter Combinations</th>
    <th style="width:25%;">Type</th>
    <th style="width:35%;">Conformance</th>
</tr>
<tr>
    <td><code class="highlighter-rouge">patient + notgiven</code></td>
    <td><code class="highlighter-rouge">reference + token</code></td>
    <td>MUST</td>
</tr>
<tr>
    <td><code class="highlighter-rouge">patient + status</code></td>
    <td><code class="highlighter-rouge">reference + token</code></td>
    <td>MUST</td>
</tr>
<tr>
    <td><code class="highlighter-rouge">patient + vaccination-procedure-code</code></td>
    <td><code class="highlighter-rouge">reference + token</code></td>
    <td>SHOULD</td>
</tr>
</table>

This section outlines the search parameter syntax used, with some examples provided.



<!--
| `dose-sequence` | `number` | Dose number within series |  | 	Immunization.vaccinationProtocol.doseSequence |
| `notgiven` | `token` | Administrations which were not given | | Immunization.wasNotGiven |
| `lot-number` | `string` | Vaccine Batch Number |  | Immunization.lotNumber |
| `vaccine-code` | `token` | Vaccine Product Administered |  | Immunization.vaccineCode |
-->

<!--
{% include custom/search.date.html para="2.1.1." content="Immunization" %}
-->

{% include custom/search.status.plus.html para="2.1.1." name="notgiven" content="Immunization" options="true | false" selected="false" %}

{% include custom/search.patient.html para="2.1.2." content="Immunization" %}

{% include custom/search.status.plus.html para="2.1.3." name="status" content="Immunization" options="completed | entered-in-error" selected="completed" %}

{% include custom/search.vaccinationprocedure.html para="2.1.4." name="vaccination-procedure-code" content="Immunization" options="completed" selected="completed" %}

{% include custom/search.response.html resource="Immunization" %}


## 3. Example ##

### 3.1 Request Query ###

<h3 id="32-response-headers">3.1 cURL</h3>

Return all Immunization resources with an id of 1, the format of the response body will be xml. The Reference Implementation is hosted at '{{ site.fhir_ref_impl }}'.

{% include custom/embedcurl.html title="Search Immunization" command="curl -X GET -H 'Accept: application/fhir+xml' -H 'Authorisation: BEARER [token]' -v 'https://data.developer.nhs.uk/ccri-fhir/STU3/Immunization?patient=1'" %}

<h3 id="32-response-headers">3.2 Explore the Response</h3>

Explore the response in XML & JSON on the Reference Implementation below
<div class="language-http highlighter-rouge">
<pre class="highlight">
<p style="font-size: 110%;">Reference Implementation</p>
XML <a target="_blank" href="{{ site.fhir_ref_impl }}search?serverId=home&pretty=true&resource=Immunization&param.0.0=&param.0.1=1&param.0.name=patient&param.0.type=reference&resource-search-limit=&encoding=xml">Patient id search RI viewer</a>
JSON <a target="_blank" href="{{ site.fhir_ref_impl }}search?serverId=home&pretty=true&resource=Immunization&param.0.0=&param.0.1=1&param.0.name=patient&param.0.type=reference&resource-search-limit=&encoding=json">Patient id search RI viewer</a>
</pre>
</div>
