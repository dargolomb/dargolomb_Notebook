---
layout: _post
title: Agisoft Metashape: Video Photo Cutting and 3D Model Building
tags: []
---

### Agisoft Metashape: Video Photo Cutting and 3D Model Building

(Recommended to save the project after each step)

**1\. Cutting Photos from Video**

• Go to **File > Import > Video**.
• Choose a folder to save the extracted images.
• Trim the video to remove unnecessary parts by setting **Cut In** and **Cut Out**.
• Set **Frame Step** to Large.

**2\. Align the Photos** (This step also call Tie Points)

• Go to **Workflow > Add Folder > Single > Add Photos**.
• Next, go to **Workflow > Align Photos**. (Accuracy: Moderate) Once the processing is complete, click the **Camera Icon** to proceed.

**3.** **Move Region**

\* organize the box on the model area.

**4\. Scale the Model**

• Add marker point **>** Right click on a specific point and 1 more point.

• Create scale bar **>** Select 2 point in the reference > Right click on the scale bar > modify- change the distance.

• Model**\>** Transform Object**\> Update Transform**

**5\. Cleaning**

Manual cleaning – go to manual selection icon and select "free form", then select the point that irrelevant and delete.

**6\. Building the Point Cloud**

• Go to **Workflow > Build Point Cloud**

Quality: Medium
Click- save project after each step
Click- Calculate point confidence
Depth filtering: Mild

(After this stage you can skip to stage 9 and build DEM- if you don’t need a nice 3D model)

**7\. Building the 3D Model (**The "Build Model" - creating a 3D representation of your object, which includes both **dense cloud generation** and **mesh creation**)

• Go to **Workflow > Build Model**.

- Source data: Point cloud.
- Face count: Moderate.

After the processing is complete, click the **Triangular Icon** to finalize the model.

**8\. Building the Texture (**the **Build Texture** process is used to **apply photographic textures** to a 3D mesh or model, giving it realistic surface details. Essentially, it wraps your 3D model in high-resolution imagery to make it look more lifelike and visually accurate)

• Go to **Workflow > Build Texture**.

- - Texture type: Diffuse map
    - Source data: images
    - Mapping mode: Generic
    - Blending mode: mosaic
    - Texture size: 8192

After the processing is complete, click the small arrow next to the **Triangular Icon** and select **TEXTURED**.

**9\. Building the DEM** (Digital Elevation Model**\-** represents the elevation of the terrain. It is created from the **dense point cloud** or **mesh)**

• Go to **Workflow > Build DEM**.

**10\. Building the Orthomosaic (**is a type of aerial photograph that has been geometrically corrected so that the scale of the image is uniform across the entire image. In simpler terms, it’s a **map-like** image where the distortions from the camera angle or topography have been removed, making it a "true" representation of the earth's surface)

• Go to **Workflow > Build Orthomosaic**.

- Set **Pixel Size** to **0.0005x 0.0005y**.

**11\. Exporting Results**

- Go to **File > Export > Export Orthomosaic**.
- Choose **JPEG** (with **Tiff: None**).
    • **Export DEM**:
- Go to **File > Export > Export DEM**.
- Choose **Tiff**.

**ArcGIS analyze DEM for rugosity**

ADD data🡪 import DEM file

Catalog🡪 System Toolboxes🡪Spatial Analyst Tool🡪Neighborhood🡪Focal Statistics

Focal Statistics: Import raster- DEM file (Do this step 3 time for: Min, Max and Mean) (Mukherjee et al 2020)

Catalog🡪 System Toolboxes🡪Spatial Analyst Tool🡪Map Algebra🡪Raster Calculator

Raster Calculator: (mean-min)/(max-min)

Right click on TRI Layer🡪 Symbology🡪Classifed🡪Export as Raster

Catalog🡪Raster to polygon: import the raster

OR Raster to point
