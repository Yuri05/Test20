# Downloads:

- [Full setup **TODO**](TODO)

- [**ospsuite** R package **TODO**](TODO)

- [Gene expression database (human)](https://github.com/Open-Systems-Pharmacology/Gene-Expression-Databases/releases/download/v2.0.0/GENEDB_human.expressionDb)

# Release Notes for the Open Systems Pharmacology Software Suite 11 Update 1

## New features

### Mapping observed data sets to simulation outputs in individual simulations

In simulations, the newly introduced **Observed Data** tab can be used to map observed data sets to the corresponding simulation outputs. 
This mapping is required for some of the new features described below (e.g. for displaying goodness of fit, etc.).

All observed data sets belonging  to the opened simulation are listed in the mapping table. When adding or removing an observed data set to/from the simulation, the table is updated. Newly added observed data sets are automatically mapped to simulation outputs according to `Organ`, `Compartment` and `Molecule` meta data of the data set and path elements of the outputs. If no matching output can be found, the mapped simulation output is set to **None**. This means that the specified observed data set is not mapped. The user can also clear an output mapping by selecting the **None** entry from the Output dropdown. By clicking the **"x"** on the right side of the grid, the user can delete the observed data from the simulation.

<p align="center">
  <img src="https://user-images.githubusercontent.com/25061876/200050125-418222fd-9bca-4bbc-84c3-ef899b3ddc62.png">
</p>

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

<p align="center">
  <img src="https://user-images.githubusercontent.com/25061876/203576087-fa622cf7-6270-4acb-8067-b3ff5ead29ea.png">
</p>

**Adding Deviation Lines to the chart**

In a *Predicted vs. Observed* plot the user can right click on the chart and add deviation lines:

<p align="center">
  <img width="600" src="https://user-images.githubusercontent.com/25061876/203598210-6c318fc4-407c-4103-a30e-cdc06a9192cd.png">
</p>

This opens a dialog where the user can specify the fold value of the deviation curves.

<p align="center">
  <img width="600" src="https://user-images.githubusercontent.com/25061876/200374364-eb123065-18f3-4fda-96a2-01baffc4998a.png">
</p>

This will create two deviation lines according to the given x-fold value which has to be greater than 1. An x-fold deviation range includes simulated values within x-fold and 1/x-fold of observed values.

<p align="center">
  <img src="https://user-images.githubusercontent.com/25061876/203598414-1f3d19de-cfab-4707-b4f9-18324b4f2a6d.png">
</p>

### Residuals vs. Time Chart in Simulations

This chart is similar to the Time Profile chart, but on the y-axis the (absolute) residuals are plotted. The chart includes scaling and weights.
At the top of the chart, the **total residual error** is displayed.

<p align="center">
  <img src="https://user-images.githubusercontent.com/25061876/203111220-3c543f94-e2a6-4eb9-92b2-741e4960542d.png">
</p>

### PK-Parameters in Population Simulations

Before *version 11 Update 1* pk parameters were only calculated for the selected outputs and were calculated based on the analyzed curve. For example, a mean curve was created and PK Values calculated once from that curve.

With the new release, population simulations contain new features for PK-analyses.

#### Global PK Analysis

Individual simulations prior to v11 update 1 have had a 'global' PK calculation done using venous blood curve.

<p align="center">
  <img src="https://user-images.githubusercontent.com/25061876/203112086-fdf8c291-5f92-4143-a89f-1fdb7bcf8444.png">
</p>

This type of analysis was not previously available for population simulations. The global pk parameters for population simulation will show in a similar location to the individual simulation, with the caption indicating how the values are aggregated. They are calculated for all individuals in the population and the displayed value is the median of the individual values.

<p align="center">
  <img src="https://user-images.githubusercontent.com/25061876/203113506-7be67360-b8eb-42e4-9f7c-4779c0a9720e.png">
</p>

These newly available PK-parameters can also be used in the creation of other types of analysis. For example scatter analysis or box plot.

<p align="center">
  <img src="https://user-images.githubusercontent.com/261477/199485206-9bdf33f4-1d97-4380-9268-b493894ff1cd.png">
</p>

#### PK-parameters for range selections

Now when you select a range analysis for your time profile (e.g. 5%-95%), Pk-parameters will be calculated for the upper and lower range.

Selecting Mean, and Range 5% to 95% as an example:

<p align="center">
  <img src="https://user-images.githubusercontent.com/261477/199485266-89d5af3d-0716-4563-bf0a-99b95873414d.png">
</p>

Generates PK-parameters for Mean, 5%, and 95% for each compound.

<p align="center">
  <img src="https://user-images.githubusercontent.com/261477/199485316-dd237bb1-f8d4-4f00-8df9-1bc9fad5f9d0.png">
</p>

#### PK-Parameter Aggregation 
Also apparent from the screenshot is that there are tabs which display Pk-Parameters aggregated in different ways.

In the tab shown above, 'Aggregated PK Values', PK Values are calculated **from the analyzed curve.** For example, the curve at the lower limit of the range 5% is used to calculate PK parameters.

Compared to the tab shown below, 'Individual PK Values' where PK Values are calculated **for the individuals and then the median is shown.**

<p align="center">
  <img src="https://user-images.githubusercontent.com/261477/199485365-0da788b2-072b-4d6e-a551-e088442d896e.png">
</p>

###  Color grouping tab in the Chart Editor 

A new tab called "Curves Color Grouping" has been introduced to the plots with observed data curves. In the tab the user can select one or more metadata, according to which the observed data sets will be grouped and given the same color. Clicking the “Apply Color Grouping” button changes the color of the observed data sets in the chart according to the selection, and then the selection is cleared. The user can then choose a new selection of metadata and change the coloring once again.

<p align="center">
  <img src="https://user-images.githubusercontent.com/25061876/203570761-f9d8ea29-e3d9-4384-a852-8df81660d4e2.png">
</p>

###  Editing options of multiple curves

In the “Curves and Axis Options” Tab of the Chart Editor a new context menu item has been added called “Edit options for selected”. It is only visible when the user has selected at least two rows.

<p align="center">
  <img src="https://user-images.githubusercontent.com/25061876/203116288-85233c3c-109a-4e84-8a4e-b767d227a583.png">
</p>

Selecting this option opens a new dialog that lists the common options of the curves. Initially the values for the options are not set, and if the user lets any of the options to that initial state, that option will not be edited – meaning that the selected curves will retain for that option the value they had before opening the dialog.

<p align="center">
  <img src="https://user-images.githubusercontent.com/25061876/203571279-377c5e01-3875-4d90-af67-2c7277138916.png">
</p>

###  Grouping of results in the Chart Editor

In the result charts of Simulations and Parameter Identifications (Time Profile, Predicted vs. Observed, Residuals vs. Time) the curves in the Chart Editor are grouped according to their Category. Additionally the checkbox "Link Data to Simulations has been added". When activated, (un)selecting a simulation curve will also unselect the mapped observed data.

<p align="center">
  <img src="https://user-images.githubusercontent.com/37107428/199510440-9002d77d-7387-4516-90b3-8f9cbe050ba9.png">
</p>

### Running multiple Parameter Identifications in parallel in PK-Sim and MoBi

It is now possible to run multiple Parameter Identifications in parallel. After starting at least one PI, the ribbon bar “Run & Analyze” should reflect the state of the currently selected PI, instead of being equal for all PI instances as it was till now.

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
* [Initial concentration overwritten with a value in Protein Expression BB not propagated into simulation](https://github.com/Open-Systems-Pharmacology/PK-Sim/issues/2253)
* [Snapshot including individual with user-defined initial concentrations for protein expression cannot be reloaded](https://github.com/Open-Systems-Pharmacology/PK-Sim/issues/2256)
* [Expression profile building block shows "0" for all initial concentrations](https://github.com/Open-Systems-Pharmacology/PK-Sim/issues/2241)
* [Curve selection view (Define settings and run) - buttons are hidden in 4k, scaling 200%](https://github.com/Open-Systems-Pharmacology/PK-Sim/issues/2252)
* [UI: Parameter disappears when trying to edit another parameter](https://github.com/Open-Systems-Pharmacology/PK-Sim/issues/2285)
* [UI: Parameter disappears during creation of a simulation](https://github.com/Open-Systems-Pharmacology/PK-Sim/issues/2287)
* [UI: Ontogeny data window - x axis missing in 4K, 200% scaling](https://github.com/Open-Systems-Pharmacology/PK-Sim/issues/2274)
* [Add version to splash screen](https://github.com/Open-Systems-Pharmacology/PK-Sim/issues/2263)
* [UI: Creating population - "Stop" button too small](https://github.com/Open-Systems-Pharmacology/PK-Sim/issues/2278)
* [When overwriting initial protein concentration in Expression Profile: Reset button is active in Individual with no effect](https://github.com/Open-Systems-Pharmacology/PK-Sim/issues/2270)
* [Refresh problem with protein initial concentrations when updating individual from building block](https://github.com/Open-Systems-Pharmacology/PK-Sim/issues/2254)
* [OCT1 Influx expression profile populates on apical side of liver rather than basolateral](https://github.com/Open-Systems-Pharmacology/PK-Sim/issues/2302)
* [PK-Parameter normalized not calculated for statistical curves of a population analysis](https://github.com/Open-Systems-Pharmacology/PK-Sim/issues/414)
* [Export time profile analysis change the units](https://github.com/Open-Systems-Pharmacology/PK-Sim/issues/1640)

### MoBi
* [Wrong icon for events tab](https://github.com/Open-Systems-Pharmacology/MoBi/issues/731)
* [Layout problems in MSV-BB](https://github.com/Open-Systems-Pharmacology/MoBi/issues/725)
* [Mobi 11 returned error while trying to create a new PKSIM molecule.](https://github.com/Open-Systems-Pharmacology/MoBi/issues/726)
* [Inconsistent size of buttons in "Rename" window](https://github.com/Open-Systems-Pharmacology/MoBi/issues/728)
* [UI: Passive transports -> "Add molecule" button is too small](https://github.com/Open-Systems-Pharmacology/MoBi/issues/743)
* [UI: "local reference point" is hidden](https://github.com/Open-Systems-Pharmacology/MoBi/issues/741)
* [UI: formula editor - missing "x" in aliases field](https://github.com/Open-Systems-Pharmacology/MoBi/issues/750)
* [UI: Reaction -> Stoichiometry -> Empty column](https://github.com/Open-Systems-Pharmacology/MoBi/issues/742)
* [UI: unnecessary scroll bars in explorers](https://github.com/Open-Systems-Pharmacology/MoBi/issues/739)
* [Parameter added to an inhibition/induction process should be GLOBAL](https://github.com/Open-Systems-Pharmacology/MoBi/issues/769)
* [Comparison does not include container criteria for parameter](https://github.com/Open-Systems-Pharmacology/MoBi/issues/751)
* [UI: text boxes cut-off in parameter menu](https://github.com/Open-Systems-Pharmacology/MoBi/issues/757)
* [NaNs in boolean formulas](https://github.com/Open-Systems-Pharmacology/OSPSuite.SimModel/issues/148)

### PK-Sim and MoBi
* [Chart Editor panel automatically resizes and hides plots after every simulation run](https://github.com/Open-Systems-Pharmacology/MoBi/issues/732)
* [Add "g/l" to "Concentration (mass)"](https://github.com/Open-Systems-Pharmacology/OSPSuite.Dimensions/issues/32)
* [UI: sensitivity analysis - "Update multiple sensitivity parameters" field is not readable.](https://github.com/Open-Systems-Pharmacology/OSPSuite.Core/issues/1689)
* [UI: Parameter Identification feedback](https://github.com/Open-Systems-Pharmacology/OSPSuite.Core/issues/1687)
* [SensitivityAnalysis does not produce any results in certain cases](https://github.com/Open-Systems-Pharmacology/OSPSuite.SimModel/issues/146)
* [Calculate AUC_tEnd and C_tEnd for multiple administration simulations](https://github.com/Open-Systems-Pharmacology/OSPSuite.Core/issues/1693)
* [Show a warning message when number of output points is high](https://github.com/Open-Systems-Pharmacology/OSPSuite.Core/issues/1636)

## Known Issues

### PK-Sim
* [**Predicted vs. Observed** and **Residuals vs. Time** plots in a simulation are not saved to snapshot](https://github.com/Open-Systems-Pharmacology/PK-Sim/issues/2404)
* [**Predicted vs Observed** Plot: it is not possible to plot the data in the different dimensions](https://github.com/Open-Systems-Pharmacology/PK-Sim/issues/2398)
* [**Predicted vs. Observed** and **Residuals vs. Time** plots: some graphical settings are lost if the plot was cloned](https://github.com/Open-Systems-Pharmacology/PK-Sim/issues/2394)

## Notes 
* **TODO final report location** Validation of the CKD (Chronic Kidney Disease) population was completed and the "experimental" flag was removed.
The preliminary validation report can be viewed [here](https://github.com/Open-Systems-Pharmacology/Qualification-CKD/blob/main/Qualification/report/report.md). 
