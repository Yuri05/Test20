# Simulation Parameter Sets

## Problem Statement

Users working with PK-Sim simulations frequently override **compound-dependent simulation parameters** (BuildingBlockType = Simulation) that are originally formula-based with constant values. 
_Compound-dependent_ means in this context: the initial formula of the simulation parameter depends on a compound which is used in the simulation configuration as a building block.

These customized parameter values are valuable and represent validated configurations, but currently they exist only within the simulation context and cannot be:

- Saved and reused across different projects
- Shared with other team members
- Applied consistently when creating new simulations with the same compound
- Tracked as part of the compound's validated configuration

This leads to repeated manual work, risk of inconsistency, and loss of institutional knowledge when simulation-specific parameter overrides cannot be persisted back to the compound building block.

## Solution

Introduce **Simulation Parameter Sets** as a new concept attached to Compounds. A Simulation Parameter Set is a named collection of parameter values (using `MOLECULE` keyword for path portability) that can be:

- **Pavel**: I don't think that the `MOLECULE` keyword is required, as the simulation parameter set is always specific for a particular compound.  Renaming of the compound should, however, also change the paths in the parameter values set.

1. **Created** by committing changed (compound-dependent) simulation parameters back to their respective compounds
2. **Selected** when configuring a simulation (one active Simulation Parameter Set per compound, optional)
3. **Applied** automatically during simulation model construction
4. **Exported/Imported** as JSON for sharing and reuse across projects
5. **Edited** within the Compound's new Simulation Parameter Sets tab.
- **Pavel**: No, no edits, only deletion. Or also edits? Definitely, no new entries should be created from the Simulation parameter sets tab. 

The system will track uncommitted (compound-dependent) simulation parameter changes with a visual indicator (orange status) to help users identify parameters that could be committed to Simulation Parameter Sets.

## User Stories

1. As a user, I want to save my optimized simulation parameters back to the compound, so that I can reuse them in future simulations without manual re-entry.

2. As a user, I want to see a visual indicator when my simulation has uncommitted compound-related parameter changes, so that I know there are values I might want to persist.

3. As a user, I want to commit all my changed (compound-dependent) simulation parameters to compounds in a single action, so that I don't have to save them one by one.
- **Pavel**: This should be the only way to commit. Either all or nothing.
- Now I even ask myself. If a Simulation parameter set has been selected that contains changed values for 5 parameters. Now the user changes the value of an additional parameter, but resets the values of two parameters that are stored in the set. I think that if the user commits the changes, the parameters that have been reset should be removed from the Simulation parameter set. A commit should ensure that if the simulation is built with this Simulation parameter set, it is exactly as during the commit action. **Juri**: agree.

4. As a user, I want to review which parameters will be committed before confirming, so that I can verify the changes are correct.

5. As a user, I want to choose whether to create a new Simulation Parameter Set or update an existing one when committing, so that I can organize my parameter configurations appropriately.
**Juri**: Question: if I change parameters of >1 compound and want to commit: is this choice the same for ALL compounds or per Compound?

7. As a user, I want to exclude specific compounds from the commit action, so that I only save parameters for the compounds I intend to update.
- **Pavel**: The "Commit" command should be a property of a compound, no? In that case, only the values for this specific compound are committed. **Juri**: for me: no.

7. As a user, I want to view all Simulation Parameter Sets defined for a compound in a dedicated tab, so that I can see what configurations are available.

8. As a user, I want to edit parameter values within a Simulation Parameter Set, so that I can make corrections without recreating the entire set.
- **Pavel**: are we sure about this? **Juri**: I think we should have editing possibility for the values.

9. As a user, I want to delete individual parameters from a Simulation Parameter Set, so that I can clean up unnecessary entries.

10. As a user, I want to delete entire Simulation Parameter Sets, so that I can remove obsolete configurations.

11. As a user, I want to mark one Simulation Parameter Set as the default for a compound, so that new simulations automatically use my preferred configuration.
**Juri**: I am not sure about this. Especially when using a compound template in a new project: the default setting for Simulation Parameter Set should be **NONE**.
          So either it should be possible that none of the Simulation Parameter Sets is set to default.
          Or: we introduce an empty Simulation Parameter Set, which cannot be deleted und then it can be set to default.

13. As a user, I want to select which Simulation Parameter Set to use when adding a compound to my simulation, so that I can choose the appropriate parameter configuration.

15. As a user, I want the default Simulation Parameter Set to be automatically selected when I add a compound, so that I get sensible defaults without extra clicks.

16. As a user, I want to clear the Simulation Parameter Set selection (choose "None"), so that I can use the original formula-based values instead.

17. As a user, I want parameters applied from a Simulation Parameter Set to behave as compound parameters, so that subsequent changes follow normal compound update logic.
- **Pavel** - don't know. **Juri**: yes, it should be like this imo.

16. As a user, I want to export a Simulation Parameter Set to JSON, so that I can share validated configurations with my team.
- **Pavel** - I don't thinks so..

17. As a user, I want to import a Simulation Parameter Set from JSON into a compound, so that I can use configurations shared by others.
- **Pavel**: This should be part of compound import, I think

