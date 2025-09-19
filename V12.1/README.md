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

# Release Notes for the Open Systems Pharmacology Software Suite 12

## New features
<!--
<sup>(*)</sup> Implementation of the features was sponsored by **XXX**
-->

### XXXXXX


### XXXXXX


### XXXXXX


### XXXXXX


### XXXXXX


### XXXXXX


### XXXXXX


### XXXXXX


### XXXXXX



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
* [XXXXX](XXXXX)
* [XXXXX](XXXXX)
* [XXXXX](XXXXX)
* [XXXXX](XXXXX)
* [XXXXX](XXXXX)
* [XXXXX](XXXXX)
* [XXXXX](XXXXX)
* [XXXXX](XXXXX)
* [XXXXX](XXXXX)
* [XXXXX](XXXXX)
* [XXXXX](XXXXX)
* [XXXXX](XXXXX)
* [XXXXX](XXXXX)
* [XXXXX](XXXXX)
* [XXXXX](XXXXX)
* [XXXXX](XXXXX)
* [XXXXX](XXXXX)


### MoBi
* [XXXXX](XXXXX)
* [XXXXX](XXXXX)
* [XXXXX](XXXXX)
* [XXXXX](XXXXX)
* [XXXXX](XXXXX)
* [XXXXX](XXXXX)
* [XXXXX](XXXXX)
* [XXXXX](XXXXX)
* [XXXXX](XXXXX)
* [XXXXX](XXXXX)
* [XXXXX](XXXXX)
* [XXXXX](XXXXX)
* [XXXXX](XXXXX)
* [XXXXX](XXXXX)
* [XXXXX](XXXXX)
* [XXXXX](XXXXX)
* [XXXXX](XXXXX)


### PK-Sim and MoBi
* [XXXXX](XXXXX)
* [XXXXX](XXXXX)
* [XXXXX](XXXXX)
* [XXXXX](XXXXX)
* [XXXXX](XXXXX)
* [XXXXX](XXXXX)
* [XXXXX](XXXXX)
* [XXXXX](XXXXX)
* [XXXXX](XXXXX)
* [XXXXX](XXXXX)
