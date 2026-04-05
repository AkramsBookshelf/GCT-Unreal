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
      
![View mode Unlit](imgs/modeling/gct-unlit-level.png)

5.  Save this level with the name **Empty**

> [!NOTE]
> This empty level will be used as a staging area for creating models inside of Unreal. 

#

### Step 2 — Enable Modeling Mode
1.  Top-left mode dropdown
2.  Select **Modeling Mode**
    - OR press **SHIFT + 5**
      
![Modeling Mode](imgs/modeling/gct_modeling_mode.png)
#

### Step 3 — Create Base Wall Shape
1.  From the Modeling tool bar on the left side, select **Create**
2.  Then select **Box** 
3.  In the **Create Box** dialog, set the following: 
    - Width = 12.5
    - Depth = 100
    - Height = 12.5
    - Target Position = At Origin
      
![Create Box](imgs/modeling/gct-create-box.png)

4. At the bottom of the **Viewport** press **Accept** to acept the box model

![Accept Box](imgs/modeling/gct-accept-box.png)

#

### Step 4 — Rename Static Mesh
1. In the **Content Browser** navigate to the `_GENERATED > Username` folder
2. Find the **Box** static mesh and rename it to `SM_Wall`

> [!NOTE]
> Models created in Unreal Engine will be placed in the content folder inside a folder named `_GENERATED` and inside a subfolder with your_username_. The object will be named by the primitive type (in this case, _Box_) followed by an ID number. This can be renamed at any time.
>

3. In the **Outliner** select the **Box** instance of the static mesh
4. Rename this to `SM_Wall` as well.

#

### Step 5 — Extruding Faces
1. From the top menu, choose the `Select Mesh PolyGroups` setting
   - This will allow us to select the polygon faces on the box.

  ![Select Mesh](imgs/modeling/gct-select-mesh-polygroup.png)
    
2. In the **Viewport**, select the front face along the **Y axis** of the _wall_

  ![Select front face](imgs/modeling/gct-select-front-face.png)
  
3. From the Modeling toolbar on the left side, choose **Select**
4. Then choose **Extrude**

  ![Extrude](imgs/modeling/gct-select-extrude.png)
  
5. In the **Viewport** locate the **Transform box**
6. Turn **Delta Mode** OFF
7. Enter **6.25** in the **Y axis** to extrude out that distance.
8. Click **Accept**

  ![Extrude Front](imgs/modeling/gct-extrude-Y-axis.png)
  
9. Rotate around to the other side of the wall and select the back face
10. Choose **Extrude** again
11. Enter **-6.25** in the **Y axis** to extrude in the opisite direction.
12. Click **Accept**

  ![Extrude Back](imgs/modeling/gct-extrude-Y-axis-opisite.png)

13. Repeat steps 7 through 12 again, extruding another **6.26** and **-6.25** on both sides.

  ![Wall base exturded](imgs/modeling/gct-wall-base-extruded.png)
#

### Step 6 — Extruding the Wall Top Faces
1. Select the inner three faces on the top of the wall base
2. Then choose **Extrude**
3. Extrude up by entering **6.25** in the **Z axis**
4. Choose **Accept**

![Extrude base up ](imgs/modeling/gct-extrude-top.png)

5. Select the innermost top face and choose **Extrude** again
6. Enter **300** in the **Z axis** to extrude up.
7. Choose **Accept**

![Extrude wall ](imgs/modeling/gct-extrude-center-top.png)

8. Select the top face again, and **Extrude** in the **Z axis** at **3.125**
9. Choose **Accept**

![Extrude top](imgs/modeling/gct-extrude-center-top-cap.png)

10. Repeat Steps 8 and 9 one more time.


#

### Step 7 — Extrude Front Faces for Detail
1. Select the **front faces of the top two sections** of the wall
   - **Exturde** in the **Y axis** at **6.25**
   - Choose **Accept**
2. Select the **back faces of the top two sections** of the wall
   - **Exturde** in the **Y axis** at **-6.25**
   - Choose **Accept**
![Extrude top sides](imgs/modeling/gct-wall-top.png)

3. Select the **very top front face** only
  - **Exturde** in the **Y axis** at **6.25**
  - Choose **Accept**
4. Select the **very top Back face** only
  - **Exturde** in the **Y axis** at **-6.25**
  - Choose **Accept**

  ![Extrude top final cap](imgs/modeling/gct-wall-top-cap.png)

You now have the top cap of the wall completed.

 #

 ### Step 8 — Create Wall Blueprint
 1. In the **Content Browser** create a new folder named **Blueprints**
 2. In the **Outliner** select the **SM_Wall**
 3. In the Top toolbar, click on the **BluePrints** tool
 4. From the dropdown, choose **Convert Selection to Blueprint Class**

 ![Convert to Blueprint](imgs/modeling/gct-convert-blueprint.png)
 
 5. In the Blueprint dialog
    - Set the **Creation Method** to **New Subclass**
    -  Name the class to **BP_Wall**
    -  Set the path to the **BluePrints** folder
    -  Click **Select**
    
