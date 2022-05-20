# Downloads:

- [Full setup **TODO**](TODO)

- [**ospsuite** R package](https://github.com/Open-Systems-Pharmacology/OSPSuite-R/releases/tag/v11.0.123)

- [Gene expression database (human)](https://github.com/Open-Systems-Pharmacology/Gene-Expression-Databases/releases/download/v2.0.0/GENEDB_human.expressionDb)

# Release Notes for the Open Systems Pharmacology Software Suite 11

## New features

### Expression Profile as standalone building block
Until PK-Sim version 10, expression profiles could only be created _within an individual or a population_.
Starting with the version 11, expression profiles can be created independently (like all other building blocks) and thus can be **reused** in different individuals/populations.
<p align="center">
<img src="https://881660647-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2FewOAYfFFhObyan6wZQs0%2Fuploads%2Fgit-blob-969bf4fe9c3d8a2534a34cb1a5a4864584c604c6%2FCreateExpressionProfile.png?alt=media">
<img src="https://user-images.githubusercontent.com/25061876/162777774-ea5c00c7-7c9f-42a5-b411-8d81be0e3ec0.png">
</p>

For the details s. the [documentation](https://docs.open-systems-pharmacology.org/working-with-pk-sim/pk-sim-documentation/pk-sim-expression-profile)

### Building block templates can be downloaded directly from the OSP GitHub site
<p align="center">
<img src="https://user-images.githubusercontent.com/25061876/162787879-a4ef5caa-fb0e-495c-b85c-53b04a054314.png">
</p>

### OSP Platform qualification library and PBPK Models Library
#### PBPK Models library extended
New PBPK models added:
* Ethinylestradiol
* Mexiletine
* Moclobemide
* Omeprazole
* S-Mephenytoin
* Tizanidine

#### OSP Qualification reports library extended
New Qualification reports added:
* **CYP1A2 DDI** <br>
This qualification report evaluates the developed PBPK drug-drug interactions (DDI) models network for the ability to perform simulations with the intended purpose to predict cytochrome P450 1A2 (**CYPA12**)-mediated DDI.
* **CYP2C19 DDI** <br>
This qualification report evaluates the developed PBPK drug-drug interactions (DDI) models network for the ability to perform simulations with the intended purpose to predict cytochrome P450 2C19 (**CYP2C19**)-mediated DDI.

Model building process and model quality of every new PBPK model is documented in the corresponding _model evaluation report_. 
#### New releases of OSP Platform qualification library and PBPK Models Library
As with every new OSP Suite release, ALL platform qualification reports and model evaluation reports have been recreated with the new version of the OSP Suite and the latest version of the [_OSP Qualification Framework_](https://github.com/Open-Systems-Pharmacology/QualificationPlan/releases/latest):
* [**_OSP Qualification Reports library_**](https://github.com/Open-Systems-Pharmacology/OSP-Qualification-Reports) 
* [**_OSP-PBPK-Model-Library_**](https://github.com/Open-Systems-Pharmacology/OSP-PBPK-Model-Library)

### [Experimental!] Creating individuals and populations with CKD (Chronic Kidney Disease)

Already in version 10 of the software it was possible to use predefined CKD templates (based on the publication [Malik PRV, Yeung CHT, Advani U, Dije S, Edginton AN. A Physiological Approach to Pharmacokinetics in Chronic Kidney Disease. J Clin Pharmacol 2020. 60 Suppl 1: S52-S62. doi: 10.1002/jcph.1713](https://accp1.onlinelibrary.wiley.com/doi/full/10.1002/jcph.1713)).

With version 11, CKD individuals and populations can now be created dynamically.
When creating an individual, a new option **"Disease State"** is provided, which allows a selection between _Healthy_ and diseased individuals.

<p align="center">
<img width="800" src="https://user-images.githubusercontent.com/25061876/162768013-1c1b7ab9-e980-4d67-ba3c-abbd36630bdb.png">
</p>

For the details s. the [documentation **TODO Update link after docu V11 is merged**](https://docs.open-systems-pharmacology.org/v/v11/working-with-pk-sim/pk-sim-documentation/pk-sim-creating-individuals#disease-state) and the original publication by Malik et al.

### [Experimental!] New preclinical species
Two new preclinical species were added: **Cat** and **Cattle**.
The validation of the new species is not fully finalized yet, so both species are provided as an _experimental_ version.
_Cattle_ models can be used with IV applications only.

### Extension of Container Criteria in MoBi
Container Criteria can be concatenated now not only by AND but also by OR operator
This extension is partucularly used for the newly introduced **Container Criteria of local molecule parameters**
<p align="center">
<img src="https://user-images.githubusercontent.com/25061876/162804251-845290d2-0ac8-4a71-b62f-5acabb87345d.png">
<img src="https://user-images.githubusercontent.com/25061876/162804399-3952afb9-d81f-477a-93de-3f4c91b7fee8.png">
</p>

### Color group observed data when drag and dropping folders to charts
When adding data sets via drag-and-drop of a folder (or multiple folders), all data sets within one folder can be assigned to a single color. This behavior is optional and can be changed by a setting integrated into the context menu of the “Observed Data” entry of the building blocks explorer. This setting is valid for all subfolders.

![grafik](https://user-images.githubusercontent.com/25061876/162808473-41bfb4e1-27ba-49cc-8868-d445e190c8f8.png)


Alternatively this feature can be toggled on and off from the User Settings:
* PK-Sim: under “Utilities” -> “Options” -> “General” -> “Colors”
![grafik](https://user-images.githubusercontent.com/25061876/162808820-fdc9519f-63b6-4569-8e33-6f99e47ba055.png)
* MoBi:  under “Utilities” -> “Options” -> “Chart Options”
![grafik](https://user-images.githubusercontent.com/25061876/162809088-98352e02-64a9-4387-a854-66ec0f3bc197.png)

Also, in case the user selects individual observed data sets instead of folders and drags and drops them on the plot, then each one should be assigned a new color, and they should not be grouped according to the folder they belong to. 

### High Screen Resolution Support
Users reported some issues with the layout of PK-Sim or MoBi when using custom font scaling on 4k monitors (or screen with high resolutions). Some UI elements were hidden, some icons were blurry, some text hard to read etc. The version 11 of PK-Sim and MoBi should address these issues and the tools should now behave as expected, even when using custom font scaling. Give it a try and let us know.

### New release of the **ospsuite** R package

* Many Fixed issues and Improvements (s. the [**ospsuite** R package news page](https://www.open-systems-pharmacology.org/OSPSuite-R/news/index.html) and the [**ospsuite** R package release page](https://github.com/Open-Systems-Pharmacology/OSPSuite-R/releases/tag/v11.0.123) for details)
* Major new features:
  * Adds new `DataCombined` class that combines observed data (`DataSet`) and
  simulated data (`SimulationResults`) into a single object. Especially
  important is the `$toDataFrame()` method of this object that returns a data
  frame containing combined data from observed and simulated data, which can be
  further used for visualizations or other analysis.

  * Adds new visualization functions:

    - `plotIndividualTimeProfile()` and `plotPopulationTimeProfile()` to create 
      time-profile plots.

  * Adds a new class `DefaultPlotConfiguration` to provide plot configurations for 
  plotting functions.

  * Adds `simulationResultsToDataFrame()` function to convert `SimulationResults`
  objects into a data frame.

  * All `*ToDataFrame()` functions also get `*ToTibble()` variants to extract a
  tibble data frame instead of a classical data frame.

S. [documentation of the ospsuite R package](https://www.open-systems-pharmacology.org/OSPSuite-R/) for detailed description and usage examples.

### (Re-)Qualification framework updated
OSP (Re-)Qualification framework is a technical framework to assess the confidence of specific intended use of the OSP platform. This framework allows for an automatic (re)-qualification workflow of the OSP suite. New release of the OSP (Re-)Qualification framework provides some improvements and bugfixes (s. below).

* (Re-)Qualification framework is not part of the OSP Suite setup (is only required for the creation of qualification reports) and must be installed separately. The latest release can be found [here](https://github.com/Open-Systems-Pharmacology/QualificationPlan/releases/latest)
* Full documentation of the (Re-)Qualification framework can be found [here](https://docs.open-systems-pharmacology.org/shared-tools-and-example-workflows/qualification)

### Windows 11 support
Windows 11 is now officially supported by the OSP Suite.

## Fixed issues and Improvements

### PK-Sim
* [Add "Urine compartment emptying" as an event template to PK-Sim](https://github.com/Open-Systems-Pharmacology/PK-Sim/issues/1933)
* [Running multiple parameter identifications in parallel](https://github.com/Open-Systems-Pharmacology/PK-Sim/issues/1901)
* [Listing individual and population should order first by type](https://github.com/Open-Systems-Pharmacology/PK-Sim/issues/2164)
* [Active transports Lumen<=> Mucosa: too many transports are created in case the transporter direction (Influx/Efflux/...) is not the same in all GI segments.](https://github.com/Open-Systems-Pharmacology/PK-Sim/issues/1930)
* [Active influx transports Lumen=>Mucosa with the Hill kinetics: cannot create simulations](https://github.com/Open-Systems-Pharmacology/PK-Sim/issues/1929)
* [Load from Template: multiselect+Delete](https://github.com/Open-Systems-Pharmacology/PK-Sim/issues/834)
* [Symbol Change in Legend for Population Simulation](https://github.com/Open-Systems-Pharmacology/PK-Sim/issues/1522)
* [Clone simulation: Plot title and plot description not copied](https://github.com/Open-Systems-Pharmacology/OSPSuite.Core/issues/1568)
* [Liver zonation: wrong observer formula](https://github.com/Open-Systems-Pharmacology/PK-Sim/issues/2133)
* [Make parameter "Fraction of blood for sampling" visible](https://github.com/Open-Systems-Pharmacology/PK-Sim/issues/1976)
* [AUCR and CmaxR not calculated if formulation with more than 1 Particle bin used](https://github.com/Open-Systems-Pharmacology/PK-Sim/issues/1755)
* [Edit Database Query does not display "old" values correctly](https://github.com/Open-Systems-Pharmacology/PK-Sim/issues/2055)
* [Load project from snapshot: new option "Run simulations"](https://github.com/Open-Systems-Pharmacology/PK-Sim/issues/2158)
* [Display "OK" and "Cancel" buttons in the value origin window](https://github.com/Open-Systems-Pharmacology/OSPSuite.Core/issues/1484)

### MoBi
* [Running multiple parameter identifications in parallel](https://github.com/Open-Systems-Pharmacology/MoBi/issues/639)
* [Cannot import molecular weight if it does not match the molecule](https://github.com/Open-Systems-Pharmacology/MoBi/issues/667)
* [Import parameter values from Excel: error if a column without name is present](https://github.com/Open-Systems-Pharmacology/MoBi/issues/679)
* [Import parameter values from Excel: error when a cell contains a formula](https://github.com/Open-Systems-Pharmacology/MoBi/issues/678)
* [Dimension 'Flow per body surface area' not available in DimensionFactory](https://github.com/Open-Systems-Pharmacology/MoBi/issues/694)
* [Deleting a molecule node connected to a reaction does not remove the molecul from reaction](https://github.com/Open-Systems-Pharmacology/MoBi/issues/690)
* [New path keyword: ALL_FLOATING_MOLECULES TODO link]()

### PK-Sim and MoBi
* [Adding different sheets requires same column names](https://github.com/Open-Systems-Pharmacology/PK-Sim/issues/2069)
* [Importer: MetaData with empty values should not be stored](https://github.com/Open-Systems-Pharmacology/OSPSuite.Core/issues/1429)
* [Importer: Error when measurement column has missing entries](https://github.com/Open-Systems-Pharmacology/OSPSuite.Core/issues/1192)
* [Importer: "Guess" unit each time a column for time or measurement is selected](https://github.com/Open-Systems-Pharmacology/PK-Sim/issues/2075)
* [Importer: setting molweight of imported observed data not possible](https://github.com/Open-Systems-Pharmacology/PK-Sim/issues/2073)
* [Import Observed Data: "Import unit from a column" is case sensitive](https://github.com/Open-Systems-Pharmacology/PK-Sim/issues/1931)
* [Multiselect for color settings in chart editor](https://github.com/Open-Systems-Pharmacology/PK-Sim/issues/553)
* [Data import tool naming pattern is not working as expected](https://github.com/Open-Systems-Pharmacology/OSPSuite.Core/issues/1380)
* [Importer: loading configuration with molecule not mapped](https://github.com/Open-Systems-Pharmacology/OSPSuite.Core/issues/1384)
* [Importer: "Molecule" MetaData saved to configuration even when not mapped](https://github.com/Open-Systems-Pharmacology/OSPSuite.Core/issues/1387)
* [Data import misaligns values/column header](https://github.com/Open-Systems-Pharmacology/OSPSuite.Core/issues/1404)
* [Data import: group data is not used](https://github.com/Open-Systems-Pharmacology/OSPSuite.Core/issues/1432)
* [Data import cannot handle correctly arithmetic error of a fraction given as percentage](https://github.com/Open-Systems-Pharmacology/OSPSuite.Core/issues/1405)
* [Importer: Handling of "invalid" files](https://github.com/Open-Systems-Pharmacology/OSPSuite.Core/issues/1409)
* [Importer: Cannot select " " as unit for "Fraction"](https://github.com/Open-Systems-Pharmacology/OSPSuite.Core/issues/1500)
* [Importer should perform better when loading several datasets](https://github.com/Open-Systems-Pharmacology/OSPSuite.Core/issues/1492)
* [Importer: "Reset mapping based on current sheet" should be a button.](https://github.com/Open-Systems-Pharmacology/OSPSuite.Core/issues/1513)

## Notes 
* The limitation of max. 5000 output time points per simulation was dropped. Now **arbitrary** number of output time points per simulation can be defined. This does not have influence on the simulation time but might have impact e.g. on the memory consumption or on the plotting time in charts. 
Thus if you have old projects with very high output resolution - please check it (and adjust if required) before simulationg
* PDF reports (of simulations and building blocks) are not supported anymore.
