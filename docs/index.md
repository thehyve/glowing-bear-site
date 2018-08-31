# User documentation
{: .no_toc}

Welcome to the Glowing Bear user documentation. If you are a new user looking for a short introduction, 
you can visit our **[quickstart guide](/docs/quickstart)**.


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

This shows the result of the users actions during data selection. When opening or refreshing the page
there will be no subjects or observations selected, the counts will be ``0``. While interacting with
the query builder in the right panel, this number changes to `...` to indicate Glowing Bear does not 
know the accurate numbers anymore. 

After successfully selecting data, by going through [Step 1](#data-selection-step-1) and 
[Step 2](#data-selection-step-2) of Data Selection, and pressing the ``Update`` buttons, it will show the 
number of subjects and observations that match the given criteria. Also, the tree nodes that can be 
used for Analysis and Export will be added to this panel.

The ``Clear all`` button in this panel resets the criteria specified in all steps of Data Selection, allowing
you to start over.


## Ontology tree

```
Todo:
- [x] Where does tree come from
- [x] metadata tags
- [x] Study and concept vs concept
- [x] dragging behaviour vs clicking
```

The ontology tree shows a hierachy of data items that are available for your user. 
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
- <span class="icon fa fa-star-o"></span> bookmarks this query, which is useful for sorting. Bookmarked queries
  will also load faster if there is a lot of data in the database.
- <span class="icon fa fa-download"></span> downloads the query to a file, so you could share it with a colleague
- <span class="icon fa fa-arrow-right"></span> restores the state of the query builder with this saved query
- <span class="icon fa fa-times"></span> removes this query from this list, it cannot be retrieved

If you have previously downloaded a query, or received a query file from a colleage, you can use the ``Import`` 
button to add this query to your list of saved queries. A query file is specially formatted and is 
not meant to be created or edited by hand.  

### Query subscription

<div class="note"></div>
**Note**: this feature is not always available.

By subscribing yourself to a query you will receive an email when there are new subjects found for 
the specified criteria. Any time new data is loaded, Glowing Bear will check whether you have access
to any of the new subjects and notify about the changes. 


# Right Panel

The right panel provides the main user functionality to interact with the database:
[Data selection](#data-selection), [Analysis](#analysis), and [Export](#export).

## Data selection

```
Todo:
- [ ] output of this will be in "Current data selection"
```

Most often you would first start here to select create the dataset that you want to use within 
the application.


### Step 1: Select a group of subjects
{: refdef id="data-selection-step-1"}

```
Todo:
- [ ] Import criteria format
- [ ] Searching tree nodes
- [ ] Inclusion count vs Exclusion count
- [ ] Observation level constraints vs patient set constraints.
```


![Glowing Bear Step 1 image][gb_step1]

By dragging nodes from the tree on the left into step 1 of data selection you can select the group
of subjects you are interested in. Dragging tree nodes automatically adds constraints for a concept and/or study, 
e.g. ``Subjects with any value for '/Demographics/Gender'``.

Depending on the data type additional constraints can be specified, e.g. ``Subjects the value 'Male' for '/Demographics/Gender'``.

### Step 2: Select variable of interest
{: refdef id="data-selection-step-2"}

```
Todo:
- [ ] Update button behaviour (first limit tree, then get counts for selected)
- [ ] import criteria button.
```
![Glowing Bear Step 2 image][gb_step2]

After selecting a group of subjects you can select the variables of interest by checking the nodes in the 
show tree. You can update the counts by pressing the *Update* button on the right. That will also 
update the *Current data selection* on the left and allow you to use the selection you've made in the
rest of the application.

### Step 3: Data table

```
Todo:
- [ ] Update button behaviour
- [ ] Row vs. Column dimensions
- [ ] Moving dimensions.
- [ ] What are dimensions?
- [ ] relation to export
```

The internal data model for Glowing Bear is not suitable for representation in rows and columns based 
systems like Excel, without first specifying how to reduce the dimensionality of the 
longitudinal properties of the data.

## Analysis
![Glowing Bear Analysis image][gb_analysis]

```
Todo:
- [ ] Dragging categorical nodes.
```

The Analysis tab now presents you a cross table functionality. You can drag any categorical variables from
the *Current data selection* panel into the vertical and horizontal dropzone to create a cross table with 
subject counts.

## Export
![Glowing Bear Export image][gb_export]

```
Todo:
- [ ] choosing a name.
- [ ] contents of export.
- [ ] export options.
```

The Export tab allows you specify a name that will create a downloadable .zip file with all the data selected
during data selection.

# Glossary

Common terms explained:

- **Concept** - A certain variable, e.g. age or heart rate. A concept can be shared by multiple studies and subjects. 
- **Dimension** - 
- **Observation** - A single data point. 


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