![Blueprint selection](imgs/modeling/gct-create-selection-blueprint.png)
    
6. The Blueprint dialog will open.
7. Press save to save the **BP_Wall** settings and close the dialog
8. Back in the **Outliner** select the **BP_Wall**
9. Repeat steps 3-5, naming the new blueprint **BP_WallX3**
10. In the Blueprint dialog, copy and paste the static mesh
11. Move the copy mesh over **100** units in the **X axis**.
12. Paste another copy of the wall mesh, and move it over **-100** units in the **X axis**.
13. Save the Blueprints and close the dialog

![Blueprint selection](imgs/modeling/gct-blueprint-wall3.png)



### Step 9 — Place Walls in the Park
1. In the **Empty** level you can now delete your **Wall** object from the **outliner**
   - This keeps the empty level, empty
> [!NOTE]
> The Wall model is still tied to your static mesh in the `_GENERATED` folder, so do not worry about deleting it.
>
2. From the **Content Browser** open **Level_01**
3. Change the view mode back to **Lit** (`ALT+4`) 
4. In the **Outliner** under the **Enviorment** folder add a new sub-folder name **Park Walls**
5. From the **Content Browser** drag and drop the **BP_WallX3** static mesh into the level.
6. Use the **BP_WallX3** to create the main boundaries of the park.
    -   For small gaps, use the single **BP_Wall** to fill in.
7.  Add wall segments to divide the park into at least **two sections**.
8.  Leave a **3-meter opening** between the sections.
    -   We will add a gate here in the next tutorial.

#

### Step 10 — Save & Commit
1.  Save your scene: **File > Save** or **Ctrl + S**.
2.  Close Unreal.
3.  Switch to **GitHub Desktop** → stage your changes.
4.  Commit with the message:
    -   `feat: created Wall Blueprint.`
5.  Push your changes to the remote branch: `SceneBuilding`.


        
---

# 🎯 CHALLENGE: Recreate the Park Gate in Unreal

Now that you’ve learned the basics of **Modeling Mode in Unreal Engine**, it’s time to apply those skills independently.

In game development, it’s very common to switch tools and engines. For example, a **Unity developer may be hired to work in Unreal Engine**. Employers value developers who can:

-   **Adapt quickly**
-   **Apply prior knowledge to new tools**
-   **Problem-solve without step-by-step instructions**

This challenge is designed to build that skill.

## 🧠 The Task

Use the **[Unity ProBuilder Gate Tutorial](https://github.com/AkramsBookshelf/GCT-Unity/blob/main/UnityEssentials/ProBuilder.md#%EF%B8%8F-tutorial-create-the-park-gate-with-probuilder)** to recreate the **Park Gate in Unreal Engine**.

👉 You are **not** given step-by-step Unreal instructions this time.

Instead, your goal is to:

-   **Translate the process**
-   **Apply equivalent tools in Unreal**
-   **Problem-solve when things don’t match exactly**

## 🔁 What You Should Recognize

Even though the tools are different, the **core concepts are the same**:

-   Creating a base shape
-   Extruding faces
-   Adding detail through subdivision and repetition
-   Building a modular structure
-   Creating a reusable asset (Blueprint)

👉 _The workflow is different, but the thinking is the same._

## ⚠️ Important Reminders

Before you begin, keep the following in mind:

### 📏 Units

-   Unreal uses **centimeters**
-   Multiply all Unity values by **100**

### 🔄 Axis Differences

-   Unity uses **Y as up**
-   Unreal uses **Z as up**

👉 This means:

-   Height → **Z axis in Unreal**
-   Depth → **X axis in Unreal**

### 🧱 Prefabs vs Blueprints

-   Unity **Prefabs** = Unreal **Blueprints**
-   You will need to convert your final gate into a **Blueprint Actor**

### ⚒️ Modeling Behavior

-   You will need to **extrude front and back faces separately**
-   This ensures correct extrusion direction:
    -   One goes **positive**
    -   One goes **negative**

If you extrude both at once, the geometry may not behave as expected.

## 🧪 Suggested Approach

To help guide your thinking:

1.  Start in an **empty level**
2.  Create a **base cube**
3.  Build the **vertical gate post first**
4.  Add **front details**
5.  Construct the **horizontal rails**
6.  Use **subdivide + extrude** for panel details
7.  Finish with **decorative elements (finials)**
8.  Convert to a **Static Mesh**
9.  Create a **Blueprint** for the full gate

## 🎯 Goal

By the end of this challenge, you should have:

-   A **fully modeled gate in Unreal**
-   A **Blueprint version of the gate**
-   A deeper understanding of how to **transfer skills between engines**

**You will be graded on your ability to problem-solve and to apply logic.**

Remember that the internet is a good resource, AI is helpful but not always correct. 

## 💡 Mindset Reminder

> \[!TIP\]  
> You are not learning _Unreal_ or _Unity_—  
> you are learning **how to think like a game developer**.
> 
> Tools will change.  
> Your ability to **adapt and solve problems** is what matters most.
