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