18. As a user I want to see warnings when Simulation Parameter Set paths cannot be resolved during simulation creation, so that I know some parameters were not applied.
- **Pavel**: actually, such a case should never happen. If parameters are (re-)moved in a software update, project conversion should take care of it.
- **Juri**: could happen with building block swaps in qualification plans for example. I would produce a warning.

19. As a user, I want my simulation to still be created even if some Simulation Parameter Set paths are invalid, so that minor issues don't block my work.
- **Pavel**: Disagree

20. As a user, I want all Simulation Parameter Set modifications to support undo/redo, so that I can recover from mistakes.
- **Pavel**: Undo yes. Redo? Should be a simulation refresh.

21. As a user, I want to add metadata (like Species) to a Simulation Parameter Set, so that I can document the intended use case.

22. As a user, I want to reset a changed simulation parameter and have it removed from the uncommitted changes list, so that the tracking stays accurate.

23. As a user, I want uncommitted parameter changes to be persisted when saving the project, so that users see the orange indicator when reopening.

24. As a user working with multiple compounds, I want the commit dialog to use the same Simulation Parameter Set name across all compounds, so that related configurations are named consistently.

25. As a MoBi user, I want to load simulations that use Simulation Parameter Sets created in PK-Sim, so that I can continue my work in either tool.
- **Pavel**: parameters from the "Simulation Parameter Set" in PK-Sim should be transfered as PV to MoBi.

## Implementation Decisions

### Domain Model (OSPSuite.Core)

**SimulationParameterSet class:**
- Properties: Name, IsDefault
- ExtendedProperties for metadata (Species stored here, extensible for future needs)
- Contains IReadOnlyList<ParameterValue> (reusing existing ParameterValue class)
- ParameterValues are unique by path within a set
- Paths use `MOLECULE` keyword (not `<MOLECULE>`) for compound-name portability

**Compound changes:**
- Add IReadOnlyList<ParameterSet> property
- Starts as empty list (no default Simulation Parameter Set created automatically) **Juri**: would create an empty default parameter set which cannot be edited or removed (s. the default set remarks above).
- Internal collection management exposed through service/task layer

**SimulationConfiguration changes:**
- Add ParameterSetSelections object to store which Simulation Parameter Set is selected per compound
- Encapsulated with behavior methods, not exposed as primitive dictionary

**Simulation changes:**
- Add SimulationParameterChangeTracker to track uncommitted changes
- Stores list of ObjectPath for changed simulation parameters
- Persisted with simulation (survives save/load)
- Provides HasUncommittedChanges property for status indicator

### Path Matching Logic

- Dedicated, testable method to determine if a simulation parameter belongs to a compound, which was used as a building block in the simulation configuration.
  (we have compounds which are created in the simulation but are not compound building block, like unnamed metabolites etc. Changing such a parameter should e.g. not change simulation status to orange etc.)
- Logic: parameter path contains compound name as one of its elements
- Returns compound name if matched, null if no match
- Designed for extension if more sophisticated matching needed later

### Keyword Handling

- Simulation Parameter Sets store paths with `MOLECULE` keyword
- When applying Simulation Parameter Set to simulation: replace `MOLECULE` with actual compound name
- Enables portability and reuse across different compounds/projects
- **Pavel**: no need to reuse across different compounds

### Model Construction Integration

- Simulation Parameter Set values applied during simulation creation/configuration
- Happens after keyword replacement in the model construction pipeline
- For each selected Simulation Parameter Set:
  - Replace `MOLECULE` with compound name in paths
  - Find matching parameters in simulation
  - Apply values from Simulation Parameter Set
- Invalid/unresolved paths: log Warning via Notification system, continue construction
- **Pavel** should actually never happen. **Juri**: could happen, however it's maybe should even be an (explicit) error, not a warning. Similar things already do happen with the actual qualification plans (compare e.g. https://github.com/Open-Systems-Pharmacology/Rifampicin-Verapamil-DDI/issues/2 ==> https://github.com/Open-Systems-Pharmacology/QualificationRunner/issues/144)

### Parameter BuildingBlockType Behavior

- When Simulation Parameter Set is applied, affected parameters become BuildingBlockType = Compound
- Subsequent changes to these parameters follow normal compound parameter logic
- Changes trigger standard red status indicator on compound
- Commit goes through normal compound commit flow

### Commit Workflow

- Single action: "Commit simulation parameters to compounds"
- **Pavel**: Did we agree on this? I think it should be a "Compound" action. **Juri**: I think we did. Some compounds can be than just deselected in the preview dialog (s. below).
- Identifies all changed simulation parameters (from tracker)
- Groups by compound using path matching
- Dialog presents:
  - Parameters grouped by compound (compounds can be excluded via checkbox)
  - Option to create new Simulation Parameter Set (with name input) OR update existing (dropdown)
  - Same name applied across all compounds when creating new
- On confirm: creates/updates Simulation Parameter Sets, clears tracker for committed parameters
- All-or-nothing per compound (no individual parameter selection)

### Change Tracking

