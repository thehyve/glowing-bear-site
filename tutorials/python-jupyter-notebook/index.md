# Data analysis with Python and Jupyter Notebook
{: .no_toc}

![Plot made in Python with the data retrieved from Glowing Bear][glowing-bear-python-plot]{: .small-image-right}

With [the powerful API](/docs/technical/#transmart-api), you can easily retrieve
data from Glowing Bear to use in your programming language of choice. For Python
there is a
[dedicated client library](/docs/installation/#python-api-client) to natively
access the data. This is especially useful in
[Jupyter Notebook](https://jupyter.org/), as we'll see below.

The following tutorial is using the
[SyntheticMass dataset](https://syntheticmass.mitre.org/), an open source
synthetic patient and population health data that simulates the state of
Massachusetts in 2021.

# Table of contents
{: .no_toc}

* TOC
{:toc}
{::options toc_levels="1,2" /}

# Exercise 1: Querying and analysis

In this exercise we will teach you:
* How to connect to a Glowing Bear server in Python
* How to explore the data in the Server
* How to create a patient query
* How to retrieve and analyse the selected patients and observations

<a href="https://mybinder.org/v2/gh/thehyve/transmart-api-client-py/master?urlpath=/lab/tree/examples/Example.ipynb" target="_blank">![Binder](https://mybinder.org/badge.svg)</a>

Go to <a href="https://mybinder.org/v2/gh/thehyve/transmart-api-client-py/master?urlpath=/lab/tree/examples/Example.ipynb" target="_blank">the interactive Jupyter Notebook with the exercise</a> or
<a href="https://github.com/thehyve/transmart-api-client-py/blob/master/examples/Example.ipynb" target="_blank">download the Notebook</a> to run it on your own computer.

# Exercise 2: Administration

The API is also very useful to perform administrative tasks, like the rebuilding
of the caches after you have loaded new data.

<div class='note'></div>
**Note:** Your user account on Glowing Bear will need to have _admin_ rights to
perform this exercise.

In this exercise we will teach you:
* How to rebuild the Glowing Bear cache after data loading
* How to validate the new data has indeed been loaded

<a href="https://mybinder.org/v2/gh/thehyve/transmart-api-client-py/master?urlpath=/lab/tree/examples/Example-administration.ipynb" target="_blank">![Binder](https://mybinder.org/badge.svg)</a>

Go to <a href="https://mybinder.org/v2/gh/thehyve/transmart-api-client-py/master?urlpath=/lab/tree/examples/Example-administration.ipynb" target="_blank">the interactive Jupyter Notebook with the exercise</a> or
<a href="https://github.com/thehyve/transmart-api-client-py/blob/master/examples/Example-administration.ipynb" target="_blank">download the Notebook</a> to run it on your own computer.


[glowing-bear-python-plot]: /tutorials/images/glowing-bear-python-plot.png
