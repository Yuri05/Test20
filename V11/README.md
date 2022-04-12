<p align="center">
<img width="182" src="https://user-images.githubusercontent.com/25061876/162976311-ed939cb7-7abb-4b29-a6ce-d0726a44479f.png">
</p>

# Beta-Release of PK-Sim 11 and MoBi 11
Dear OSP users, 

We are happy to announce that the new Version 11 of PK-Sim and MoBi is now available for beta-testing. The beta-test phase will last until the **end of April**.
The goal of the beta release is to give the commmunity an opportunity to test the new features and to report any problems and give feedback regarding the new implementation.

## How can you test the new features?
You can use the *portable versions* of PK-Sim and MoBi  (download links below). The portable versions do not require installation and can be used in parallel to the official OSP Suite 10.

Your feedback on the new features is highly welcome.

**Important**: The beta-test versions are not final releases of the software packages: please use them for testing purposes only, but not for productive work.

## Downloads:

- [PK-Sim 11 beta portable](http://pk-sim-portable.open-systems-pharmacology.org)

- [MoBi 11 beta portable](http://mobi-portable.open-systems-pharmacology.org)

## New features

### [Experimental!] Creating individuals and populations with CKD (Chronic Kidney Disease)

Already in version 10 of the software it was possible to use predefined CKD templates (based on the publication [Malik PRV, Yeung CHT, Advani U, Dije S, Edginton AN. A Physiological Approach to Pharmacokinetics in Chronic Kidney Disease. J Clin Pharmacol 2020. 60 Suppl 1: S52-S62. doi: 10.1002/jcph.1713](https://accp1.onlinelibrary.wiley.com/doi/full/10.1002/jcph.1713)).

With version 11, CKD individuals and populations can now be created dynamically.
When creating an individual, a new option **"Disease State"** is provided, which allows a selection between _Healthy_ and diseased individuals.

<p align="center">
<img width="800" src="https://user-images.githubusercontent.com/25061876/162768013-1c1b7ab9-e980-4d67-ba3c-abbd36630bdb.png">
</p>

For the details s. the [documentation](https://docs.open-systems-pharmacology.org/v/v11/working-with-pk-sim/pk-sim-documentation/pk-sim-creating-individuals#disease-state) and the original publication by Malik et al.

### Expression Profile as standalone building block
Until PK-Sim version 10, expression profiles could only be created _within an individual or a population_.
Starting with the version 11, expression profiles can be created independently (like all other building blocks) and thus can be **reused** in different individuals/populations.
<p align="center">
<img src="https://881660647-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2FewOAYfFFhObyan6wZQs0%2Fuploads%2Fgit-blob-969bf4fe9c3d8a2534a34cb1a5a4864584c604c6%2FCreateExpressionProfile.png?alt=media">
<img src="https://user-images.githubusercontent.com/25061876/162777774-ea5c00c7-7c9f-42a5-b411-8d81be0e3ec0.png">
</p>

For the details s. the [documentation](https://docs.open-systems-pharmacology.org/v/v11/working-with-pk-sim/pk-sim-documentation/pk-sim-expression-profile)

### Building block templates can be downloaded directly from the OSP GitHub site
<p align="center">
<img src="https://user-images.githubusercontent.com/25061876/162787879-a4ef5caa-fb0e-495c-b85c-53b04a054314.png">
</p>

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
Users reported some issue with the layout of PK-Sim or MoBi when using custom font scaling on 4k monitors (or screen with high resolutions). Some UI elements were hidden, some icons were blurry, some text hard to read etc. Version 11 of PK-Sim and MoBi should now behave as expected, even when using custom font scaling. Give it a try and let us know.


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
