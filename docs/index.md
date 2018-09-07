# User documentation
{: .no_toc}

Welcome to the Glowing Bear user documentation. If you are a new user looking for a short 
introduction, you can visit our **[quickstart guide](/docs/quickstart)**.


```
General todo:
 - [ ] Update images to release version.
```

More detailed information can be found below.

# Table of contents
{: .no_toc}

* TOC
{:toc}
{::options toc_levels="1,2" /}


# Left panel
The left panel contains information about the [current data selection](#current-data-selection), 
and  the [available concepts](#ontology) and [queries](#queries) in the database.

## Current data selection

```
Todo:
 - [x] when is dirty what do dots mean.
 - [x] clear button.
```

This shows the result of the users actions during data selection. When opening or refreshing the 
page there will be no subjects or observations selected, the counts will be ``0``. While interacting 
with the query builder in the right panel, this number changes to `...` to indicate Glowing Bear
does not know the accurate numbers anymore. 

After successfully selecting data, by going through *[Step 1](#data-selection-step-1)* and 
*[Step 2](#data-selection-step-2)* of Data Selection, and pressing the ``Update`` buttons, it will 
show the number of subjects and observations that match the given criteria. Also, the tree nodes 
that can be used for Analysis and Export will be added to this panel.

The ``Clear all`` button in this panel resets the criteria specified in all steps of Data Selection,
allowing you to start over.


## Ontology tree

```
Todo:
- [x] Where does tree come from
- [x] metadata tags
- [x] Study and concept vs concept
- [x] dragging behavior vs clicking
```

The ontology tree shows a hierarchy of data items that are available for your user. 
It contains concepts and studies and the number of subjects that have information 
for them. This tree is created when the data set is loaded into the database and the 
data items are *not necessarily* limited to existing terminologies.

Each node in the tree is either a folder, or one of the node types listed below. The
number of subjects that have at least one observation for a specific variable is 
appended to the label. The nodes in the tree can be dragged into the right panel
to compose criteria that define the group of subjects. Dragging one of the nodes 
automatically adds a criterion to the builder for the **concept and/or study** 
that is associated with this tree node. The concept criteria can be further 
specified to more precisely compose your queries. 

- ![icons 123][icons_123] numerical: *allows setting a minimum and maximum value*
- ![icons abc][icons_abc] categorical: *provides a list of options from which you can select*
- <span class="icon fa fa-calendar-o"></span> dates: *can set minimum and maximum dates*
- <span class="icon fa fa-newspaper-o"></span> free text: *no further options*
- ![icons hd][icons_hd] high-dimensional: *no further options*
- ![icons study][icons_study] study: *no further options*

More details on subject selection can be found [further down](#data-selection-step-1).

For some nodes, additional information is available when hovering over the label. This is 
indicated by an ⓘ information icon.

The search box in this windows allows you to search the tree. Nodes that match the search string
will be highlighted and opened for convenient access. Note that if there are too many search 
results, not all nodes will be opened. 


## Queries

```
Todo:
- [x] subscription feature details
- [x] icons explained
- [x] saving / restoring / sharing
- [x] import query
```

Queries you've created previously can be seen and restored from here. This is convenient if you
frequently require information about the same (updated) group of subjects. 

- <span class="icon fa fa-rss"></span> subscribes you to this query: see [below](#query-subscription)
- <span class="icon fa fa-star-o"></span> bookmarks this query, which is useful for sorting. 
  Bookmarked queries will also load faster if there is a lot of data in the database.
- <span class="icon fa fa-download"></span> downloads the query to a file, so you could share it 
  with a colleague
- <span class="icon fa fa-arrow-right"></span> restores the state of the query builder with this 
  saved query
- <span class="icon fa fa-times"></span> removes this query from this list, it cannot be retrieved

If you have previously downloaded a query, or received a query file from a colleague, you can use 
the ``Import`` button to add this query to your list of saved queries. A query file is specially 
formatted and is not meant to be created or edited by hand.  

### Query subscription

<div class="note"></div>
**Note:** this feature is not always available.

By subscribing yourself to a query you will receive an email when there are new subjects found for 
the specified criteria. Any time new data is loaded, Glowing Bear will check whether you have access
to any of the new subjects and notify about the changes. 


# Right Panel

The right panel provides the main user functionality to interact with the database:
[Data selection](#data-selection), [Analysis](#analysis), and [Export](#export).

## Data selection

```
Todo:
- [x] output of this will be in "Current data selection"
```

Once you are familiar with Glowing Bear you would start here to select criteria to create the 
dataset that you want to use within the application. Within the Data Selection panel various subject
counts are shown to you. It is important to know that these counts reflect that particular part
of the data selection. After completing these steps and requesting updated counts, the correct
counts will be shown in the [current data selection](#current-data-selection) panel.


### Step 1: Select a group of subjects
{: refdef id="data-selection-step-1"}

```
Todo:
- [x] Import criteria format
- [x] Searching tree nodes
- [x] Inclusion count vs Exclusion count
- [ ] Observation level constraints vs subject set constraints: **Add image**.
```

![Glowing Bear Step 1 image][gb_step1]

By dragging nodes from the tree on the left into *Step 1* of data selection you can select the group
of subjects you are interested in. Dragging tree nodes automatically adds constraints for a concept 
and/or study, e.g. ``Subjects with any value for '/Demographics/Gender'``. Alternatively, you can 
click on the empty *add criterion*-box and search the list of possible constraints:

- Study: all subjects included in the study with the specified identifier.
- Concept: all subjects with a value for the specified concept. Depending on the data 
  type additional constraints can be specified, 
  e.g. ``Subjects the value 'Male' for '/Demographics/Gender'``.
- Group: create a new ``and/or`` group to compose more complex queries.
- Pedigree: include all subjects that have the given relationship with at least one of the subjects
  in the specified subject set. 


#### Observation level versus subject level constraints

The Glowing Bear query builder is flexible in the different constraint composition types it 
supports. In order to fully understand the query that is composed, you should know that every 
observation is not simply a field in a flat text file where the row indicates the subject and the
column the variable. Each observation has in fact a number of *dimensions* that provide additional
context to this particular value. The most common dimensions are: *patient*, *concept*, *study*, 
*trial visit*, and *start date*. 

In the query builder it is both possible create criteria that will apply to a single 
observation, and those that apply to a subject. For example, 
``Subjects with the value 'Male' for the '/Demographics/Gender'`` only makes sense if 
both ``Male`` and ``/Demographics/Gender`` apply to the same observation. On the other hand, if we
are looking for males with an elevated heart rate, you want to look for subjects for which the 
database has at least two observations, *(1)* one that says they are male, and *(2)* one that
indicates they have an elevated heart rate.

Glowing Bear clearly distinguishes the two. Any criteria within a single query box apply to the 
**observation level** and anything that combines the query boxes applies to the **subject level**.

#### Inclusion and Exclusion
In Glowing Bear it is not possible to select anyone you do not have any information on. Instead, you
can specify not only **Inclusion** criteria, but also **Exclusion** criteria. This allows you to 
revert inclusion based on any criteria.

Although both function mostly the same. One difference is in the counts that are shown. The 
included subject count represents the total number of subjects selected from the database, 
where the excluded subject count only represents subjects that were initially included.  

<div class="note"></div>
**Note:** adding no criteria in **Inclusion** criteria selects everyone in the database.

#### Import subject list

Example of a file ``'subject_list.txt'`` that can be used to select these 8 subjects by uploading
it into *Step 1* of the query builder. The file is required to contain 1 identifier per row and 
its name should end with a ``.txt`` file extension. Glowing Bear will try to select all subjects, 
but will ignore subjects it cannot find.
```
NSG512
NSG518
NSG519
PAF507
PAF509
PNS004
PNS016
PNS023
```

### Step 2: Select variable of interest
{: refdef id="data-selection-step-2"}

```
Todo:
- [x] Update button behavior (first limit tree, then get counts for selected)
- [x] import criteria button.
```
![Glowing Bear Step 2 image][gb_step2]

After selecting a group of subjects in *Step 1* you can select the variables of interest by 
checking the nodes in the show tree. You can update the counts by pressing the *Update* button on
the right. That will also update the *Current data selection* on the left and allow you to use the 
selection you've made in the rest of the application.

The ``Update`` button has two purposes in this panel. By pressing it a first time you can
limit the size of the tree, by removing any variables that do no have any information about
your selected group of subjects. After making a selection, the button can be used to get the
actual number of selected observations and subjects. The number of selected subjects might change
during *Step 2*, if the variables you select do not have information on all subjects you have 
selected in *Step 1*.


#### Import criteria

<div class="note"></div>
**Note:** the ``Import criteria`` button can currently only be used 
in specific cases and is not meant for general use.


### Step 3: Data table

```
Todo:
- [x] Update button behavior
- [x] Row vs. Column dimensions
- [x] Moving dimensions.
- [x] What are dimensions?
- [x] relation to export
- [ ] add simple image with two scenarios
```

The internal data model for Glowing Bear is not suitable for representation in 
rows and columns based systems like Excel, without first specifying how to 
reduce the dimensionality of the longitudinal properties of the data. This step 
not only allows you to specify the format of the selected data, but you can also 
directly view it.

You can use the data table by first retrieving all *dimensions* that apply to your selected
data, by pressing the ``Update`` button. These dimensions will all be shown in the 
*dimension director*. The two lists determine whether dimensions will show in the horizontal or 
vertical axis of the table. You can move dimensions between the two list and change the order 
based on what your preferred view on the data is. 

<div class="note"></div>
Add image here.

In this simple example we have all applicable dimensions in the vertical axis on the left and
in the right we have the *concept* dimension in the horizontal axis.

After making changes to the dimension director, you need to press ``Update`` to retrieve your 
updated view on the data. This view will also be stored along side your current data selection
so that the export you make is of same shape.

<div class="note"></div>
**Note:** dimensions other than the standard dimensions cannot 
be moved to the vertical axis currently.

## Analysis
![Glowing Bear Analysis image][gb_analysis]

```
Todo:
- [x] Dragging categorical nodes.
```

The Analysis tab now presents you a cross table functionality. You can drag any categorical 
variables from the *Current data selection* panel into the vertical and horizontal drop zone 
to create a cross table with subject counts.

Creating the cross table with any other node type is currently not supported.

## Export
![Glowing Bear Export image][gb_export]

```
Todo:
- [x] choosing a name.
- [x] contents of export.
- [X] export options.
```

The Export tab allows you specify a name. This name has to be unique across the entire application
not just for your user account. After choosing a name and pressing  ``Create export``, Glowing Bear
will create a downloadable *.zip* file with all the data selected during data selection.

Included in the export is the main data file, called *data.tsv* and an additional file for 
each *dimension* that applies to this particular data set. The main data file is shaped in 
the way you have configured the data table during *Step 3* of data selection, otherwise the 
default representation is used. The additional files contain the information known about 
each *dimension element* in yourdata set.


# Glossary

Common terms explained:

- **Concept** - A certain variable, e.g. age or heart rate. A concept can be shared by 
  multiple studies and subjects. 
- **Dimension** - Every observation has a standard set of mandatory and optional fields that provide
  context to this observations value. These fields are the *dimensions* and the values of these
  dimensions are the *dimension elements*. Mandatory dimensions are: *patient*, *concept*,
  *trial visit*, and *study*. Optional dimensions include: *start date*, *end date*, and *visit*.
- **Dimension element** - A specific element within a dimension, for example *Age* in the concept 
  dimension, or *GSE8581* in the study dimension.
- **Observation** - A single data point, described by dimension elements. 
- **Study** - One of the mandatory dimensions. Every observation in the database is associated with
    a study. The study is the entity on which the permission system is based.


# Friends of Glowing Bear

## KeyCloak configuration

```
Todo:
- [ ] Mapping studies to access for users.
```

## Python client for programmatic access

```
Todo:
- [ ] Link to github.
```

[gb_overview]: /docs/images/gb_overview.png
{: .wide-image}

[gb_step1]: /docs/images/gb_step1.png
{: .wide-image}

[gb_step2]: /docs/images/gb_step2.png
{: .wide-image}

[gb_export]: /docs/images/gb_export.png
{: .wide-image}

[gb_analysis]: /docs/images/gb_analysis.png
{: .wide-image}

[icons_123]: /docs/images/icons/123.svg
{: .icon}

[icons_abc]: /docs/images/icons/abc.svg
{: .icon}

[icons_hd]: /docs/images/icons/hd.svg
{: .icon}

[icons_study]: /docs/images/icons/study.svg 
{: .icon}
