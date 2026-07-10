# Downloads:

- [Full setup](https://github.com/Open-Systems-Pharmacology/Suite/releases/download/v12.3.263/OSPSuite-Full.12.3.263.exe) 

  |**MD5-Hash**| **SHA256-Hash**|
  |-|-|
  |`99a1bca9f36d896e594d6759d24824c8`|`e910a46f76c852f9f5a021257c021a9e5c101934f722ef11cb9ff9eb10a939aa` |

    <a href="https://www.virustotal.com/gui/file/e910a46f76c852f9f5a021257c021a9e5c101934f722ef11cb9ff9eb10a939aa"><img src="https://img.shields.io/badge/Scanned%20by%20VirusTotal-000000?style=for-the-badge&logo=virustotal&logoColor=white&labelColor=blue&color=green"></a>
- [**ospsuite** R package](https://github.com/Open-Systems-Pharmacology/OSPSuite-R/releases/latest)

- [Gene expression database (human)](https://github.com/Open-Systems-Pharmacology/Gene-Expression-Databases/releases/download/v2.0.0/GENEDB_human.expressionDb)
  - Additional gene expression databases for human and animal species can be found [here](https://github.com/Open-Systems-Pharmacology/Gene-Expression-Databases/releases/latest). 
 <!--   (**NOTE: Validation of these databases is ongoing and not fully complete.**). -->

<details><summary><b>Portable versions of PK-Sim and MoBi</b></summary><br>

Portable versions provide an **alternative** way to use the tools if for some reason the full installation of the OSP software suite is not practical.
No installation is required: just download and extract the zip archives and run **PKSim.exe** or **MoBi.exe** from the extracted folder.

* [Download PK-Sim 12.3 portable version](https://github.com/Open-Systems-Pharmacology/PK-Sim/releases/tag/v12.3.173)
* [Download MoBi 12.3 portable version](https://github.com/Open-Systems-Pharmacology/MoBi/releases/tag/v12.3.136)

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

# Release Notes for the Open Systems Pharmacology Software Suite 12 Update 3 Hotfix 1

## Fixed issues and Improvements

### PK-Sim

- [Fixed incorrect updates of effective molecular weight during validation](https://github.com/Open-Systems-Pharmacology/PK-Sim/issues/3580)

### OSP Platform qualification library and PBPK Models Library
#### Platform qualification library extended
New reports added:
* Pediatric Qualification Package: P-gp Ontogeny

#### New releases of OSP Platform qualification library and PBPK Models Library

As with every new OSP Suite release, ALL platform qualification reports and model evaluation reports have been recreated with the new version of the OSP Suite:
* [**_OSP Qualification Reports library_**](http://www.open-systems-pharmacology.org/OSP-Qualification-Reports)
  * See the [Release Notes](https://github.com/Open-Systems-Pharmacology/OSP-Qualification-Reports/releases/tag/v12.3.1) for a full list of changes. 
* [**_OSP-PBPK-Model-Library_**](http://www.open-systems-pharmacology.org/OSP-PBPK-Model-Library)
  * See the [Release Notes](https://github.com/Open-Systems-Pharmacology/OSP-PBPK-Model-Library/releases/tag/v12.3.1) for a full list of changes. 

### New release of the **ospsuite.reportingengine** R package

* Installation and new features: see [here](https://github.com/Open-Systems-Pharmacology/OSPSuite.ReportingEngine/releases/latest)
* Documentation: see [here](https://www.open-systems-pharmacology.org/OSPSuite.ReportingEngine)

