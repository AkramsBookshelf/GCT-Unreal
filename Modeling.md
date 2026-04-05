# 📜 Unreal Engine Modeling (Modeling Mode)

> By: Akram Taghavi-Burris | © 2026

In most game projects, **3D models are created outside of Unreal Engine**, using programs like Blender, Maya, or 3ds Max. These tools provide full control but take time to complete.

During early **level design**, you often need to **prototype environments quickly**, before final models are ready. Unreal provides basic geometry tools for blocking out levels, but they are limited when creating more complex structures.

This is where **Modeling Mode** comes in.

--- 

# ⚒️ Tutorial: Create the Park Wall in Unreal

### Step 1 — Open a Clean Level
1.  Open your project
2.  Create/Open an **Empty Level**

#

### Step 2 — Enable Modeling Mode
1.  Top-left mode dropdown
2.  Select **Modeling Mode**
    - OR press **SHIFT + 5** 

#

### Step 3 — Create Base Wall Shape
1.  From the Modeling tool bar on the left side, select **Create**
2.  Then select **Box** 
3.  In the **Create Box** dialog, set the following: 
    - Width = 12.5
    - Depth = 100
    - Height = 12.5
    - Target Position = At Origin
4. At the bottom of the **Viewport** press **Accept to acept the box model
#

### Step 4 — Rename Static Mesh
1. In the **Content Browser** navigate to the `_GENERATED > Username` folder
2. Find the **Box** static mesh and rename it to `Wall`

> [!NOTE]
> Models created in Unreal Engine will be placed in the content folder inside a folder named `_GENERATED` and inside a subfolder with your_username_. The object will be named by the type of primitive (in this case, _Box_) followed by an ID number. This can be renamed at any time.
>

3. In the **Outliner** select the **Box** instance of the static mesh
4. Rename this to `Wall` as well. 
