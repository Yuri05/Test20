# Downloads:

- [Full setup TODO](https://github.com/Open-Systems-Pharmacology/Suite/releases/download/v12.2/OSPSuite-Full.12.2.XXX.exe) 

  |**MD5-Hash**| **SHA256-Hash**|
  |-|-|
  |`TODO`|`TODO` |

    TODO<a href="https://www.virustotal.com/gui/file/XXX"><img src="https://img.shields.io/badge/Scanned%20by%20VirusTotal-000000?style=for-the-badge&logo=virustotal&logoColor=white&labelColor=blue&color=green"></a>
- [**ospsuite** R package TODO](Released with 12.1 => https://github.com/Open-Systems-Pharmacology/OSPSuite-R/releases/tag/v12.3.1)

- [Gene expression database (human)](https://github.com/Open-Systems-Pharmacology/Gene-Expression-Databases/releases/download/v2.0.0/GENEDB_human.expressionDb)
  - Additional gene expression databases for human and animal species can be found [here](https://github.com/Open-Systems-Pharmacology/Gene-Expression-Databases/releases/tag/v3.0.1). 
 <!--   (**NOTE: Validation of these databases is ongoing and not fully complete.**). -->

<details><summary><b>Portable versions of PK-Sim and MoBi</b></summary><br>

Portable versions provide an **alternative** way to use the tools if for some reason the full installation of the OSP software suite is not practical.
No installation is required: just download and extract the zip archives and run **PKSim.exe** or **MoBi.exe** from the extracted folder.

* [Download PK-Sim 12.2 portable version TODO](https://github.com/Open-Systems-Pharmacology/PK-Sim/releases/tag/v12.2.XXX)
* [Download MoBi 12.2 portable version TODO](https://github.com/Open-Systems-Pharmacology/MoBi/releases/tag/v12.2.XXX)

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
* [Ontogeny not properly updated in simulations after changing in Expression Profile](https://github.com/Open-Systems-Pharmacology/PK-Sim/issues/3340)
* [Resetting the value in the Expression Profile building block is not propagated to Individual/Population building blocks](https://github.com/Open-Systems-Pharmacology/PK-Sim/issues/2530)
* [Reference concentration units are not updated in individual after reset](https://github.com/Open-Systems-Pharmacology/PK-Sim/issues/3313)
* [Error when selecting user defined variability in pregnancy models](https://github.com/Open-Systems-Pharmacology/PK-Sim/issues/2964)
* [Issues with the progress bar](https://github.com/Open-Systems-Pharmacology/PK-Sim/issues/3278)
* [Renaming simulation to compound name possible](https://github.com/Open-Systems-Pharmacology/PK-Sim/issues/3003)
* ["Effective molecular weight" can become negative](https://github.com/Open-Systems-Pharmacology/PK-Sim/issues/2900)
* [Unnecessary `Project has changed. Save changes?` prompt](https://github.com/Open-Systems-Pharmacology/PK-Sim/issues/3272)
* [Population chart issue](https://github.com/Open-Systems-Pharmacology/PK-Sim/issues/3279)
* [Security dialogue missing when parameter identification is running](https://github.com/Open-Systems-Pharmacology/PK-Sim/issues/874)
* [Batch-run of simulations using context menu](https://github.com/Open-Systems-Pharmacology/PK-Sim/issues/3287)
* [Parameter edit view - allow copy path for parameters](https://github.com/Open-Systems-Pharmacology/PK-Sim/issues/3320)
* [Display "Simulation Fail" rate for population simulations](https://github.com/Open-Systems-Pharmacology/PK-Sim/issues/3310)

### MoBi
* [Batch-run of simulations using context menu](https://github.com/Open-Systems-Pharmacology/MoBi/issues/2128)
* [Simulation cannot be closed due to invalid output intervals](https://github.com/Open-Systems-Pharmacology/MoBi/issues/2166)
* [Exception when trying to paste a parameter into the parameter tree of a simulation](https://github.com/Open-Systems-Pharmacology/MoBi/issues/234)
* [Order of module building blocks in simulation](https://github.com/Open-Systems-Pharmacology/MoBi/issues/2125)
* [Unnecessary `Project has changed. Save changes?` prompt](https://github.com/Open-Systems-Pharmacology/MoBi/issues/2135)
* [Security dialogue missing after renaming parameter identification task](https://github.com/Open-Systems-Pharmacology/MoBi/issues/313)
* [MoBi portable - the "PK-Sim executable path" option is not respected](https://github.com/Open-Systems-Pharmacology/MoBi/issues/2036)
* [New dimensions missing in portable version of MoBi](https://github.com/Open-Systems-Pharmacology/MoBi/issues/2117)
* [Adding a physical container to a spatial structure does not register the MoleculeProperties container](https://github.com/Open-Systems-Pharmacology/MoBi/issues/2116)
* [Adding a sum formula in the events building block: Unhandled exception occurs](https://github.com/Open-Systems-Pharmacology/MoBi/issues/2103)
* [Deleting simulation results does not work](https://github.com/Open-Systems-Pharmacology/MoBi/issues/1817)
* [When loading a pkml with observed data, the data are not shown in the simulation chart](https://github.com/Open-Systems-Pharmacology/MoBi/issues/1717)
* [`TIME` variable is not listed in all "Possible reference objects" lists](https://github.com/Open-Systems-Pharmacology/MoBi/issues/2129)
* [Parameters from Reactions are not listed in the "Possible referenced objects"](https://github.com/Open-Systems-Pharmacology/MoBi/issues/1964)
* [Renaming of an Expression Profile does not rename the initial conditions](https://github.com/Open-Systems-Pharmacology/MoBi/issues/2168)
* [Do not allow "*" in path names](https://github.com/Open-Systems-Pharmacology/MoBi/issues/561)
* [Parameter Values building block: New Parameter Value -> "Relative path" does not make sense](https://github.com/Open-Systems-Pharmacology/MoBi/issues/2099)
* [Extend a Parameter Values building block with Expression Profiles - do not create the same formula multiple times](https://github.com/Open-Systems-Pharmacology/MoBi/issues/1997)
* [Deleting of observed data takes too long](https://github.com/Open-Systems-Pharmacology/MoBi/issues/2142)
* [Performance issue with creating a simulation using Expression Profiles for proteins that are not part of the model](https://github.com/Open-Systems-Pharmacology/MoBi/issues/2109)
* [Import applications with rename should change all hidden tags](https://github.com/Open-Systems-Pharmacology/MoBi/issues/2003)
* [Export of Parameter Values to Excel - do not export values defined by a formula](https://github.com/Open-Systems-Pharmacology/MoBi/issues/1985)
* [Simulation -> Observed Data -> delete multiple entries in one step](https://github.com/Open-Systems-Pharmacology/MoBi/issues/1748)
* [Default simulation settings -> Output Selections -> Cannot add a new output if the list is empty](https://github.com/Open-Systems-Pharmacology/MoBi/issues/2161)

### PK-Sim and MoBi
* [Sensitivity analysis runs, but no results are produced](https://github.com/Open-Systems-Pharmacology/OSPSuite.Core/issues/2447)
* [Deleting a running parameter identification should be forbidden](https://github.com/Open-Systems-Pharmacology/OSPSuite.Core/issues/2651)
* [Security dialogue missing after renaming parameter identification](https://github.com/Open-Systems-Pharmacology/OSPSuite.Core/issues/2673)
* [Wrong dimension prompt for GeoStd error when importing observed data](https://github.com/Open-Systems-Pharmacology/OSPSuite.Core/issues/2639)
* [Observed data can be loaded in MoBi but not in R](https://github.com/Open-Systems-Pharmacology/OSPSuite-R/issues/1632)
* [Residuals vs time plots - re-adding data plots them as lines and not symbols](https://github.com/Open-Systems-Pharmacology/OSPSuite.Core/issues/1669)
* [Differences in simulation configuration are not shown](https://github.com/Open-Systems-Pharmacology/OSPSuite.Core/issues/2660)
* [Renaming of an Expression Profile does not rename the Initial Conditions](https://github.com/Open-Systems-Pharmacology/OSPSuite.Core/issues/2707)
* [Watermark shown in GoDiagram window](https://github.com/Open-Systems-Pharmacology/OSPSuite.Core/issues/2683)
* [Import data set from excel - error message should show the name of the sheet](https://github.com/Open-Systems-Pharmacology/OSPSuite.Core/issues/2648)
* [Simulation -> Observed Data -> Deleting an entry refreshes the whole list](https://github.com/Open-Systems-Pharmacology/OSPSuite.Core/issues/2705)
* [Exporting results to Excel renders MoBi unresponsive for large results](https://github.com/Open-Systems-Pharmacology/OSPSuite.Core/issues/2636)
* [Performance issue with creating a simulation using Expression Profiles for proteins that are not part of the model](https://github.com/Open-Systems-Pharmacology/OSPSuite.Core/issues/2646)

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

### OSP Platform qualification library and PBPK Models Library
#### PBPK Models library extended
New PBPK models added:
* TODO

Model building process and model quality of every new PBPK model is documented in the corresponding _model evaluation report_. 

#### New releases of OSP Platform qualification library and PBPK Models Library

As with every new OSP Suite release, ALL platform qualification reports and model evaluation reports have been recreated with the new version of the OSP Suite:
* [**_OSP Qualification Reports library_**](https://github.com/Open-Systems-Pharmacology/OSP-Qualification-Reports)
  * See the [Release Notes](https://github.com/Open-Systems-Pharmacology/OSP-Qualification-Reports/releases/tag/v12.2) for a full list of changes. 
* [**_OSP-PBPK-Model-Library_**](https://github.com/Open-Systems-Pharmacology/OSP-PBPK-Model-Library)
  * See the [Release Notes](https://github.com/Open-Systems-Pharmacology/OSP-PBPK-Model-Library/releases/tag/v12.2) for a full list of changes. 

### New release of the **ospsuite** R package

* Installation and new features: see [here TODO](released with 12.1 => https://github.com/Open-Systems-Pharmacology/OSPSuite-R/releases/tag/v12.3.1)
* Documentation: see [here](https://www.open-systems-pharmacology.org/OSPSuite-R)

### New release of the **tlf** R package

* Installation and new features: see [here TODO](released with 12.1 => https://github.com/Open-Systems-Pharmacology/TLF-Library/releases/tag/v1.6.1)
* Documentation: see [here](https://www.open-systems-pharmacology.org/TLF-Library)
