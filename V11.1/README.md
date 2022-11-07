# Downloads:

- [Full setup **TODO**](TODO)

- [**ospsuite** R package **TODO**](TODO)

- [Gene expression database (human)](https://github.com/Open-Systems-Pharmacology/Gene-Expression-Databases/releases/download/v2.0.0/GENEDB_human.expressionDb)

# Release Notes for the Open Systems Pharmacology Software Suite 11 Update 1

## New features

### Mapping observed data sets to simulation outputs in individual simulations

In individual simulations, the newly introduced **Observed Data** tab can be used to map observed data sets to the corresponding simulation outputs. 
This mapping is required for some of the new features described below (e.g. for displaying goodness of fit, etc.).

All observed data sets belonging  to the opened simulation are listed in the mapping table. When adding or removing an observed data set to/from the simulation, the table is updated. Newly added observed data sets are automatically mapped to simulation outputs according to `Organ`, `Compartment` and `Molecule` meta data of the data set and path elements of the outputs. If no matching output can be found, the mapped simulation output is set to **None**. This means that the specified observed data set is not mapped. The user can also clear an output mapping by clicking on the **x** button on the right, which will also set the output to **None**.

![SimulationOutputMappings](https://user-images.githubusercontent.com/25061876/200050125-418222fd-9bca-4bbc-84c3-ef899b3ddc62.png)

For each mapping, the scaling can be defined as **Linear** or **Log** which determines the residual calculation.

**Scaling**

<table>
  <tr>
    <td><b>Linear</b></td>
    <td>Residuals are calculated as: <b>Simulation value - Observed value</b>. This means that the residuals are defined by absolute differences. If the magnitudes of values are different for different parameters, the different magnitudes of residuals should be harmonized by corresponding weights (reciprocal values).</td>
  </tr>
  <tr>
    <td><b>Log</b></td>
    <td>Residuals are calculated as: <b>log(Simulation value) - log(Observed value)</b> = <b>log (Simulation Value / Observed Value)</b>. This means that the ratio of values is considered which is independent of the magnitude of the value.</td>
  </tr>
</table>

To reflect the quality or importance of the observed data set, you can edit the weights of each mapping.

### Predicted vs. Observed Chart in Simulations

For each observed value a point is plotted with observed value as x-Value and corresponding simulated value as y-Value.

![SimulationPredictedVsObservedChart](https://user-images.githubusercontent.com/25061876/200373885-138084ff-974a-4a08-99ab-eb8b4e97d8fd.png)


**Adding Deviation Lines to the chart**

In a *Predicted vs. Observed* plot the user can right click on the chart and add deviation lines:

<p align="center">
  <img width="500" src="https://user-images.githubusercontent.com/37107428/199511249-4a7b78b9-5af0-440f-b699-9ef49f13b143.png">
</p>

This opens a dialog where the user can specify the fold value of the deviation curves.

<p align="center">
  <img width="600" src="https://user-images.githubusercontent.com/25061876/200374364-eb123065-18f3-4fda-96a2-01baffc4998a.png">
</p>

This will create two deviation lines according to the given x-fold value which has to be greater than 1. An x-fold deviation range includes simulated values within x-fold and 1/x-fold of observed values.

![TwoFoldDeviationLine](https://user-images.githubusercontent.com/37107428/199511403-359e559b-36ab-44a2-b061-dc3f1d738118.png)

### Residuals vs. Time Chart in Simulations

This chart is similar to the Time Profile chart, but on the y-axis the (absolute) residuals used in the optimization are plotted. The chart includes scaling, weights and LLOQ usage and the values are dimensionless, so you can assess the actual influence of the observed data.

![Simulation Residuals vs Time Chart.](https://user-images.githubusercontent.com/37107428/199511037-f3035d88-f318-4f01-9ad1-5b190e11093d.png)

At the top of the chart, the total residual error is being displayed.

### PK-Parameters in Population Simulations

Before version v11 Update 1 global pk parameters were only calculated for the selected outputs and were calculated based on the analyzed curve. For example, a mean curve was created and PK Values calculated once from that curve.

With the new release, population simulations contain new features for PK-analyses.

#### Global PK Analysis

Individual simulations prior to v11 update 1 have had a 'global' PK calculation done using venous blood curve.

![individual_global_pk_analysis](https://user-images.githubusercontent.com/261477/199485072-7deb3d45-8dc0-441f-ab86-c6b57df12afa.png)

This type of analysis was not prevsiously available for population simulations. The global pk parameters for population simulation will show in a similar location to the individual simulation, with the caption indicating how the values are aggregated. They are calculated for all individuals in the population and the displayed value is the median of the population values.

![population_global_pk_analysis](https://user-images.githubusercontent.com/261477/199485142-f86b44b0-20a6-44f5-8558-87820f2fcd26.png)

These newly availabe PK-parameters can also be used in the creation of other types of analysis. For example scatter analysis or box plot.

![global_pk_parameters_for_analyses](https://user-images.githubusercontent.com/261477/199485206-9bdf33f4-1d97-4380-9268-b493894ff1cd.png)

#### PK-parameters for range selections

Now when you select a range analysis for your time profile (eg. 5%-95%), Pk-parameters will be calculated for the upper and lower range.

Selecting Mean, and Range 5% to 95% as an example:

![range_selection_for_time_profile](https://user-images.githubusercontent.com/261477/199485266-89d5af3d-0716-4563-bf0a-99b95873414d.png)

Generates PK-parameters for Mean, 5%, and 95% for each compound.

![pk_values_calculated_for_individual_curves_at_range_extremes](https://user-images.githubusercontent.com/261477/199485316-dd237bb1-f8d4-4f00-8df9-1bc9fad5f9d0.png)

#### PK-Parameter Aggregation 
Also apparent from the screenshot is that there are tabs which display Pk-Parameters aggregated in different ways.

In the tab shown above, the tab 'Aggregated PK Values' is calculated from the analyzed curve. For example, the curve at the lower limit of the range 5% is used to calculate PK parameters.

Compared to the tab shown below, 'Individual PK Values' where PK Values are calculated for the individuals and then the median is shown.

![individual_pk_values](https://user-images.githubusercontent.com/261477/199485365-0da788b2-072b-4d6e-a551-e088442d896e.png)

###  Observed Data grouping in PK-Sim simulation figures

When adding data sets to a plot via drag-and-drop of a folder (or multiple folders), all data sets within one folder can be assigned to a single color. This behavior is optional and can be changed by (un)selecting the checkbox "Color group when adding to chart" in the context menu of the “Observed Data” entry of the building blocks explorer. This setting is a central configuration and valid for all subfolders. 

![color_grouping_context_menu](https://user-images.githubusercontent.com/261477/199485722-2ca9ca3f-b631-459e-b2b8-61343de0def9.png)

Alternatively this feature can be toggled on and off from the User Settings, under “Utilities” -> “Options” -> “General” -> “Colors”:

![color_grouping_in_settings](https://user-images.githubusercontent.com/261477/199485758-9bf1b2e8-3c7e-4889-a9db-694d43951d4a.png)

When this option is selected and whole folders are dragged and dropped into a plot, the observed data from the same folders will be assigned the same color. However, when the user selects individual observed data sets instead of folders and drags and drops them on the plot, then each one will be assigned a new color, and they should not be grouped according to the folder they belong to. 

###  Color grouping tab in the Chart Editor 

A new tab called "Curves Color Grouping" has been introduced to the plots with observed data curves. In the tab the user can select one or more metadata, according to which the lines will be grouped and given the same color. Clicking the “Apply Color Grouping” button changes the color of the curves in the chart according to the selection, and then the selection is cleared. The user can then if she wants choose a new selection of metadata and change the coloring once again.

![color_grouping_tab](https://user-images.githubusercontent.com/261477/199485799-18d35175-b8d4-4591-be7f-ef07af677af3.png)

###  Editing options of multiple curves

In the “Curves and Axis Options” Tab of the Chart Editor a new context menu item has been added called “Edit options for selected”. It is only visible when the user has selected at least two rows.

![edit_multiple_curves_context](https://user-images.githubusercontent.com/261477/199485828-64dbb0a3-9afa-4712-8d15-ee03c4a562ea.png)

Selecting this option opens a new dialog that lists the common option of the curves. Initially the values for the options are not set, and if the user lets any of the options to that initial state, that option will not be edited – meaning that the selected curves will retain for that option the value they had before opening the dialog.

![edit_options_dialog](https://user-images.githubusercontent.com/261477/199485858-15ebdfd1-e7ed-4f0b-90e7-ede3e2994e4c.png)

###  Grouping of results in the Chart Editor

In the result charts of Simulations and Parameter Identifications (Time Profile, Predicted vs. Observed, Residuals vs. Time) the curves in the Chart Editor are grouped according to their Category. Additionally the checkbox "Link Data to Simulations has been added". When selected (un)selecting a simulation curve will also unselected the mapped observed data.

![link_data_to_simulations](https://user-images.githubusercontent.com/37107428/199510440-9002d77d-7387-4516-90b3-8f9cbe050ba9.png)

### Running multiple Parameter Identifications in parallel in PK-Sim

It is now enabled to run multiple Parameter Identifications in parallel. After starting at least one PI, the tab “Run & Analyze” should reflect the state of the currently selected PI, instad of being equal for all PI instances as it was till now.

### OSP Platform qualification library and PBPK Models Library
#### PBPK Models library extended
New PBPK models added:
* Felodipine
* Sildenafil

Model building process and model quality of every new PBPK model is documented in the corresponding _model evaluation report_. 
#### New releases of OSP Platform qualification library and PBPK Models Library
**TODO**
As with every new OSP Suite release, ALL platform qualification reports and model evaluation reports have been recreated with the new version of the OSP Suite and the latest version of the [_OSP Qualification Framework_](https://github.com/Open-Systems-Pharmacology/QualificationPlan/releases/latest):
* [**_OSP Qualification Reports library_**](https://github.com/Open-Systems-Pharmacology/OSP-Qualification-Reports) 
* [**_OSP-PBPK-Model-Library_**](https://github.com/Open-Systems-Pharmacology/OSP-PBPK-Model-Library)

### New release of the **ospsuite** R package

* ...

### (Re-)Qualification framework updated
OSP (Re-)Qualification framework is a technical framework to assess the confidence of specific intended use of the OSP platform. This framework allows for an automatic (re)-qualification workflow of the OSP suite. New release of the OSP (Re-)Qualification framework provides some improvements and bugfixes (s. below).

* (Re-)Qualification framework is not part of the OSP Suite setup (is only required for the creation of qualification reports) and must be installed separately. The latest release can be found [here](https://github.com/Open-Systems-Pharmacology/QualificationPlan/releases/latest)
* Full documentation of the (Re-)Qualification framework can be found [here](https://docs.open-systems-pharmacology.org/shared-tools-and-example-workflows/qualification)

## Fixed issues and Improvements

### PK-Sim
* [...](https://github.com/Open-Systems-Pharmacology/...)
* ...

### MoBi
* [...](https://github.com/Open-Systems-Pharmacology/...)
* ...

### PK-Sim and MoBi
* [...](https://github.com/Open-Systems-Pharmacology/...)
* ...

## Notes 
* ...
