
2024-07-28 15:37

Status:

Tags: #UOM #L2S2-S4 #Graphic-Design 



# Traditional Graphic Pipeline

*Which is fundamental concepts of in computer graphics, The graphic pipeline is a sequence of interconnected stages that transform 3D data in to meaning full 2D images for display.*

1. **Transformation**:
    - **Input**: 3D vertices (points), normal (surface orientations), and triangles (geometric primitives).
    - **Purpose**: Transform these 3D coordinates into 2D screen space (pixel coordinates).
    - **Operations**: Apply transformations like translation, rotation, scaling, and projection.
    - **Result**: Transformed vertices ready for further processing.

2. **Lighting**:
    - **Input**: Transformed vertices.
    - **Purpose**: Calculate how light interacts with surfaces.
    - **Operations**: Apply lighting models (e.g., Phong, Lambertian) to determine shading, highlights, and shadows.
    - **Result**: Shaded surfaces based on lighting conditions.

3. **Clipping**:
    - **Input**: Shaded surfaces.
    - **Purpose**: Remove portions of objects outside the view frustum (visible area).
    - **Operations**: Clip polygons to fit within the frustum.
    - **Result**: Clipped polygons ready for rasterization.

4. **Scan Conversion (Rasterization)**:
    - **Input**: Clipped polygons.
    - **Purpose**: Convert geometric primitives (triangles, lines) into individual pixels.
    - **Operations**: Determine which pixels are part of each primitive.
    - **Result**: Pixel fragments representing the scene.

5. **Pixel Processing**:
    - **Input**: Pixel fragments.
    - **Purpose**: Finalize pixel values for display.
    - **Operations**:
        - Texture mapping: Apply textures to surfaces.
        - Z-buffering: Handle depth information for occlusion.
        - Alpha blending: Combine transparent objects.
        - Antialiasing: Reduce jagged edges.
    - **Result**: Ready-to-display pixels.


# Reference

![[Graphic Systems graphic pipeline.png | 800]]