- SimulationParameterChangeTracker maintains list of changed parameter paths
- Commands that change simulation parameters add to tracker
- Reset parameter command removes from tracker
- Commit clears relevant entries from tracker
- Non-empty tracker = orange status indicator on simulation

### Status Indicators

- Orange/yellow indicator on Simulation when HasUncommittedChanges = true
- Distinct from red indicator (existing compound changes)
- Only on Simulation, not on Compound

### UI Components (PK-Sim)

**Compound Simulation Parameter Sets Tab:**
- New tab after Advanced Parameters
- Master-detail layout: list of Simulation Parameter Sets on left, details on right
- Left panel: Name, IsDefault indicator, Species metadata
- Right panel: metadata display, parameter grid (Path, Value, Unit, ValueOrigin)
- Editing: inline value editing, delete individual parameters, delete entire set
- Set default action
- No "create new" action (only via commit from simulation)

**Simulation Configuration:**
- When selecting compound, show Simulation Parameter Set dropdown
- Options: "None" + all available Simulation Parameter Sets from compound
- Default Simulation Parameter Set auto-selected if exists
- User can change or clear selection

**Commit Dialog:**
- Modal dialog triggered from simulation
- Shows parameters grouped by compound
- Compound-level checkboxes to include/exclude
- Radio: "Create new Simulation Parameter Set" (+ name input) OR "Update existing" (+ dropdown)
- Confirm/Cancel buttons

**Context Menu Actions:**
- Export Simulation Parameter Set (on Simulation Parameter Set in list)
- Import Simulation Parameter Set (on compound or in Simulation Parameter Sets tab)
- Set as default Simulation Parameter Set

### Export/Import

- JSON format for Simulation Parameter Set
- Export includes: Name, IsDefault, ExtendedProperties, all ParameterValues with paths
- No path validation on import (paths are abstract until applied)
- Validation happens at simulation creation time

### Command Structure

All modifications through commands for undo/redo:
- AddSimulationParameterSetToCompoundCommand
- RemoveSimulationParameterSetFromCompoundCommand
- SetDefaultSimulationParameterSetCommand
- RenameSimulationParameterSetCommand
- UpdateSimulationParameterValueInSetCommand
- RemoveSimulationParameterValueFromSetCommand
- CommitSimulationSetParametersCommand (macro command)
- TrackSimulationParameterChangeCommand / UntrackSimulationParameterChangeCommand

## Testing Decisions

### What Makes a Good Test

- Test external behavior and contracts, not implementation details
- Use meaningful test names that describe the scenario and expected outcome
- Arrange-Act-Assert structure
- Mock dependencies at boundaries, not internal collaborators
- Test edge cases: empty collections, null values, invalid paths

### Modules to Test

**Domain (OSPSuite.Core):**
- SimulationParameterSet: creation, adding/removing parameters, uniqueness by path, IsDefault behavior
- SimulationParameterSetSelections: selection storage, retrieval, clearing
- SimulationParameterSetChangeTracker: tracking, untracking, clearing, HasUncommittedChanges
- Path matching logic: compound identification from paths, edge cases

**Services (PKSim.Core):**
- ParameterSetTask: all command operations
- SimulationParameterSetCommitTask: grouping logic, Simulation Parameter Set creation/update
- SimulationParameterSetApplicationService: keyword replacement, value application, warning generation
- SimulationParameterSetExportImportTask: serialization round-trip

**Presenters (PKSim.Presentation):**
- SimulationParameterSetPresenter: loading, editing, deletion flows
- CommitSimulationParameterSetsPresenter: parameter grouping, compound exclusion, name handling
- Selection presenter: default selection, clearing, dropdown population

### Prior Art

- ParameterAlternative tests for similar domain patterns
- CompoundAlternativeTask tests for command patterns
- Snapshot mapper tests for serialization patterns
- Existing presenter tests in PKSim.Presentation.Tests

## Out of Scope

The following are explicitly **not required** for this feature:

1. **MoBi UI changes** - MoBi will be able to load and use Simulation Parameter Sets (via shared Core), but no new UI or commit workflow in MoBi
2. **Automatic filtering by Species metadata** - Species is informational only, not used for automatic filtering or validation
3. **Multiple active Simulation Parameter Sets per compound per simulation** - only one Simulation Parameter Set can be selected per compound
4. **Creating Simulation Parameter Sets directly in Compound tab** - Simulation Parameter Sets are only created through commit from simulation
5. **Individual parameter selection in commit dialog** - commit is per-compound (all or nothing for each compound)
6. **Path validation on import** - paths are validated only at simulation creation time, not during import

## Further Notes

### Serialization Considerations

- ParameterSet and related classes must be serializable for project save/load
- JSON export format should be versioned for future compatibility
- Consider snapshot mapper patterns used elsewhere in PKSim

### Migration

- Existing compounds will have empty ParameterSets collection (no migration needed)
- Existing simulations will have empty tracker and no selections (no migration needed)

### Future Considerations

- Additional metadata fields can be added via ExtendedProperties without schema changes
- Path matching logic is isolated for potential enhancement
- Export/Import foundation enables potential cloud sharing or template libraries
