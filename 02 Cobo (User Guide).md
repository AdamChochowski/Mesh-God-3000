# CatBorg Studio | Mesh God 3000 – Combo (User Guide)

## What is a Combo?
A **Combo** is a custom asset that runs several Mesh God operations in sequence as a single instant action. Combos let you automate common multi-step edits (for example: delete unwanted faces → separate selection → save mesh) and run them with one click. Only **instant** operations are executed — interactive/persistent tools (Move, Rotate, Scale, etc.) are skipped.

---

## Create a Combo (step-by-step)

1. Open Unity and go to **MeshGod3000 → Resources → MeshOperations**.  
2. Find an existing combo asset (default assets: **Combo A**, **Combo B**).  
3. Right-click the combo you want and choose **Duplicate** (or select it and press `Ctrl+D` / `Cmd+D`).  
4. Rename the duplicated asset to your desired combo name (e.g. `CleanupAndSave`).  
5. Select the new combo asset to open it in the **Inspector** — it appears automatically after duplicating.  
6. In the Inspector, add operations to the `MeshGodOperations` list by dragging existing MeshGod operation assets into the list or using the object picker.  
   - Order matters: operations are executed from top → bottom.  
7. Save your project (Ctrl/Cmd+S) to persist the new combo asset.

---

## Execute a Combo

1. In the **Scene** or **Hierarchy**, select the GameObject that contains the mesh you want to operate on (this will be the initial target).  
2. Run the combo from your Mesh God UI or by executing the combo asset (how it’s exposed in your editor window).  
3. The combo will process its assigned operations in order.  
   - For each operation the combo will update the active target as it goes.  
   - If an operation produces new GameObjects (for example, `Separate Selected`), those objects can be used by the next operation in the chain.  
4. When finished, the combo restores the original active target and collapses the Undo group so the whole combo is a single undoable step.

---

## Important Rules & Notes

- **Only instant operations run.** Interactive/persistent tools (Move, Rotate, Scale, Orientation Set, Pivot Set, etc.) are skipped automatically.  
- **Undo is grouped.** The combo runs inside a single Undo group — one Undo will roll back the entire combo.  
- **Nulls are skipped.** If the combo contains `null` entries or missing assets, those steps are logged and skipped.  
- **Per-object flow:** Combos start with the currently selected GameObject. If an operation creates new objects and returns them, the next operation will run on those objects (if provided).  
- **No scene changes without selection:** If no active mesh is selected when you run the combo, it will abort and log a warning.

---

## Example Combo: `QuickCleanup`
_Example sequence to remove unwanted faces, separate selection, then save the result:_

1. `Select` (user selection step)  
2. `Mesh Delete` (instant)  
3. `Separate Selected` (instant)  
4. `Save Mesh` (instant)  

After creating this combo, duplicating it and applying it will run steps 2–4 automatically for the selected GameObject.

---

## Best Practices

- **Build combos from tested single operations.** Make sure each operation works standalone before chaining it.  
- **Keep order logical.** For example, `Delete` before `Save` if you want the saved result to reflect removal of triangles.  
- **Name combos clearly.** Use descriptive names like `TrimAndExport_FBX` so teammates know what the combo does.  
- **Test on a copy.** When designing a new combo, test it on a duplicate GameObject or a simple mesh to avoid accidental scene damage.  

---

## Troubleshooting

- **Combo does nothing / aborts:** Ensure you have an active mesh selected in the Hierarchy before running.  
- **An operation in the combo failed:** Check the Console for warnings. The combo will skip null operations and continue.  
- **Result isn’t what you expected:** Re-run individual operations manually to isolate the failing step, then fix the sequence or operation settings.  
- **New objects not used by next operation:** Make sure the preceding operation actually returns newly created GameObjects (some operations update the original mesh instead).

---