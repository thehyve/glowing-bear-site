# Quick start Guide

The initial page of Glowing Bear is a screen split into a left and right panel.
The left panel contains information about
[Ontology](#left-panel-ontology) related to the available data, list of saved [Cohorts](#left-panel-cohorts) and list of [Variables](#left-panel-variables) of the selected cohort.

The right panel provides the main user functionality to interact with the database:
[Cohort selection](#right-panel-cohort-selection), 
[Analysis](#right-panel-analysis), and [Data Export](#right-panel-data-export).

![Glowing Bear overview image][homescreen_gb2.0]

## Left panel: Ontology
The tree shows the variables that are available to you. This hierarchy contains studies and concepts, with the number of subjects reported in parenthesis. The nodes in the tree can be dragged into the right panel to create queries. Currently the following data types are supported:

- ![icons 123][icons_123] numerical
- ![icons abc][icons_abc] categorical
- <span class="icon fa fa-calendar-o"></span> dates
- <span class="icon fa fa-newspaper-o"></span> free text
- ![icons study][icons_study] study

## Left panel: Cohorts
List of cohorts you’ve created previously can be seen and restored from here. This is convenient if you frequently require information about the same (updated) group of subjects.
The first cohort in the list is named *currently editing*. This shows the result of the user actions during data selection in the right window. 
After successfully selecting cohorts, on the top left of the Cohort panel the number of subjects that match the given criteria is shown.


## Left panel: Variables
List of variables related to the cohort selected. When a cohort is chosen in the Cohort panel, the variables associated to the selected subjects are shown in two views:

 - The <strong>Tree view</strong> reflects the hierarchical structure of the data displayed in the Ontology panel.
 - The <strong>Catergory view</strong> represents the variables in a plein list, grouped by specific data types: Categorical, Numeric, Date, Text. 

If multiple cohorts are selected, the list of the overlapping variables across the cohorts is shown.

## Right panel: Cohort selection
Often you would first start here to create a data set that you want to use within the application.

### Select a group of subjects
![Glowing Bear Step 1 image][query1_gb2.0]

You can select the group of subjects you are interested in three ways: by dragging nodes from the tree on the left, into *add criteria* box, typing into that box, or selecting them from a drop-down menu. Dragging tree nodes automatically adds constraints for a concept and/or study, e.g ``Subjects with any value for '/Demographics/Gender'``.

Depending on the data type additional constraints can be specified, e.g. ``Subjects the value 
'Male' for '/Demographics/Gender'``.


## Right panel: Analysis
![Glowing Bear Analysis image][crosstable_gb2.0]

The Analysis tab presents a cross table functionality. You can drag any categorical 
variables from the *Variable* panel into the vertical and horizontal drop zone 
to create a cross table with subject counts.

## Right panel: Data Export
![Glowing Bear variable_selection image][variable_selection_gb2.0]
The Data Export tab allows you to select and if needed visualize in a data table, the data that you want to export.
You can select the variables of interest by checking the boxes of the variables views in the Left panel. 

### Data table
![Glowing Bear datatable image][datatable_gb2.0]
Data table displays the data selected for the export. The internal data model of Glowing Bear is not suitable for representation in rows and columns based systems like Excel, without first specifying how to reduce the dimensionality of the longitudinal properties of the data.

### New and Recent exports
![Glowing Bear export image][export_gb2.0]

The Export tab allows you specify a name that will create a downloadable .zip file with all the data selected during data selection.
In the Recent export tab you can view, download or archive the list of exports that you have made.


[homescreen_gb2.0]: /images/homescreen_gb2.0.png
{: .wide-image}

[query1_gb2.0]: /images/query1_gb2.0.png
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
