# Quick start Guide

The initial page of Glowing Bear is a screen split into a left and right panel.
The left panel contains information about the 
[current data selection](#left-panel-current-data-selection), and the 
[available ontology](#left-panel-ontology) and [queries](#left-panel-queries) in the database.

The right panel provides the main user functionality to interact with the database:
[Data selection](#right-panel-data-selection), 
[Analysis](#right-panel-analysis), and [Export](#right-panel-export).

![Glowing Bear overview image][gb_overview]

## Left panel: Current data selection
This shows the result of the users actions during data selection. After successfully selecting data 
it will show the number of subjects and observations that match the given criteria, and the tree 
nodes that can be used for Analysis and Export.

## Left panel: Ontology
The tree shows the variables that are available to you. This hierarchy contains studies and 
concepts, with the number of subjects reported in parenthesis. 
The nodes in the tree can be dragged into the right panel to create queries. 
Currently the following data types are supported:

- ![icons 123][icons_123] numerical
- ![icons abc][icons_abc] categorical
- <span class="icon fa fa-calendar-o"></span> dates
- <span class="icon fa fa-newspaper-o"></span> free text
- ![icons hd][icons_hd] high-dimensional
- ![icons study][icons_study] study

## Left panel: Queries
Queries you've created previously can be seen and restored from here. This is convenient if you
frequently require information about the same (updated) group of subjects. 

## Right panel: Data selection
Most often you would first start here to select create the data set that you want to use within 
the application.

### Step 1: Select a group of subjects
![Glowing Bear Step 1 image][gb_step1]

By dragging nodes from the tree on the left into step 1 of data selection you can select the group
of subjects you are interested in. Dragging tree nodes automatically adds constraints for a concept 
and/or study, e.g. ``Subjects with any value for '/Demographics/Gender'``.

Depending on the data type additional constraints can be specified, e.g. ``Subjects the value 
'Male' for '/Demographics/Gender'``.

### Step 2: Select variable of interest
![Glowing Bear Step 2 image][gb_step2]

After selecting a group of subjects you can select the variables of interest by checking the nodes 
in the show tree. You can update the counts by pressing the *Update* button on the right. That will 
also update the *Current data selection* on the left and allow you to use the selection you've made
in the rest of the application.

### Step 3: Data table
The internal data model for Glowing Bear is not suitable for representation in rows and columns 
based systems like Excel, without first specifying how to reduce the dimensionality of the 
longitudinal properties of the data.

## Right panel: Analysis
![Glowing Bear Analysis image][gb_analysis]

The Analysis tab now presents you a cross table functionality. You can drag any categorical 
variables from the *Current data selection* panel into the vertical and horizontal drop zone 
to create a cross table with subject counts.

## Right panel: Export
![Glowing Bear Export image][gb_export]

The Export tab allows you specify a name that will create a downloadable .zip file with all the 
data selected during data selection.


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
