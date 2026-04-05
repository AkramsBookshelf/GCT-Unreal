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
3.  In the top toolbar, set the **View Mode** to **Unlit**
    - Shortcut for **Unlit** mode is `ALT + 3`
5.  Save this level with the name **Empty**

> [!NOTE]
> This empty level will be used as a staging area for creating models inside of Unreal. 

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
4. At the bottom of the **Viewport** press **Accept** to acept the box model
#

### Step 4 — Rename Static Mesh
1. In the **Content Browser** navigate to the `_GENERATED > Username` folder
2. Find the **Box** static mesh and rename it to `SM_Wall`

> [!NOTE]
> Models created in Unreal Engine will be placed in the content folder inside a folder named `_GENERATED` and inside a subfolder with your_username_. The object will be named by the type of primitive (in this case, _Box_) followed by an ID number. This can be renamed at any time.
>

3. In the **Outliner** select the **Box** instance of the static mesh
4. Rename this to `SM_Wall` as well.

#

### Step 5 — Extruding Faces
1. From the top menu, choose the `Select Mesh PolyGroups` setting
   - This will allow us to select the polygon faces on the box.
2. In the **Viewport**, select the front face along the **Y axis** of the _wall_
3. From the Modeling toolbar on the left side, choose **Select**
4. Then choose **Extrude**
5. In the **Viewport** locate the **Transform box**
6. Turn **Delta Mode** OFF
7. Enter **6.25** in the **Y axis** to extrude out that distance.
8. Click **Accept**
9. Rotate around to the other side of the wall and select the back face
10. Choose **Extrude** again
11. Enter **-6.25** in the **Y axis** to extrude in the opisite direction.
12. Click **Accept**
13. Repeat steps 7 through 12 again, extruding another **6.26** and **-6.25** on both sides.
#

### Step 6 — Extruding the Wall Top Faces
1. Select the inner three faces on the top of the wall base
2. Then choose **Extrude**
3. Extrude up by entering **6.25** in the **Z axis**
4. Choose **Accept**
5. Select the innermost top face and choose **Extrude** again
6. Enter **300** in the **Z axis** to extrude up.
7. Choose **Accept**
8. Select the top face again, and **Extrude** in the **Z axis** at **3.125**
9. Choose **Accept**
10. Repeat Steps 8 and 9 one more time.
#

### Step 7 — Extrude Front Faces for Detail
1. Select the **front faces of the top two sections** of the wall
   - **Exturde** in the **Y axis** at **6.25**
   - Choose **Accept**
2. Select the **back faces of the top two sections** of the wall
   - **Exturde** in the **Y axis** at **-6.25**
   - Choose **Accept**
3. Select the **very top front face** only
  - **Exturde** in the **Y axis** at **6.25**
  - Choose **Accept**
4. Select the **very top Back face** only
  - **Exturde** in the **Y axis** at **-6.25**
  - Choose **Accept**

You now have the top cap of the wall completed.

 #

 ### Step 8 — Create Wall Blueprint
 1. In the **Content Browser** create a new folder named **Blueprints**
 2. In the **Outliner** select the **SM_Wall**
 3. In the Top toolbar, click on the **BluePrints** tool
 4. From the dropdown, choose **Convert Selection to Blueprint Class**
 5. In the Blueprint dialog
    - Set the **Creation Method** to **New Subclass**
    -  Name the class to **BP_Wall**
    -  Set the path to the **BluePrints** folder
    -  Click **Select**
6. Close the 



### Step 8 — Return to Level_01
1. In the **Empty** level you can now delete your **Wall** object from the **outliner**
   - This keeps the empty level, empty
> [!NOTE]
> The Wall model is still tied to your static mesh in the `_GENERATED` folder, so do not worry about deleting it.
>
2. From the **Content Browser** open **Level_01**
3. In the **Outliner** under the **Enviorment** folder add a new sub-folder name **Park Walls**
4. From the **Content Browser** drag and drop the **Wall** static mesh into the level. 
