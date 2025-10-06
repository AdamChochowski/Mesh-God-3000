# CatBorg Studio | Mesh God 3000 – MeshGod Operations Documentation

This document lists all available MeshGod operations, sorted by OperationType.

## Mesh (MeshGod3000.OperationType) - Mesh Delete

Deletes only the selected triangles from a mesh while keeping the rest intact. The tool updates the mesh and any associated MeshColliders automatically, and it fully supports Undo. Useful for removing specific parts of a mesh, cleaning up geometry, or separating sub-meshes without affecting the rest of the model.

---

## Mesh (MeshGod3000.OperationType) - Mesh Move

Lets you move only the selected triangles of a mesh using handles in the Scene view. It keeps the rest of the mesh unchanged, so you can adjust parts of your model without breaking it. The tool automatically calculates the center of the selection, updates the mesh, and fixes MeshColliders if needed. Undo is fully supported. Useful for repositioning parts of a mesh, aligning details, or adjusting vertices easily.

---

## Mesh (MeshGod3000.OperationType) - Mesh Rotate

Lets you rotate only the selected triangles of a mesh around a pivot using handles in the Scene view. The rest of the mesh stays unchanged, so you can adjust parts of your model without breaking it. The tool automatically calculates the pivot from the selected triangles, updates the mesh, and fixes MeshColliders if needed. Undo is fully supported. Useful for rotating mesh details, aligning sub-meshes, or adjusting vertex orientation easily.

---

## Mesh (MeshGod3000.OperationType) - Mesh Scale

Rotate only the selected triangles of a mesh around a pivot using handles in the Scene view. The rest of the mesh stays unchanged, allowing you to adjust parts of your model without breaking it. The tool automatically calculates the pivot from the selected triangles, updates the mesh, and fixes MeshColliders if needed. Undo is fully supported. Useful for rotating mesh details, aligning sub-meshes, or adjusting vertex orientation easily.

---

## Origin (MeshGod3000.OperationType) - Pivot Bottom

Moves the pivot point of the active mesh to the bottom-center of the model, based on the lowest point in world space rather than local orientation. This operation ignores the current selection and always aligns the pivot to the true world “bottom,” making it useful for placing objects on the ground, aligning models in a scene, and preparing assets for snapping or physics interactions.

---

## Origin (MeshGod3000.OperationType) - Pivot Center of Mass

Moves the pivot point of the selected mesh to its geometric center. Useful for symmetrical object placement, precise rotations, and balancing models within the scene.

---

## Origin (MeshGod3000.OperationType) - Pivot Set

Enables interactive pivot editing by displaying handles that let you drag and reposition the pivot point directly in the scene view. This gives you precise, manual control over pivot placement, making it useful for fine-tuning alignment, snapping, or custom pivot setups beyond automatic operations.

---

## Origin (MeshGod3000.OperationType) - Pivot To Selection

Moves the pivot point of the mesh to the average center of the currently selected triangles. Ideal for fine-tuning pivot placement based on specific mesh areas or modeling focus zones. 

---

## Other (MeshGod3000.OperationType) - Orientation Set

Enables interactive orientation editing by displaying rotation handles that let you adjust the mesh’s orientation in space without rotating its geometry. This is useful for correcting alignment, standardizing model rotations, or preparing assets for consistent placement and snapping in a scene.

---

## Other (MeshGod3000.OperationType) - Save As Mesh

Saves the selected mesh as a .asset file inside the project’s MeshGod3000/Saved Files/Mesh folder. Automatically creates a unique asset name and updates the MeshFilter to use the saved mesh. Useful for preserving mesh edits within the Unity project. 

---

## Other (MeshGod3000.OperationType) - Save All As FBX

Exports all mesh objects in the selected GameObject's hierarchy as individual FBX files into the project’s MeshGod3000/Saved Files/FBX folder. Each mesh is saved as a standalone FBX file, with '*' removed from GameObject names for filenames and in the scene. Useful for saving multiple edited meshes for use in other scenes, projects, or external tools like Blender or Maya. Requires: UnityEditor.Formats.Fbx.Exporter, and the FBX Exporter package installed via Unity Package Manager.  

---

## Other (MeshGod3000.OperationType) - Save All As Mesh

Saves all meshes in the selected GameObject's hierarchy as individual .asset files inside the project’s MeshGod3000/Saved Files/Mesh folder. Each mesh is saved with a unique asset name, with '*' removed from GameObject names for filenames and in the scene. Updates each MeshFilter to use its respective saved mesh. Useful for preserving multiple mesh edits within the Unity project.  

---

## Other (MeshGod3000.OperationType) - Save As FBX

Exports the selected mesh object as a standalone FBX file into the project’s MeshGod3000/Saved Files/FBX folder. Useful for saving edited meshes for use in other scenes, projects, or external tools like Blender or Maya. Requires: UnityEditor.Formats.Fbx.Exporter, and the FBX Exporter package installed via Unity Package Manager. 

---

## Select (MeshGod3000.OperationType) - Deselect Linked

Flood-fills all triangles linked to the triangle nearest the mouse cursor, then inverts their selection. For best results, keep the cursor above the mesh in the Scene view and use the shortcut to trigger the operation.

---

## Select (MeshGod3000.OperationType) - Select All

Selects all triangles of the current mesh. Useful for applying operations to the entire mesh at once.

---

## Select (MeshGod3000.OperationType) - Invert

Inverts the current selection of triangles on the mesh. Useful for quickly switching between selected and unselected areas.

---

## Select (MeshGod3000.OperationType) - Less

Inverts the current selection of triangles on the mesh. Useful for quickly switching between selected and unselected areas.

---

## Select (MeshGod3000.OperationType) - Linked

Selects all triangles connected to the triangle nearest to the mouse cursor, expanding the selection to linked geometry. For best results, keep the cursor above the mesh in the Scene view and use the shortcut to trigger the selection.

---

## Select (MeshGod3000.OperationType) - More

Expands the current selection by adding all triangles that share vertices with the already selected triangles. This grows the selection outward, including connected triangles to help you select larger contiguous mesh areas quickly.

---

## Select (MeshGod3000.OperationType) - None

Clears selection of the current mesh.

---

## Separate (MeshGod3000.OperationType) - Separate By Loose Parts

Splits the selected triangles of a mesh into multiple new objects based on disconnected (loose) parts. Each loose part becomes a separate GameObject, while the original mesh is updated with one part. Useful for breaking complex meshes into logical sub-meshes for easier editing or optimization. 

---

## Separate (MeshGod3000.OperationType) - Separate Selected

Creates a new mesh object from the currently selected triangles, separating them from the original mesh. The original mesh is updated to exclude the separated triangles, and the new object inherits the original’s transform and materials. Useful for splitting parts of a mesh into distinct objects for editing or organization. 

---

