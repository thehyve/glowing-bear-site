# User documentation
{: .no_toc}

Welcome to the Glowing Bear user documentation. If you are a new user looking for a short 
introduction, you can visit our **[quick start guide](/docs/quickstart)**.


More detailed information can be found below.

# Table of contents
{: .no_toc}

* TOC
{:toc}
{::options toc_levels="1,2" /}


# Left panel
The left panel contains information about the [Ontology tree](#ontology-tree), 
 [Cohorts](#cohorts) saved in the database and their [Variables](#Variables).

## Ontology tree

The ontology tree shows a hierarchy of data items that are available for your user. It contains concepts and studies and the number of subjects that have information for them. This tree is created when the data set is loaded into the database and the data items are *not necessarily* limited to existing terminologies.
Each node in the tree is either a folder, or one of the node types listed below. The number of subjects that have at least one observation for a specific variable is appended to the label. The nodes in the tree can be dragged into the right panel to compose criteria that define the group of subjects. Dragging one of the nodes automatically adds a criterion to the builder for the **concept and/or study** that is associated with this tree node. The concept criteria can be further specified to precisely compose your queries.
  
- ![icons 123][icons_123] numerical: *allows setting a minimum and maximum value*
- ![icons abc][icons_abc] categorical: *provides a list of options from which you can select*
- <span class="icon fa fa-calendar-o"></span> dates: *can set minimum and maximum dates*
- <span class="icon fa fa-newspaper-o"></span> free text: *no further options*
- ![icons study][icons_study] study: *no further options*

More details on subject selection can be found [further down](#Cohort-selection).

For some nodes, additional information is available when hovering over the label. This is 
indicated by an ⓘ information icon.

The search box in this panel allows you to search in the tree. Nodes that match the search string will be highlighted and opened for convenient access. Note that if there are too many search results, not all nodes will be opened, but the number of total results found is displayed below the search box.


## Cohorts
 
Cohorts you’ve created previously can be seen and restored from here. This is convenient if you frequently require information about the same (updated) group of subjects. The first cohort in the list is named *currently editing*. This shows the result of the user actions during data selection in the right window. 
When you click on a cohort name you can quickly visualise the number of subjects above the search box in this panel. If multiple cohorts are selected the number of subjects visualised is the union of the cohorts selected. However, be aware that if the cohorts contain overlapping subjects, these will be counted only one time.
Next to the cohorts name there are several buttons that allow the following actions:


- <span class="icon fa fa-rss"></span> subscribes you to this query: see [below](#cohort-subscription-for-subjects-and-samples)
- <span class="icon fa fa-star-o"></span> bookmarks this query, which is useful for sorting. 
  Bookmarked queries will also load faster if there is a lot of data in the database.
- <span class="icon fa fa-download"></span> downloads the query to a file, so you could share it 
  with a colleague
- <span class="icon fa fa-arrow-right"></span> restores the state of the query builder with this 
  saved query
- <span class="icon fa fa-times"></span> removes this query from this list, it cannot be retrieved

If you have previously downloaded a cohort, or received a file with a cohort query from a colleague, you can use the ``Import``  button to add this cohort to your list of saved cohorts. A cohort query file is specially formatted and is not meant to be created or edited by hand.


### Cohort subscription for subjects and samples

<div class="note"></div>
**Note:** this feature is available to users on request.

By subscribing yourself to a saved cohort you will receive an email when there are new subjects or samples found for the specified criteria. Any time new data is loaded, Glowing Bear will check whether you have access to any of the new subjects and samples information and notify about the changes.
If you expand the cohort box you will find below the cohort details, an additional button: “Show subscription records”. Clicking on this button you can check if there are any changes of the data related to the cohort saved. In particular the time and the IDs of items changed are reported


## Variables

The Variable panel shows the variables selected by the users’ actions during cohort selection. When opening or refreshing the page all the subjects of the dataset will be selected by default, meaning that in this panel all the variables are shown. The variables can be displayed in two ways: *Tree view* and *Category view*. Switching between the two views you can either opt for a hierarchical visualization of the variables or a plain list, respectively. 
This panel is present across the different windows: cohort selection, analysis and data export. The variables shown can be dragged and dropped or selected ( in the case of the data export window) for the specific window purpose.
A search box is also present, allowing to look for a specific variable either in the tree or the categorise view. 


# Right Panel

The right panel provides the main user functionality to interact with the database:
[Cohort selection](#cohort-selection), [Analysis](#analysis), and [Data Export](#data-export).

## Cohort selection

Once you are familiar with Glowing Bear you would start here to select criteria to create a data set that you want to use within the application. In the Cohort Selection panel the total subject counts of the database is shown by default in *Summary*. It is important to know that after choosing the desired criteria and requesting updated counts with the  Update cohort button, the displayed counts in the *Summary* line reflect that particular part of the data selection. el.


### Select a group of subjects
{: refdef id="data-selection-step-1"}

![Glowing Bear Step 1 image][query1_gb2.0]

You can select the group of subjects you are interested in three ways: by dragging nodes from the tree on the left, into add criteria box, typing into that box, or selecting them from a drop-down menu. Dragging tree nodes automatically adds constraints for a concept and/or study, e.g. ``Subjects with any value for '/Demographics/Gender'``. If you choose the drop-down menu option you can select the following options: 
  
- Study: all subjects included in the study with the specified identifier.
- Concept: all subjects with a value for the specified concept. Depending on the data type additional constraints can be specified, e.g. ``Subjects the value 'Male' for '/Demographics/Gender'``.
- Group: create a new ``and/or`` group to compose more complex queries.
- Pedigree (custom option): include all subjects that have the given relationship with at least one of the subjects in the specified subject set.

<div class="note"></div>
**Note:** adding no criteria in **Inclusion** criteria selects everyone in the database.

#### Extended query to custom subject dimension types
A cohort is created by selecting the variables of interest connected to a patient such as: gender, age, diagnosis, treatment, et cetera. Retrieving from the database, the information specifically contained in the so called “subject dimension type” for the patients. However, now you can choose to customize the subject dimension type to the needs and requirements of any given hospital, research institution or life science organization. Allowing the selection of a cohort, based on other subject information than patients. For example, in the box below the *Summary* subject counts, a drop-down menu shows the current available subject dimension options, such as: Patient, Diagnosis ID, Biosources ID, Biomaterials ID, and Images ID. This extension allows users to retrieve specific information on the selected dimensions independently from the others.

![Glowing Bear dimension type][subject_dimensions_gb2.0]

#### Group constraint creation

You can click on the ``+`` of the empty add criterion-box, to create a group constraint that allow you to build a more articulate and complex query. A complex query can be visualised as a series of constraints linked with ``and/or`` logic, and it can be imagined as a mathematical expression with parentheses. Those parenthesis are displayed with different range of blue vertical lines on the left side of the constraint boxes.

An example of a complex query sentence: 
``Give me all patients in the dataset that are female and were born between 1992 and 1997, and that have RNA or DNA biomaterials.``

The translation to mathematical expression with parentheses:

Give me all Patients = [(female) **AND** (born between 1992 and 1997)] **AND** [(RNA)  **OR** (DNA) biomaterials]

The visualization of the complex query in the user interface of the cohort selection panel:
![Glowing Bear complex query][gb_step1]

#### Observation level versus subject level constraints

The Glowing Bear query builder is flexible in the different constraint composition types it supports. In order to fully understand the query that is composed, you should know that every observation is not simply a field in a flat text file where the row indicates the subject and the column variable. Each observation has in fact a number of *dimensions* that provide additional context to this particular value. The most common dimensions are: *patient*, *concept*, *study*, 
*trial visit*, and *start date*.
In the query builder it is both possible to create criteria that will apply to a single observation, and to a subject. For example, ``Subjects with the value 'Male' for the '/Demographics/Gender'`` only makes sense if both ``Male`` and ``/Demographics/Gender`` apply to the same observation. On the other hand, if we are looking for males with an elevated heart rate, you want to look for subjects for which the database has at least two observations,  *(1)* one that says they are male, and *(2)* one that indicates they have an elevated heart rate.
Glowing Bear clearly distinguishes the two. Any criteria within a single query box apply to the **observation level** and anything that combines the query boxes applies to the **subject level**.

#### Inclusion/Exclusion icon

![Glowing Bear icon incl ][included_icon]
![Glowing Bear icon excl ][excluded_icon]

In Glowing Bear you can specify if you want **to exclude a criteria**, switching the included/excluded icon on the right side of the constraint box. Moreover, it is not possible to select anyone you do not have any information on.


## Analysis
![Glowing Bear Analysis image][crosstable_gb2.0]

The Analysis tab now presents you a cross table functionality. You can drag any categorical variables from the Current data selection panel into the vertical and horizontal drop zone to create a cross table with subject counts.

Creating the cross table with any other node type is currently not supported.


## Data Export

#### Select variable of interest
![Glowing Bear variable_selection image][variable_selection_gb2.0]

The Data Export tab allows you to select and visualize in a data table the data that you want to export.
You can select the variables of interest by checking the boxes of the variables views in the Left panel. At this point you can choose either to first visualise and adjust the variables in the data table or export directly the data.

#### Import criteria in the Variable panel

<div class="note"></div>
**Note:** the ``Import criteria`` button can currently only be used 
in specific cases and is not meant for general use.


### Data table

![Glowing Bear datatable image][datatable_gb2.0]

The internal data model for Glowing Bear is not suitable for representation in rows and columns based systems like Excel, without first specifying how to reduce the dimensionality of the longitudinal properties of the data. This step not only allows you to specify the format of the selected data, but you can also directly view it.
You can use the data table by first retrieving all dimensions that apply to your selected data, by pressing the ``Update`` button. These dimensions will all be shown in the *dimension director*. The two lists determine whether dimensions will show in the horizontal or vertical axis of the table. You can move dimensions between the two list and change the order based on what your preferred view on the data is.
In this simple example we have all applicable dimensions in the vertical axis on the left and on the right we have the concept dimension in the horizontal axis.
After making changes to the dimension director, you need to press ``Update`` to retrieve your updated view on the data. This view will also be stored alongside your current data selection so that the export you make is of the same shape.

**Note**: dimensions other than the standard dimensions cannot be moved to the vertical axis currently.


### New and recents exports
![Glowing Bear export image][export_gb2.0]

The Export tab allows you to specify a name. This name has to be unique across the entire application not just for your user account. After choosing a name and pressing ``Create export``, Glowing Bear will create a downloadable *.zip* file with all the data selected during data selection.

Included in the export is the main data file, called data.tsv and an additional file for each dimension that applies to this particular data set. The main data file is shaped in the way you have configured the data table, otherwise the default representation is used. The additional files contain the information known about each *dimension element* in your data set.

Finally, it is now possible to select subjects groups both under the Cohort Selection tab and under the Data Export tab, using the saved cohorts panel on the left side. This creates a more streamlined workflow for experienced users, as they can skip the first page and don’t need to switch tabs when selecting and exporting subjects cohorts. 


# Glossary

Common terms explained:

- **Concept** - A certain variable, e.g. age or heart rate. A concept can be shared by 
  multiple studies and subjects. 
- **Dimension** - Every observation has a standard set of mandatory and optional fields that provide context to this observations value. These fields are the *dimensions* and the values of these dimensions are the dimension elements. Mandatory dimensions are: *patient*, *concept*, *trial visit*, and *study*. Optional dimensions include: *start date*, *end date*, *visit*, *diagnosis id*, *biosource id*, *biomaterial id*, *images*. Note that mandatory and optional dimensions are visualised in different ways.
- **Dimension element** - A specific element within a dimension, for example *Age* in the concept 
  dimension, or *Tumor samples* in the study dimension.
- **Observation** - A single data point, described by dimension elements. 
- **Study** - One of the mandatory dimensions. Every observation in the database is associated with
    a study. The study is the entity on which the permission system is based.


# Friends of Glowing Bear

![transmart components overview][transmart_components]

In a typical deployment you use KeyCloak to manage user accounts and access rights to 
both Glowing Bear and tranSMART. The image above quickly details the role of these three
components. 

## KeyCloak configuration

This documentation will explain for an admin how to create a user, define roles 
needed to grant access, assign roles to grant access, set password policies and look 
at the event logs.

<div class='note'></div>
**Note:** The official KeyCloak documentation is available 
[here](https://www.keycloak.org/documentation.html) and 
for a server admin [here](https://www.keycloak.org/docs/latest/server_admin/index.html). 

### Studies and user access

In tranSMART all data is associated with a study and all user access permissions are associated
with a specific study. A user can be assigned one of two study access levels to a *private study*:

* ``measurement`` - users with this permission are able to view all observations for this study.
* ``counts_with_threshold`` - users can only request subject counts for queries to this study. 
  If this count is below the configured threshold, the Glowing Bear will show ``...`` instead.
* A user without a study role can view neither observations nor counts. 

Alternatively, it is possible for a study to be added to the database as a *public study*, this 
means anyone with access to tranSMART has ``measurement`` access to its data.

A user with the role ``ROLE_ADMIN`` is able to access studies as if they were public. This user 
is also able to perform administrative requests necessary after data 
loading or after the server application restarts. 

### Assigning users to study roles

**This is for KeyCloak administrators only!**

#### Creating a study role

In order to give users access to studies in tranSMART, you should first 
create the role according to the convention that tranSMART requires. A role name should combine
the study identifier and access level, separated by the pipe ``|``
symbol, ie. ``<STUDY_ID>|<ACCESS_LEVEL>``.

To add a role go to *Clients* under the *Configure* option in the menu. 

![KeyCloak Clients][keycloak_clients]

Next click on the client to which the role should be added, in this case the ``transmart-client``. 
In the client configuration window go to the *Roles* tab near the top of the screen. 
Click *Add Role* at the top right of the table displayed on screen.

![KeyCloak Roles][keycloak_roles]

Define the role name according to the convention mentioned above. Here we define the measurement
access level role for the *GSE8581* study by creating the role ``GSE8581|MEASUREMENTS``.
The description is not used outside of the KeyCloak interface and can be left empty.

![KeyCloak Role add][keycloak_add_role]

The new role is now added to the list of possible roles that can be assigned to users.


<div class='note'></div>
**Note:** these roles can be programmatically created by the [Python client](#python-client). 

#### Add role to user

To add a user to a role go to *Users* in the left panel, then select the users you
want to give permission and open the *Role Mappings* tab. In the section **Client Roles**
select ``transmart-client`` and give this user the assigned role.

![KeyCloak Role assign][keycloak_assign_role]

## Python client for programmatic access
{: refdef id="python-client"}

Because Glowing Bear connects to tranSMART exclusively via a publicly available API, it is also 
possible to import data directly into your analytical environment. 

A Python client for the API can be found [here](https://github.com/thehyve/transmart-api-client-py).
Check also the [API tutorial with Python and Jupyter notebook](https://glowingbear.app/tutorials/python-jupyter-notebook/).


[query1_gb2.0]: /images/query1_gb2.0.png
{: .wide-image}

[subject_dimensions_gb2.0]: /images/subject_dimensions_gb2.0.png
{: .wide-image}

[included_icon]: /images/included_icon.png
{: .wide-image}

[excluded_icon]: /images/excluded_icon.png
{: .wide-image}

[crosstable_gb2.0]: /images/crosstable_gb2.0.png
{: .wide-image}

[variable_selection_gb2.0]: /images/variable_selection_gb2.0.png
{: .wide-image}

[datatable_gb2.0]: /images/datatable_gb2.0.png
{: .wide-image}

[export_gb2.0]: /images/export_gb2.0.png
{: .wide-image}

[icons_123]: /docs/images/icons/123.svg
{: .icon}

[icons_abc]: /docs/images/icons/abc.svg
{: .icon}

[icons_study]: /docs/images/icons/study.svg 
{: .icon}

[transmart_components]: /docs/images/transmart171_components.svg
[keycloak_clients]: /docs/images/keycloak_clients.png
[keycloak_roles]: /docs/images/keycloak_roles.png
[keycloak_add_role]: /docs/images/keycloak_add_role.png
[keycloak_assign_role]: /docs/images/keycloak_assign_role.png
