# Technical documentation
{: .no_toc}

This page provides technical information on the Glowing Bear data warehouse. For
more information on how to install Glowing Bear please see
[the Installation page](/docs/installation).

Do [reach out to The Hyve](https://thehyve.nl/contact/) if you have any
questions.

# Table of contents
{: .no_toc}

* TOC
{:toc}
{::options toc_levels="1,2" /}

# Glowing Bear architecture

The Glowing Bear data warehouse consists of a decoupled user interface on one or
two backends.

* [Glowing Bear interface Github repository](https://github.com/thehyve/glowing-bear)
* [tranSMART API server Github repository](https://github.com/thehyve/transmart-core)
* [Glowing Bear backend Github repository](https://github.com/thehyve/gb-backend)

The following **architecture diagram** summarizes how tranSMART, Glowing Bear and
other (optional) components interact:


![Glowing Bear and tranSMART architecture][Glowing_Bear_TranSMART_architecture]

# tranSMART API

The [interactive documentation for the tranSMART 17.1 API is available here](https://transmart.thehyve.net/open-api/), via Open API's Swagger.

# tranSMART data model

Below is the **class model** for tranSMART Glowing Bear, giving the relationship
between all core concepts:

![tranSMART Glowing Bear class diagram][transmart_gb_class_diagram]

With this data model we can model both *health care datasets*, having absolute
timestamps and hospital visits, and *studies and clinical trials*, by using the
study and study-specific visits.

In the flexible star-schema data model, the observations have the following dimensions:
* **Patient**: For uniquely capturing the study subject
* **Concept**: For capturing the variable in a tree hierarchy structure
* **Start/End Date**: Absolute timestamps linked to the specific observation
* **Instance Num**: A follow number allowing to differentiate otherwise identical observations, like technical replicates
* **(Patient) Visit / Encounter**: The patient specific visit, like for example a hospital visit, bundling multiple observations from the same patient. It can have it’s own absolute start and end date.
* **Trial Visit**: The visit shared over multiple patients, for example specific visits in a clinical trial, like ‘Baseline’ and ‘Week 1’.
The trial visit can have:
   * A human readable *Label*, for example ‘Week 1’
   * A *Value* and *Unit* for capturing structured information on the visit, like ‘7’ and ‘Days’
* The trial visit is also the link to the **Study**, uniquely identifying clinical trials or other studies or dataset groupings. This dimension is also used for defining data access per user.
* **Modifier**: This dimension allows for capturing any other metadata on the observation, like the dosage or way of administering. It allows theoretically for adding an infinite amount of extra dimensions.

Full, interactive documentation of the tranSMART 17.1 data model is [made
available here via SchemaSpy](https://thehyve.github.io/transmart-core-db-doc/).

You can also generate the most recent documentation yourself with Schema Spy,
and read design decisions [on the Github repository](https://github.com/thehyve/transmart-core/tree/dev/transmart-data/db-doc).


[Glowing_Bear_TranSMART_architecture]: /docs/images/Glowing_Bear_TranSMART_architecture.png
[transmart_gb_class_diagram]: /docs/images/transmart_gb_class_diagram.jpg
