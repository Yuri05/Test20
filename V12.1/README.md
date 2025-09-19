# Downloads:

- [Full setup TODO](https://github.com/Open-Systems-Pharmacology/Suite/releases/download/v12.1/OSPSuite-Full.12.1.136.exe) 

  |**MD5-Hash**| **SHA256-Hash**|
  |-|-|
  |`TODO`|`TODO` |

- [**ospsuite** R package TODO](https://github.com/Open-Systems-Pharmacology/OSPSuite-R/releases/tag/v12.2.0)

- [Gene expression database (human)](https://github.com/Open-Systems-Pharmacology/Gene-Expression-Databases/releases/download/v2.0.0/GENEDB_human.expressionDb)
  - Additional gene expression databases for human and animal species can be found [here](https://github.com/Open-Systems-Pharmacology/Gene-Expression-Databases/releases/tag/v3.0.1). 
 <!--   (**NOTE: Validation of these databases is ongoing and not fully complete.**). -->

<details><summary><b>Portable versions of PK-Sim and MoBi</b></summary><br>

Portable versions provide an **alternative** way to use the tools if for some reason the full installation of the OSP software suite is not practical.
No installation is required: just download and extract the zip archives and run **PKSim.exe** or **MoBi.exe** from the extracted folder.

* [Download PK-Sim 12.1 portable version](https://github.com/Open-Systems-Pharmacology/PK-Sim/releases/tag/v12.1.222)
* [Download MoBi 12.1 portable version](https://github.com/Open-Systems-Pharmacology/MoBi/releases/tag/v12.1.227)

Notes for Portable Versions:

1. Portable versions do not affect the installed OSP Suite and do not interfere with each other. 
 
2. If you only need one tool (e.g. only PK-Sim) - there is no need to download another portable tool(s).
 
3. PK-Sim and MoBi rely on some common Windows components: **.NET Framework** and **C++ Runtime redistributable**. 
In most cases these components are already installed on the target machine. In the very unlikely case that they aren't:
    * If PK-Sim (or MoBi) Portable crashes immediately on startup: The _.NET Framework_ is missing. Download and install it from [here] (https://go.microsoft.com/fwlink/?LinkID=863265).
    * If the program starts and you can create a simulation, but running a simulation crashes: The _C++ Runtime_ is missing. Download and install it from [here](https://aka.ms/vs/16/release/vc_redist.x64.exe).
 
4. If you use the functionality "Send to MoBi" in PK-Sim: you have to enter the location of MoBi.exe (portable) in the program options (same vice versa for MoBi).
 
5. When you double-click PK-Sim or MoBi project in Windows Explorer - it will always start the **installed application** (the one installed with the full OSP Suite setup), not one of the portables.
 
6. If you are using the OSP Qualification Runner (as part of the OSP Qualification Framework) - the path to the portable PK-Sim folder must be passed as an argument, otherwise the installed version will be used.
</details> 

# Release Notes for the Open Systems Pharmacology Software Suite 12 Update 1

## New features
<!--
<sup>(*)</sup> Implementation of the features was sponsored by **XXX**
-->

### MoBi: Trace back source of a quantity in simulation
TODO Description <br>
TODO Screenshots

### MoBi: Spatial Structure with Individual selection for preview
<!-- **Issue:** [Spatial Structure w/ Individual selection for preview](https://github.com/Open-Systems-Pharmacology/MoBi/issues/947) -->
Adds a way to select a specific individual for preview in the spatial structure view. This feature allows users to visualize and apply individual-specific settings directly within the spatial structure, improving model personalization and analysis.

TODO Screenshots

### Concurrent execution of simulations
TODO Description <br>
TODO Screenshots


### Batch edit mode for charts
<!-- **Issue:** [Batch edit mode for charts](https://github.com/Open-Systems-Pharmacology/OSPSuite.Core/issues/2536) -->
When editing charts with many data points, each change triggers a chart update, causing significant delays. The new batch edit mode allows users to temporarily disable chart updates, make multiple changes to curves, and then update all at once. This speeds up the editing workflow for large datasets and ensures that users can work efficiently without waiting for each update.
- The UI indicates when the chart is out-of-date due to batch editing.
- Users can toggle this mode when editing curves or using the data browser.

TODO Screenshots


### Exports chart to png
<!-- **Issue:** [Feature: Export chart to png](https://github.com/Open-Systems-Pharmacology/OSPSuite.Core/issues/1801) -->
A highly requested feature, this adds the ability to export any chart directly to a PNG file for use in presentations or publications. The implementation supports custom formatting and watermark settings, similar to the "copy to clipboard" function.

TODO Screenshots

### MoBi: Create Subfolders possible for modules
<!-- **Issue:** [Feature wish: Create Subfolders possible for modules](https://github.com/Open-Systems-Pharmacology/MoBi/issues/527) -->
Enables users to organize modules within building block sections by creating subfolders. 
This feature is especially useful when working with multiple structural models, helping to keep the workspace tidy and navigable.

TODO Screenshots


### Save/load neighborhood
<!-- **Issue:** [Save/load neighborhood](https://github.com/Open-Systems-Pharmacology/MoBi/issues/1318) -->
Users can now save a neighborhood configuration to a PKML file and load it from PKML. This supports efficient reuse and sharing of neighborhood setups, streamlining workflows for complex modeling scenarios.


### Calculation of sensitivity in PI should be interruptable
<!-- **Issue:** [Calculation of sensitivity in PI should be interruptable](https://github.com/Open-Systems-Pharmacology/OSPSuite.SimModel/issues/175) -->
Sensitivity calculations in parameter identification (PI) can now be interrupted by the user, similar to regular simulation runs. This saves time and resources, allowing users to halt long or unneeded calculations without waiting for them to finish.




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
* Propofol

Model building process and model quality of every new PBPK model is documented in the corresponding _model evaluation report_. 

#### New releases of OSP Platform qualification library and PBPK Models Library

As with every new OSP Suite release, ALL platform qualification reports and model evaluation reports have been recreated with the new version of the OSP Suite:
* [**_OSP Qualification Reports library_**](https://github.com/Open-Systems-Pharmacology/OSP-Qualification-Reports) 
* [**_OSP-PBPK-Model-Library_**](https://github.com/Open-Systems-Pharmacology/OSP-PBPK-Model-Library)

### New release of the **ospsuite** R package

* Installation and new features: s. [here](https://github.com/Open-Systems-Pharmacology/OSPSuite-R/releases/latest)
* Documentation: s. [here](https://www.open-systems-pharmacology.org/OSPSuite-R)

### New release of the **tlf** R package

* Installation and new features: s. [here](https://github.com/Open-Systems-Pharmacology/TLF-Library/releases/latest)
* Documentation: s. [here](https://www.open-systems-pharmacology.org/TLF-Library)

## Fixed issues and Improvements

### PK-Sim
* [Hexadecimal value 0x1F is an invalid character](https://github.com/Open-Systems-Pharmacology/PK-Sim/issues/3071)
* [Population simulations: wrong geoSD calculation](https://github.com/Open-Systems-Pharmacology/PK-Sim/issues/3132)
* [Parameters under Applications not found when importing from older snapshot](https://github.com/Open-Systems-Pharmacology/PK-Sim/issues/3069)


### MoBi
* [Expression profiles missing in MoBi unless individual is opened in PK-Sim](https://github.com/Open-Systems-Pharmacology/PK-Sim/issues/3145)
* [Invalid paths in event assignments throws unhandled exception](https://github.com/Open-Systems-Pharmacology/OSPSuite.Core/issues/2461)
* [Simulation view - show the "Parameters" tab by default instead of "Properties"](https://github.com/Open-Systems-Pharmacology/MoBi/issues/1723)
* [Typing container name not possible after choosing parent path](https://github.com/Open-Systems-Pharmacology/MoBi/issues/1929)
* [Copy path of a parameter/container in the simulation](https://github.com/Open-Systems-Pharmacology/MoBi/issues/1639)
* [Throw a warning message for non-existing neighbourhood](https://github.com/Open-Systems-Pharmacology/OSPSuite.Core/issues/2550)
* [Export of comparison results fails](https://github.com/Open-Systems-Pharmacology/OSPSuite.Core/issues/2580)
* [Add protein expression to Parameter Values does not always assign value](https://github.com/Open-Systems-Pharmacology/OSPSuite.Core/issues/2518)
* ["Negative values allowed" check box behavior](https://github.com/Open-Systems-Pharmacology/MoBi/issues/2091)
* [Error when adding reaction parameter and canceling in PK-Sim module](https://github.com/Open-Systems-Pharmacology/MoBi/issues/2068)
* [Extend PV BB with expression profiles - wrong formula for plasma expression](https://github.com/Open-Systems-Pharmacology/OSPSuite.Core/issues/2599)
* [Initial conditions BB: Extend from BB and select an Expression Profile](https://github.com/Open-Systems-Pharmacology/MoBi/issues/2030)
* [Rollback crashes in specific scenario](https://github.com/Open-Systems-Pharmacology/MoBi/issues/1966)
* [Load Initial Conditions BB: select exported Expression Profile](https://github.com/Open-Systems-Pharmacology/MoBi/issues/2031)
* [Parameter identification: renaming a parameter makes transfer of results impossible](https://github.com/Open-Systems-Pharmacology/OSPSuite.Core/issues/2257)
* [Observed data: Multi-select folders and Group by](https://github.com/Open-Systems-Pharmacology/OSPSuite.Core/issues/2411)
* [Errors in PI sensitivity calculation not obvious to user](https://github.com/Open-Systems-Pharmacology/OSPSuite.Core/issues/2400)
* [Silent crash when creating a circular reference](https://github.com/Open-Systems-Pharmacology/MoBi/issues/1045)
* [TIME alias reset](https://github.com/Open-Systems-Pharmacology/OSPSuite.Core/issues/2465)
* [Events BB get no red mark when out of date](https://github.com/Open-Systems-Pharmacology/MoBi/issues/1882)
* [Cannot select relative or absolute in events and spatial structure parameter edit](https://github.com/Open-Systems-Pharmacology/MoBi/issues/1804)
* [Wrong behavior cancelling Dimension Select #3 in Data Importer](https://github.com/Open-Systems-Pharmacology/OSPSuite.Core/issues/2586)
* [Wrong behavior in observed data importer](https://github.com/Open-Systems-Pharmacology/OSPSuite.Core/issues/2585)
* [Event assignment paths cannot be resolved](https://github.com/Open-Systems-Pharmacology/OSPSuite.Core/issues/2502)
* [Can't open existing project, Error: hexadecimal value 0x1F, is an invalid character](https://github.com/Open-Systems-Pharmacology/MoBi/issues/1794)
* [Creating a new physical container does not create MoleculeProperties node](https://github.com/Open-Systems-Pharmacology/MoBi/issues/1984)
* [Undo of clone simulation throws exception](https://github.com/Open-Systems-Pharmacology/MoBi/issues/1976)
* [Closing a simulation takes too long](https://github.com/Open-Systems-Pharmacology/MoBi/issues/1612)


### PK-Sim and MoBi
* [Observed data: Multiselect folders and "Group by"](https://github.com/Open-Systems-Pharmacology/MoBi/issues/1797)
* [Opening a new file does not drop imported data in Data importer](https://github.com/Open-Systems-Pharmacology/OSPSuite.Core/issues/2114)
* [Error when selecting "Link Data To Simulations"](https://github.com/Open-Systems-Pharmacology/OSPSuite.Core/issues/2601)
* [Add Tag dialog: focus in the text field](https://github.com/Open-Systems-Pharmacology/OSPSuite.Core/issues/2437)
* [Allow faster cancel from Parameter Identifications](https://github.com/Open-Systems-Pharmacology/OSPSuite.Core/issues/2404)
* [Error when importing sheet with empty row](https://github.com/Open-Systems-Pharmacology/OSPSuite.Core/issues/2115)
* [Dimension "Fraction" resets to "Dimensionless"](https://github.com/Open-Systems-Pharmacology/OSPSuite.Core/issues/2371)
* [`loadDataSetsFromExcel` throws unclear error for invalid configuration](https://github.com/Open-Systems-Pharmacology/OSPSuite.Core/issues/2467)
* [Error when loading a file](https://github.com/Open-Systems-Pharmacology/OSPSuite.Core/issues/1481)
