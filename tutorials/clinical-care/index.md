# Glowing Bear for querying hospital records
{: .no_toc}

Glowing Bear is a powerful cohort selector on top of the hospital data
warehouse, allowing clinical researchers to easily find hospital patients of
interest.

The following tutorial is using the
[SyntheticMass dataset](https://syntheticmass.mitre.org/), an open source
synthetic patient and population health data that simulates the state of
Massachusetts in 2021.

You can execute this tutorial on our
[public demonstration server](/getting-started) of Glowing Bear.

# Table of contents
{: .no_toc}

* TOC
{:toc}
{::options toc_levels="1,2" /}


# Step 1: Data overview

![Multiple Sclerosis studies from the Gene Expression Omnibus][ehr-data-overview]{: .small-image-right}
The data from the SyntheticMass hospital data set is available in the
[Ontology tree panel](/docs/#ontology-tree) under the top-level folders
_Demographics_ and _Conditions_.

* It includes variables that are categorical (abc) or that are dates (the calendar
icon)
* The data under _Conditions_ is structured following the
[SNOMED Clinical Terms](https://bioportal.bioontology.org/ontologies/SNOMEDCT)
hierarchy, showcasing the support for ontologies.
* The _Conditions_ observations all have linked observation dates.

<div class='note'></div>
**Tip:** Use the search box in the Ontology tree panel to a specific SNOMED
term, by its name or code like [44054006](https://bioportal.bioontology.org/ontologies/SNOMEDCT?p=classes&conceptid=44054006) or [Type 2 diabetes mellitus](https://bioportal.bioontology.org/ontologies/SNOMEDCT?p=classes&conceptid=44054006).

# Step 2: Cohort Selection

Based on the general information on
[Data Selection in the user manual](/docs/#data-selection), see if
you are able to find how many _men_, _born before 1950_ had _Viral sinusitis
within the last 10 years_.

An possible solution is shown below:
![Example query on EHR data][ehr-cohort-selection]

<div class='note'></div>
**Tip:** Always click the _Update_ button after you made any changes to your query,
to execute the query you have made.

<div class='note'></div>
**Tip:** To create a new query criterion, either drag a variable or study from
the Ontology tree or start typing in the _Add criterion_ box directly.

# Step 3: Data Analysis

Can you find the gender and race distribution within patients with _Acute
bronchitis_?

1. First make a cohort selection with all 414 patients with _Acute bronchitis_
in Step 1 of the [Data Selection tab](/docs/#data-selection) and click on
Update.
1. Select all _Demographics_ variables in Step 2 of the Data Selection tab and
click on Update.
1. Move to the [Analysis tab](/docs/#analysis).
1. Make a cross table of variable Gender against Race, both from under the
_Demographics_ folder.

![Cross table on hospital record data][ehr-cross-table]

# Step 4: Data Export

1. Move to the [Data Export tab](/docs/#export).
1. Give your data selection a name and click on _Create Export_.
1. See that your export request has been added to the list and wait until it is
ready to download.
1. Click the _Download_ button and unpack the downloaded zip-file.
1. Open _data.tsv_ with Microsoft Excel or a similar program to view the data.

<div class='note'></div>
**Tip:** The other downloaded files will have more information on the dimensions
in the downloaded data, like _patient.tsv_, _concept.tsv_ and _study.tsv_.

[ehr-data-overview]: /tutorials/images/ehr-data-overview.png
[ehr-cohort-selection]: /tutorials/images/ehr-cohort-selection.png
[ehr-cross-table]: /tutorials/images/ehr-cross-table.png
