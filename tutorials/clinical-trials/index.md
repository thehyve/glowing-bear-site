# Glowing Bear for querying clinical trials
{: .no_toc}

Glowing Bear is a powerful cohort selector on top of all internal clinical
trial data, combined with publicly available data, within a pharmaceutical
company.

The following tutorial is using three publicly available studies from the
[Gene Expression Omnibus](https://www.ncbi.nlm.nih.gov/geo/) on Multiple
Sclerosis.

You can execute this tutorial on our
[public demonstration server](/getting-started) of Glowing Bear.

# Table of contents
{: .no_toc}

* TOC
{:toc}
{::options toc_levels="1,2" /}

# Step 1: Data overview

In the [Ontology tree panel](/docs/#ontology-tree), there are many different
datasets loaded, including three Multiple Sclerosis studies from the Gene
Expression Omnibus, placed under _Public Studies_:

![Multiple Sclerosis studies from the Gene Expression Omnibus][clinical-trials]

More information on these studies can be found on GEO:
* GSE46293: [Expression data of multiple sclerosis patients receiving Interferon-beta therapy](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE46293)
* GSE33464: [Expression data of multiple sclerosis patients receiving subcutaneous Interferon-beta-1a therapy [U133 Plus 2.0]](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE33464)
* GSE42763: [Expression data of multiple sclerosis patients receiving glatiramer acetate therapy [U133 Plus 2.0]](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE42763)

A subset of the data for these studies has also been harmonized, found here in the tree:
![Harmonized data from GEO studies][clinical-trials-harmonized]

<div class='note'></div>
**Tip:** Use the search box in the Ontology tree panel to find any study or
variable of interest.

# Step 2: Cohort Selection

Based on the general information on
[Data Selection in the user manual](/docs/#data-selection), see if
you are able to recreate the following patient cohort selection:

![Cohort selection on clinical trial data][clinical-trial-cohort-selection]

<div class='note'></div>
**Tip:** Always click the _Update_ button after you made any changes to your query,
to execute the query you have made.

<div class='note'></div>
**Tip:** To create a new query criterion, either drag a variable or study from
the Ontology tree or start typing in the _Add criterion_ box directly.

# Step 3: Data Analysis

Can you find out which treatments are used (exclusively) against which Multiple
Sclerosis related disease?

1. First make a cohort selection with all 26 patients from the above mentioned
GEO studies in Step 1 of the [Data Selection tab](/docs/#data-selection) and
click on Update.
1. Select all variables in Step 2 of the Data Selection tab and click on Update.
1. Move to the [Analysis tab](/docs/#analysis).
1. Make a cross table of variable Diagnosis (under _Shared Design Factors_)
against Treatment Type (under _Shared Clinical Data_).

![Cross table on clinical trial data][clinical-trial-cross-table]

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

[clinical-trials]: /tutorials/images/clinical-trials.png
[clinical-trials-harmonized]: /tutorials/images/clinical-trials-harmonized.png
[clinical-trial-cohort-selection]: /tutorials/images/clinical-trial-cohort-selection.png
[clinical-trial-cross-table]: /tutorials/images/clinical-trial-cross-table.png
