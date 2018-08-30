# User documentation
{: .no_toc}

Welcome to the Glowing Bear user documentation. If you are a new user looking for a short introduction, 
you can visit our **[quickstart guide](/docs/quickstart)**.


```
General todo:
 - Update images to release version.
```

More detailed information can be found below.

# Table of contents
{: .no_toc}

* TOC
{:toc}
{::options toc_levels="1,2,3" /}


# Left panel
The left panel contains information about the [current data selection](#current-data-selection), 
and  the [available concepts](#ontology) and [queries](#queries) in the database.

## Current data selection

```
Todo:
 - when is dirty what do dots mean.
 - clear button.
```

This shows the result of the users actions during data selection. After successfully selecting data 
it will show the number of subjects and observations that match the given criteria, and the tree nodes
that can be used for Analysis and Export.


## Ontology
```
Todo:
- Where does tree come from
- metadata tags
- Study and concept vs concept
- dragging behaviour vs clicking
```

The tree shows the variables that are available to you. This hierarchy contains studies and concepts
and the number of subjects that have information for them. The nodes in the tree can be dragged into
the right panel to create queries. Currently the following data types are supported:

- ![icons 123][icons_123] numerical
- ![icons abc][icons_abc] categorical
- <span class="icon fa fa-calendar-o"></span> dates
- <span class="icon fa fa-newspaper-o"></span> free text
- ![icons hd][icons_hd] high-dimensional
- ![icons study][icons_study] study

## Queries

```
Todo:
- subscription feature details
- icons explained
- saving / restoring / sharing
- import query
```

Queries you've created previously can be seen and restored from here. This is convenient if you
frequently require information about the same (updated) group of subjects. 

- <span class="icon fa fa-rss"></span> subscription
- <span class="icon fa fa-star-o"></span> star
- <span class="icon fa fa-download"></span> downlaod
- <span class="icon fa fa-arrow-right"></span> apply
- <span class="icon fa fa-times"></span> delete

# Right Panel

The right panel provides the main user functionality to interact with the database:
[Data selection](#data-selection), [Analysis](#analysis), and [Export](#export).

## Data selection

```
Todo:
- output of this will be in "Current data selection"
```

Most often you would first start here to select create the dataset that you want to use within 
the application.

### Step 1: Select a group of subjects

```
Todo:
- Import criteria format
- Searching tree nodes
- Inclusion count vs Exclusion count
- Observation level constraints vs patient set constraints.
```


![Glowing Bear Step 1 image][gb_step1]

By dragging nodes from the tree on the left into step 1 of data selection you can select the group
of subjects you are interested in. Dragging tree nodes automatically adds constraints for a concept and/or study, 
e.g. ``Subjects with any value for '/Demographics/Gender'``.

Depending on the data type additional constraints can be specified, e.g. ``Subjects the value 'Male' for '/Demographics/Gender'``.

### Step 2: Select variable of interest

```
Todo:
- Update button behaviour (first limit tree, then get counts for selected)
- import criteria button.
```

![Glowing Bear Step 2 image][gb_step2]

After selecting a group of subjects you can select the variables of interest by checking the nodes in the 
show tree. You can update the counts by pressing the *Update* button on the right. That will also 
update the *Current data selection* on the left and allow you to use the selection you've made in the
rest of the application.

### Step 3: Data table

```
Todo:
- Update button behaviour
- Row vs. Column dimensions
- Moving dimensions.
- What are dimensions?
- relation to export
```

The internal data model for Glowing Bear is not suitable for representation in rows and columns based 
systems like Excel, without first specifying how to reduce the dimensionality of the 
longitudinal properties of the data.

## Analysis
![Glowing Bear Analysis image][gb_analysis]

```
Todo:
- Dragging categorical nodes.
```

The Analysis tab now presents you a cross table functionality. You can drag any categorical variables from
the *Current data selection* panel into the vertical and horizontal dropzone to create a cross table with 
subject counts.

## Export
![Glowing Bear Export image][gb_export]

```
Todo:
- choosing a name.
- contents of export.
- export options.
```

The Export tab allows you specify a name that will create a downloadable .zip file with all the data selected
during data selection.


# Friends of Glowing Bear

## KeyCloak configuration

```
Todo:
- Mapping studies to access for users.
```

## Python client for programmatic access

```
Todo:
- Link to github.
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
