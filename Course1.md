# Course 1, Session 1: Importing Simple and Complex 3D Assets

## Objective
- Learn to import and organize 3D assets in Unity.
- Resolve material and scaling issues.
- Apply animations and scripts.

## Key Concepts
- **Prefab**: A reusable, preconfigured GameObject stored as an asset in Unity.
- **BlendShapeDriver**: A Unity script used to drive BlendShape animations for 3D models.
- **Materials**: Define how 3D objects appear, including textures, shaders, and transparency settings.

## Practical Steps

### 1. Examine the Project Structure
- Import the provided package via the **Package Manager**.
- Organize assets properly:
  - Store **materials** in a `Materials` folder.
  - Place **textures** inside a `Textures` subfolder.
  - Keep **scripts** in a `Scripts` directory.
  - Store **animation clips** in an `Animation` folder.

### 2. Import 3D Assets and Fix Material Issues
- Drag assets (`Racer`, `Regina`) into the **Scene**.
- Check for **mesh/material issues**.
- **Extract & reassign materials**:
  - Select the object.
  - In the **Inspector**, go to *Import Settings > Materials*.
  - Click **Extract Materials** and store them in the appropriate folder.
  - Select each material and verify its **Surface Type** (set to "Opaque" if needed).
- **Resolve rendering pipeline issues**:
  - If materials appear **bright pink**, go to:
    `Edit > Render Pipeline > [Current Pipeline] > Upgrade Selected Materials`.

### 3. Fix Scaling Issues
- Adjust the **Transform Scale** in Import Settings:
  - Set `"Racer"` scale to **0.9**.
  - Set `"Regina"` scale to **0.45**.

### 4. Apply Animations
- Locate **Animation Controllers** in the `Animation` folder.
- Drag **Racer's Animation Controller** onto the Racer model in the **Scene**.
- Drag **Regina's Animation Controller** onto Regina.
- Click **Play** to test animations.

### 5. Apply BlendShapes
- Find the `Scripts` folder.
- Drag the **BlendShapeDriver** script onto Regina.
- In the **Inspector**, add the following BlendShapes:
  - `Body`
  - `Default`
  - `Eyes`
  - `Hair`
- Click the **slider icon** at the top-right of the Inspector to save import settings as a preset.

---

## Best Practices & Tips
✅ Keep your **folder structure clean** for easy navigation.  
✅ Extract and manually assign **materials** when import issues arise.  
✅ Always check **shader compatibility** with your rendering pipeline.  

---

## Troubleshooting

| Issue | Solution |
|--------|----------|
| **Warped meshes** | Extract and reassign materials to resolve shader issues. |
| **Bright pink materials** | Upgrade materials for the correct render pipeline (`Edit > Render Pipeline`). |
| **Scaling issues** | Adjust scale values in Import Settings. |
| **Animations not playing** | Ensure Animation Controllers are properly assigned. |

---

## Reference: Unity Documentation on Asset Importing

### Importing 3D Models into Unity
Unity supports importing **3D models** from external applications like Blender, Maya, and 3ds Max. When importing models, Unity automatically generates:
- **Meshes**
- **Materials**
- **Textures**
- **Animations**

**Steps to Import a 3D Model:**
1. Drag the model file (`.fbx`, `.obj`, `.dae`, etc.) into Unity’s **Assets** folder.
2. Select the model in the Project window.
3. In the **Inspector**, configure:
   - **Scale Factor**: Adjust based on model size.
   - **Import Materials**: Enable or disable automatic material import.
   - **Animation Settings**: Enable if the model includes animations.

For more details, see: [Unity 3D Model Importing Guide](https://docs.unity3d.com/Manual/3D-formats.html).

### Fixing Material Import Issues
When importing models, Unity may fail to assign materials correctly.  
To fix this:
1. Select the imported model.
2. In the **Inspector**, go to *Materials*.
3. Click **Extract Materials** and assign them manually.
4. Ensure all shaders match the **Render Pipeline**.

For more details, see: [Unity Material Import Troubleshooting](https://docs.unity3d.com/Manual/MaterialsAccessingViaScript.html).

---



# Course 1, Session 2: Optimization with Level of Detail (LOD)

## Objective
- Use Level of Detail (LOD) groups to optimize project performance.

## Key Concepts
- **LOD (Level of Detail)**: A technique that adjusts the complexity of 3D models based on their distance from the camera to optimize rendering.
- **LOD Group**: A Unity component that manages multiple LOD levels for a GameObject.

## Practical Steps

### 1. Prepare Models for LODs
- Optionally create your own model or use the provided **"Monstera_LOD_New"** from:  
  `Assets > CharacterPackage > Course1Session2_LODs`.

### 2. Set Up LOD Groups
- Add an **LOD Group** component to your object.
- Configure LOD levels (e.g., LOD0 for high detail, LOD1 for lower detail).
- Adjust **camera render values** to determine when each LOD is active.

### 3. Consistent Naming
- Name LOD objects systematically for proper organization:
  - `Object_LOD0` (highest detail)
  - `Object_LOD1`
  - `Object_LOD2` (lowest detail)

## Best Practices & Tips
- Organize LODs in a **clear hierarchy**.
- **Test LOD transitions** by simulating different camera distances.
- Keep LOD level **poly-count reductions proportional** to ensure a smooth transition.

## Troubleshooting
| Issue | Solution |
|--------|----------|
| **LOD not rendering properly** | Ensure object names match the LOD Group configuration. |
| **LOD switching too soon or too late** | Adjust **LOD thresholds** in the LOD Group component. |
| **LOD1 or LOD2 is missing** | Make sure the GameObject for each LOD exists and is referenced correctly. |

---

## Reference: Unity Documentation on LOD

### Configure Mesh LOD
To configure LOD, you must have a **GameObject** with an **LOD Group** component.  
The **LOD Group** component provides controls to define how LOD behaves on this GameObject, and references the GameObjects that Unity shows or hides for each LOD level.

You can set up LOD in Unity in two ways:

1. **Automatic LOD Import**  
   - Configure LOD levels in an external **3D modeling application**.  
   - Unity will automatically create and configure the required GameObjects and components.
   - See *Importing LOD Meshes* for correct configuration.

2. **Manual LOD Setup**  
   - Create a **GameObject** in Unity and add an **LOD Group** component.
   - Manually configure the LOD levels by assigning different models to each LOD slot.

For full details, visit: [Unity LOD Documentation](https://docs.unity3d.com/Manual/LevelOfDetail.html).

---

