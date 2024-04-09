# Downloads:

- [Full setup](https://github.com/Open-Systems-Pharmacology/Suite/releases/download/v11.3/OSPSuite-Full.11.3.20.exe) 

  |**MD5-Hash**| **SHA256-Hash**|
  |-|-|
  |`5da0e1b370941f5e6628401cdd0dce1e`|`092ee97cb65f2259542409982e1c9041a8d58291fe5c7daed371d9b538642624` |

- [**ospsuite** R package **TODO after 11.3 release of ospsuite-R created**]()

- [Gene expression database (human)](https://github.com/Open-Systems-Pharmacology/Gene-Expression-Databases/releases/download/v2.0.0/GENEDB_human.expressionDb)


# Release Notes for the Open Systems Pharmacology Software Suite 11 Update 3

## New features
This is a pure bug fix and performance improvement release. No new features implemented.

## Fixed issues and Improvements

### PK-Sim
* [**Observed data mappings get duplicated when cloning a simulation**](https://github.com/Open-Systems-Pharmacology/PK-Sim/issues/2592)
* [Changing the transport direction in the expression profile is not applied in the simulation.](https://github.com/Open-Systems-Pharmacology/PK-Sim/issues/2761)
* [Projects created with version $`\leq 10`$  are sometimes not exported correctly to a snapshot with version $`\geq 11`$.](https://github.com/Open-Systems-Pharmacology/PK-Sim/issues/2558)
* [Error displaying PK analysis in population simulation in some scenarios](https://github.com/Open-Systems-Pharmacology/PK-Sim/issues/2632)
* [Create Individual: wrongly memorized age](https://github.com/Open-Systems-Pharmacology/PK-Sim/issues/2808)
* [Unit of t<sub>1/2</sub> in individual enzyme expression not updated when changing unit in expression profile](https://github.com/Open-Systems-Pharmacology/PK-Sim/issues/2847)
* [`Concentration` parameter must be created with `CanBeVaried = false`](https://github.com/Open-Systems-Pharmacology/PK-Sim/issues/2691)

### PK-Sim and MoBi
* [**Parameter identification: significant performance improvement when dealing with large number of observed data sets**](https://github.com/Open-Systems-Pharmacology/OSPSuite.Core/issues/2203)
* [**Performance improvement when handling charts with many displayed curves**](https://github.com/Open-Systems-Pharmacology/OSPSuite.Core/issues/1991)
* [Crash in cloned parameter identification after project save/load](https://github.com/Open-Systems-Pharmacology/OSPSuite.Core/issues/2217)
* [`getAllParametersMatching()` should append `|*` to each path that ends with `|**`.](https://github.com/Open-Systems-Pharmacology/OSPSuite.Core/issues/2211)

### New release of the **ospsuite** R package
No new features. New release only due to the changes in the embedded OSP libraries.
