# QGIS Workflow Guide

This guide outlines a basic workflow in QGIS for processing and visualizing DEM files.

---

## Steps

### 1. Load DEM File
- Drag a DEM file into the QGIS workspace.

### 2. Adjust DEM Visualization
- Right-click on the DEM layer → **Properties** → **Symbology**.
- Set:
  - **Render Type**: `Singleband Pseudocolor`
  - **Color Ramp**: `Turbo`
- Click **Apply** and **OK**.

### 3. Generate Slope Raster
- Go to **Raster** → **Analysis** → **Slope**.

### 4. Adjust Slope Layer Transparency
- Right-click on the **Slope** layer → **Properties** → **Transparency**.
- Set **Global Transparency** to `50%`.

### 5. Create a New Print Layout
- Go to **Project** → **New Print Layout**.

In the layout window:
- Click **Add Map** to insert the map canvas.
- Click **Add Label** to add descriptive text.
- Click **Add Legend** for map elements.
- Click **Add Graph** if needed (optional).

### 6. Export
- Export the layout as a `.jpg` file via the **Layout** → **Export as Image** option.
- Save the image in your desired location.

---

## Notes
- Ensure the DEM and slope layers are correctly aligned in the layer panel for clear visualization.
- The `Turbo` color ramp is suitable for topographic contrast but can be changed based on preference.
