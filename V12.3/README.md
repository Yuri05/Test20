# Downloads:

- [Full setup TODO](https://github.com/Open-Systems-Pharmacology/Suite/releases/download/v12.3/OSPSuite-Full.12.3.NNNNN.exe) 

  |**MD5-Hash**| **SHA256-Hash**|
  |-|-|
  |`TODO`|`TODO` |

    <a href="https://www.virustotal.com/gui/file/TODO"><img src="https://img.shields.io/badge/Scanned%20by%20VirusTotal-000000?style=for-the-badge&logo=virustotal&logoColor=white&labelColor=blue&color=green"></a>
- [**ospsuite** R package TODO](https://github.com/Open-Systems-Pharmacology/OSPSuite-R/releases/tag/v12.NNN.NNN)

- [Gene expression database (human)](https://github.com/Open-Systems-Pharmacology/Gene-Expression-Databases/releases/download/v2.0.0/GENEDB_human.expressionDb)
  - Additional gene expression databases for human and animal species can be found [here TODO](https://github.com/Open-Systems-Pharmacology/Gene-Expression-Databases/releases/tag/v3.0.1). 
 <!--   (**NOTE: Validation of these databases is ongoing and not fully complete.**). -->

<details><summary><b>Portable versions of PK-Sim and MoBi</b></summary><br>

Portable versions provide an **alternative** way to use the tools if for some reason the full installation of the OSP software suite is not practical.
No installation is required: just download and extract the zip archives and run **PKSim.exe** or **MoBi.exe** from the extracted folder.

* [Download PK-Sim 12.3 portable version TODO](https://github.com/Open-Systems-Pharmacology/PK-Sim/releases/tag/v12.3.NNNNN)
* [Download MoBi 12.3 portable version TODO](https://github.com/Open-Systems-Pharmacology/MoBi/releases/tag/v12.3.NNNNN)

Notes for Portable Versions:

1. Portable versions do not affect the installed OSP Suite and do not interfere with each other. 
 
2. If you only need one tool (e.g. only PK-Sim) - there is no need to download another portable tool(s).
 
3. PK-Sim and MoBi rely on some common Windows components: **.NET Framework** and **C++ Runtime redistributable**. 
In most cases these components are already installed on the target machine. In the very unlikely case that they aren't:
    * If PK-Sim (or MoBi) Portable crashes immediately on startup: The _.NET Framework_ is missing. Download and install it from [here](https://go.microsoft.com/fwlink/?LinkID=863265).
    * If the program starts and you can create a simulation, but running a simulation crashes: The _C++ Runtime_ is missing. Download and install it from [here](https://aka.ms/vs/17/release/vc_redist.x64.exe).
 
4. If you use the functionality "Send to MoBi" in PK-Sim: you have to enter the location of MoBi.exe (portable) in the program options (vice versa for MoBi).
 
5. When you double-click PK-Sim or MoBi project in Windows Explorer - it will always start the **installed application** (the one installed with the full OSP Suite setup), not one of the portables.
 
6. If you are using the OSP Qualification Runner (as part of the OSP Qualification Framework) - the path to the portable PK-Sim folder must be passed as an argument, otherwise the installed version will be used.
</details> 

# Release Notes for the Open Systems Pharmacology Software Suite 12 Update 2

## Fixed issues and Improvements

### PK-Sim

- [Allow import/export of building blocks to snapshot in standard mode](https://github.com/Open-Systems-Pharmacology/PK-Sim/issues/1312)
- [Parameter view - make the user settings layout apply to all instances](https://github.com/Open-Systems-Pharmacology/PK-Sim/issues/2881)
- [Load compound from snapshot error in developer version](https://github.com/Open-Systems-Pharmacology/PK-Sim/issues/2535)
- [Cloning a time profile in simulation loses many settings](https://github.com/Open-Systems-Pharmacology/PK-Sim/issues/2486)
- [Cloning a population simulation retains the old simulation name in the legend](https://github.com/Open-Systems-Pharmacology/PK-Sim/issues/1006)
- [Reset of distributed individual parameters in a simulation does not work](https://github.com/Open-Systems-Pharmacology/PK-Sim/issues/3562)
- [Modified parameters not exported to snapshot](https://github.com/Open-Systems-Pharmacology/PK-Sim/issues/3530)
- [Create Compound UI destroyed](https://github.com/Open-Systems-Pharmacology/PK-Sim/issues/3396)

### MoBi

- [Check for NaN and Inf values upon creating a model configuration](https://github.com/Open-Systems-Pharmacology/MoBi/issues/1405)
- [Comparison table - show formula types when they differ](https://github.com/Open-Systems-Pharmacology/MoBi/issues/1259)
- [Remove classifications when removing modules](https://github.com/Open-Systems-Pharmacology/MoBi/issues/2306)
- [For multiple doses, improve how applications are organized using presentation](https://github.com/Open-Systems-Pharmacology/MoBi/issues/2291)
- [Renaming molecules to existing molecule names causes validation to fail](https://github.com/Open-Systems-Pharmacology/MoBi/issues/2280)
- [Add user setting for default parameter grouping](https://github.com/Open-Systems-Pharmacology/MoBi/issues/2239)
- [Create context menu for adding initial conditions](https://github.com/Open-Systems-Pharmacology/MoBi/issues/2235)
- [After a simulation runs, the highlighted simulation should not change](https://github.com/Open-Systems-Pharmacology/MoBi/issues/2231)
- [When cloning a simulation, the observed data is not enabled in the chart by default](https://github.com/Open-Systems-Pharmacology/MoBi/issues/2230)
- [It is possible to create a duplicate formula with the same name](https://github.com/Open-Systems-Pharmacology/MoBi/issues/2206)
- [Automatic rename of like-named reactions](https://github.com/Open-Systems-Pharmacology/MoBi/issues/2187)
- [Renaming reactions on load should update formula paths](https://github.com/Open-Systems-Pharmacology/MoBi/issues/2186)
- [PKML export default file name](https://github.com/Open-Systems-Pharmacology/MoBi/issues/2121)
- [Parameter Values building block: parameters of reactions are not shown when creating new parameter value](https://github.com/Open-Systems-Pharmacology/MoBi/issues/2100)
- [Undo of change molecule start amount does not revert extension module back to PK-Sim module](https://github.com/Open-Systems-Pharmacology/MoBi/issues/2083)
- [Event assignments: parameters from individuals are not displayed when changing entity](https://github.com/Open-Systems-Pharmacology/MoBi/issues/2057)
- [Parameters from reactions are not listed in the possible referenced objects](https://github.com/Open-Systems-Pharmacology/MoBi/issues/1964)
- [Make reaction parameters accessible to the parameter value building block references to add](https://github.com/Open-Systems-Pharmacology/MoBi/issues/1819)
- [Molecule properties are not added to molecules](https://github.com/Open-Systems-Pharmacology/MoBi/issues/1719)
- ["Events" should not be allowed as name for any container](https://github.com/Open-Systems-Pharmacology/MoBi/issues/1157)
- [Import of molecular start values from Excel sheet does not overwrite existing start values](https://github.com/Open-Systems-Pharmacology/MoBi/issues/548)

### PK-Sim and MoBi

- [Export history to CSV or other text format](https://github.com/Open-Systems-Pharmacology/OSPSuite.Core/issues/2714)
- [New dimension: Area per amount per time](https://github.com/Open-Systems-Pharmacology/OSPSuite.Dimensions/issues/39)
- [New dimensions: Amount per area and inversed area](https://github.com/Open-Systems-Pharmacology/OSPSuite.Dimensions/issues/40)
- [Separator selector is styled differently and pops under PK-Sim](https://github.com/Open-Systems-Pharmacology/OSPSuite.Core/issues/2834)
- [Add output path metadata to observed data imports](https://github.com/Open-Systems-Pharmacology/OSPSuite.Core/issues/2787)
- [Make preview option sticky in projects](https://github.com/Open-Systems-Pharmacology/OSPSuite.Core/issues/2767)
- [Parameter identification options not visible on small screens](https://github.com/Open-Systems-Pharmacology/OSPSuite.Core/issues/2739)
- [Include possibility of filtering by user-defined parameters for sensitivity analyses and parameter identifications](https://github.com/Open-Systems-Pharmacology/OSPSuite.Core/issues/2740)
- [When creating a new initial condition, value should default to 0 instead of not available](https://github.com/Open-Systems-Pharmacology/OSPSuite.Core/issues/2743)
- [Run and some other actions are not disabled in the context menu after a parameter identification was started](https://github.com/Open-Systems-Pharmacology/OSPSuite.Core/issues/2836)
- [Reload with same settings fails if sheets were removed](https://github.com/Open-Systems-Pharmacology/OSPSuite.Core/issues/2650)
- [Transferring parameter identification results to simulation doesn't work well when using "use as factor" option](https://github.com/Open-Systems-Pharmacology/OSPSuite.Core/issues/2398)
- [Comparison table for building blocks - show name of the module](https://github.com/Open-Systems-Pharmacology/OSPSuite.Core/issues/2745)
- [Remove check for monotonically increasing time values in data repository](https://github.com/Open-Systems-Pharmacology/OSPSuite.Core/issues/1863)
- [Allow multiple data points with the same time within observed data set](https://github.com/Open-Systems-Pharmacology/OSPSuite.Core/issues/796)
- [Cancelled parameter identification does not show number of evaluations](https://github.com/Open-Systems-Pharmacology/OSPSuite.Core/issues/2814)
- [Parameter identification: erroneous behavior of transfer results to simulation in combination with use as factor](https://github.com/Open-Systems-Pharmacology/OSPSuite.Core/issues/2754)

<!-- ## New features -->
<!--
<sup>(*)</sup> Implementation of the features was sponsored by **XXX**
-->

<!-- ### PK-Sim: XXX TODO -->
<!-- **Issue:** [XXX]() -->

<!-- ### MoBi: XXX TODO -->
<!-- **Issue:** [XXX]() -->

<!-- ### PK-Sim and MoBi: XXX TODO -->
<!-- **Issue:** [XXX]() -->
 
<!--
### OSP Platform qualification library and PBPK Models Library
#### PBPK Models library extended
New PBPK models added:
* ...

Model building process and model quality of every new PBPK model is documented in the corresponding _model evaluation report_. 
-->

<!--
### OSP Platform qualification library and PBPK Models Library
#### PBPK Models library extended
New PBPK models added:
* TODO

Model building process and model quality of every new PBPK model is documented in the corresponding _model evaluation report_. 
-->

#### New releases of OSP Platform qualification library and PBPK Models Library

As with every new OSP Suite release, ALL platform qualification reports and model evaluation reports have been recreated with the new version of the OSP Suite:
* [**_OSP Qualification Reports library_**](https://github.com/Open-Systems-Pharmacology/OSP-Qualification-Reports)
  * See the [Release Notes TODO](https://github.com/Open-Systems-Pharmacology/OSP-Qualification-Reports/releases/tag/vNNNNNN.NNNNNNN) for a full list of changes. 
* [**_OSP-PBPK-Model-Library_**](https://github.com/Open-Systems-Pharmacology/OSP-PBPK-Model-Library)
  * See the [Release Notes](https://github.com/Open-Systems-Pharmacology/OSP-PBPK-Model-Library/releases/tag/vNNNNNN.NNNNNNN) for a full list of changes. 

### New release of the **ospsuite** R package

* Installation and new features: see [here TODO](https://github.com/Open-Systems-Pharmacology/OSPSuite-R/releases/tag/vNNNNNN.NNNNNNN.NNNNN)
* Documentation: see [here](https://www.open-systems-pharmacology.org/OSPSuite-R)

### New release of the **tlf** R package TODO 

* Installation and new features: see [here TODO](https://github.com/Open-Systems-Pharmacology/TLF-Library/releases/tag/vNNNNNN.NNNNNNN.NNNNN)
* Documentation: see [here](https://www.open-systems-pharmacology.org/TLF-Library)
