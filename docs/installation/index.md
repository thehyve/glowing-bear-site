# Installation
{: .no_toc}

This page provides more information on how to install the Glowing Bear with its components and
other tools of the Glowing Bear ecosystem. More [technical information](/docs/technical)
is available too.

If you need help installing Glowing Bear or tranSMART, please do not hesitate to
[reach out to The Hyve](https://thehyve.nl/contact/).

# Table of contents
{: .no_toc}

* TOC
{:toc}
{::options toc_levels="1,2" /}

# Install Glowing Bear and its components

The Glowing Bear consists of a decoupled user interface on one or
two backends.
There are two ways to install Glowing bear in its components. One way is using Docker, [check the Github page](https://github.com/thehyve/glowing-bear-docker) to try the Docker scripts for Glowing Bear. Another way is to install each component separetly, and the instructions for this procedure are provided below.

<table>
  <tr>
    <th>Date</th>
    <th>Status</th>
    <th><a href="#glowing-bear-interface">Glowing Bear interface</a></th>
    <th><a href="#transmart-api-server">tranSMART API Server</a></th>
    <th><a href="#glowing-bear-backend">Glowing Bear backend</a></th>
  </tr>
  <tr>
    <td>28-05-2019</td>
    <td>Stable</td>
    <td>
    2.0.0<br/>
    <a href="https://github.com/thehyve/glowing-bear/releases/tag/2.0.0">Github</a> /
    <a href="https://repo.thehyve.nl/content/repositories/releases/nl/thehyve/glowing-bear/2.0.0/">Repo</a>
    </td>
    <td>
    v17.1-hyve-5.9<br/>
    <a href="https://github.com/thehyve/transmart-core/releases/tag/v17.1-hyve-5.9">Github</a> /
    <a href="https://repo.thehyve.nl/content/repositories/releases/org/transmartproject/transmart-api-server/17.1-HYVE-5.9/">Repo</a>
    </td>
     1.0.0<br/>
    <a href="https://github.com/thehyve/gb-backend/releases/tag/v1.0.0">Github</a> /
    <a href="https://repo.thehyve.nl/content/repositories/releases/nl/thehyve/gb-backend/1.0.0/">Repo</a>
    </td>
    <td>
  </tr>
</table>

## Glowing Bear interface
Installation of Glowing Bear is documented on in the
[README.md on Github](https://github.com/thehyve/glowing-bear#how-to-install).

Releases are available in [Github releases](https://github.com/thehyve/glowing-bear/releases) and as pre-built artifacts in [the The Hyve repo server](https://repo.thehyve.nl/content/repositories/releases/nl/thehyve/glowing-bear/).

## tranSMART API server
Glowing Bear talks via the REST API to a tranSMART server. The installation
instructions for the tranSMART server is documented in
[that Github repository](https://github.com/thehyve/transmart-core/tree/dev/docs#transmart-171-installation).

Releases are available in [Github releases](https://github.com/thehyve/transmart-core/releases) and as pre-built artifacts in [the The Hyve repo server](https://repo.thehyve.nl/content/repositories/releases/org/transmartproject/transmart-api-server/).

## Glowing Bear backend
In the latest versions part of the functionality Glowing Bear needs (saved
cohorts and subscriptions to them) has been moved out of the tranSMART server,
to its own dedicated [Glowing Bear backend](https://github.com/thehyve/gb-backend).

Releases are available in [Github releases](https://github.com/thehyve/gb-backend/releases) and as pre-built artifacts in [the The Hyve repo server](https://repo.thehyve.nl/content/repositories/releases/nl/thehyve/gb/backend/gb-backend/).

# Other tools

## Python API client

The Python API client for tranSMART can used to extract data from the tranSMART
server, while respecting the access rights, into a Python environment. For
example within Jupyter Notebooks. It can be installed with `pip` as [documented in
the Github repository](https://github.com/thehyve/transmart-api-client-py#installation).

Explore what you can do with the Python client with this
[online tutorial](/tutorials/python-jupyter-notebook).

## tranSMART toolkit (tmtk) data extraction and transformation

The data extraction and transformation toolkit can be used to prepare data to be
loaded into the tranSMART server. The installation information is [documented in
the Github repository](https://github.com/thehyve/tmtk#installation).

## tranSMART Copy data loader

Next the data prepared with tmtk can be loaded to the tranSMART server with
tranSMART Copy, which is [documented in the Github repository](https://github.com/thehyve/transmart-core/tree/dev/transmart-copy).
