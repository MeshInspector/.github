![MeshInspector/MeshLib](http://meshinspector.com/wp-content/uploads/2024/03/3D-mesh-processing-library.png)
# Welcome to MeshInspector
 MeshInspector is a versatile software designed for fast mesh repair, transforming 3D scans into solid models, and facilitating quality inspection. This all-in-one tool offers a modern, intuitive interface, ensuring efficient 3D data handling. It's lightning-fast, supports all platforms, and is browser-accessible. The MeshInspector supports 3D data types, like meshes, point clouds, CT scans, voxel data, distance maps, and polylines.

MeshInspector can be applied to 3D printing, scan to as-built models conversion GIS&BIM, digital dentistry, CT/ MRI scans to mesh transformation, and scan/CAD compare.

MeshInspector is built upon the robust open-source 3D mesh processing library MeshLib SDK. It is free from legacy code and is created using optimized and fast algorithms, which help achieve up to 2x faster data processing performance.

 - [MeshLib](#meshlib) 3d mesh processing library
 - [MeshInspector](#meshinspector) 3d processing software, powered by MeshLib

# Useful links
[MeshInspector website](https://meshinspector.com/)

[MeshInspector web-browser version](https://meshinspector.com/)

[Download MeshInspector (Windows/Linux/Mac)](https://meshinspector.com/download/)

[MeshLib website](https://meshlib.meshinspector.com/)

[MeshLib Documentation](https://doc.meshinspector.com/)

[Submit an issue](https://meshinspector.github.io/ReportIssue/)

# MeshLib
[MeshLib](https://github.com/MeshInspector/MeshLib) is an Open-source 3D geometry library that enables you to seamlessly create powerful 3D applications and perform advanced operations with ease using either C++ or Python.

When designing MeshLib, we valued simplicity and performance while providing a wide gamut of useful computational algorithms. The library also supports the most important data structures today’s sensors can produce—point cloud, mesh, volume, and more. For example, a mesh is represented by a half-edge data structure and cannot be made non-manifold. Some applications may require non-manifoldness, but most practical scans can be represented as manifoldness meshes without an issue. 

## Features
[Overview](https://meshlib.meshinspector.com/features-meshlib/)
### Math basics
 - Math primitives and operations support (Vectors 2D, 3D, 4D; Lines; Planes; Bounding Boxes; Matrices; Affine transformations; Quaternions; Histograms; etc.)
### 3D data handling, creation, modification
 - 3D data various representations support: Mesh, Voxel and Point Cloud.
 - Data creation 
   - Mesh creation by given vertices and triangles,
   - Surface primitives (e.g. tor, cube, sphere, etc).
 - Representation conversions
   - Triangulation of a Point Cloud to Mesh,
   - Mesh to Cloud Point conversion,
   - Mesh to Voxel conversion,
   - Voxel To Mesh conversion.
 - Deformations
   - Laplacian deformation,
   - Freeform deformation,
   - Relax, mesh smoothing,
   - Position Verts Smoothly, arrangement of vertices in accordance with the gradient along the neighbors.
 - Offsets
   - Mesh offset, 
   - Mesh partial offset.
 - Resolution
   - Breaking a mesh into smaller triangles (increasing the resolution)
   - Mesh decimation (decreasing the number of triangles, decreasing the resolution) with a specified error relative to the old mesh.
 - Cutting a contour on a surface. The mesh is modified so that the resulting contour contains new edges cut through triangles at the specified points.
 - Splitting
   - Splitting mesh into sub-meshes (components)
### 3D data operations
 - Boolean ops (union, intersection, difference) 
   - Boolean ops on meshes via voxels. Efficient but not so accurate as explicit mesh operations.
   - Explicit mesh boolean ops, very exact, fast and accurate.
### 3D Data problems fixing
 - Fixing holes in the mesh
   - Holes stitching (removing two holes by stitching their boundaries) 
   - Hole filling,
   - Holes fixing metrics
      - Basic set of triangulation metrics,
      - Extended set of triangulation metrics,
      - Custom triangulation metrics.
 - Delaunay triangulation optimization, changing triangles without changing vertices, according to Delaunay criterion,
 - Tunnels fixing,
 - Multiple edges detection
 - Degenerate triangles fixing,
 - Undercuts fixing, via voxels, 
 - Surface self-intersections fixing
   - Guaranteed fix via voxels, 
   - Fix via Relax (mesh smoothing).
### Functions on 3D data
 - Projection
   - Projecting a point onto a mesh
 - Intersection
   - Intersection of a ray with a mesh,
   - Intersection of a plane with a mesh, result is a contour,
   - Finding a contour representing the intersection of two meshes, meshes remain unchanged,
 - Distance
   - Distance from a point to a mesh,
   - Minimal distance between two meshes,
   - Mesh distance map (height map),
   - 2D contour distance map.
 - Segmentation
   - Semi-auto voxel segmentation (volumes classification).
   - Semi-auto mesh segmentation by curvature.
 - Sampling
   - Mesh sampling. The result is a separate thinned set of vertices, the mesh remains unchanged. 
   - Point cloud sampling. The result is a separate thinned set of points, the cloud remains unchanged
      - Uniform cloud sampling,
      - Grid cloud sampling.
 - Path 
   - Finding a shortest path through the mesh vertices,
   - Finding a geodesic shortest path on the surface, not necessarily through mesh vertices.
 - Iterative Closest Points (ICP), two meshes aligning
   - Point to point,
   - Point to plane.

# MeshInspector
[MeshInspector](https://github.com/MeshInspector/MeshInspector) is a software for 3D geometry processing powered by [MeshLib](https://github.com/MeshInspector/MeshLib).

![image](http://meshinspector.com/wp-content/uploads/2024/03/MeshInspector-software.png)
The application provides:
- Customizable menu window
- Stable and user-friendly viewer
- Selection tools
- Analysis tools
- Simple graphics performance test
- Low-level model constructors and modifiers
- Up to 32 customizable viewports
- Extensive set of plugins
- Ribbon UI
- Embedded python
- Hidden mode
- Supporting search and tooltip

## Features
[Overview](https://meshinspector.com/features/)
This list is not full and is updated each day.

## Developer Features
- Support for most popular operating systems: Windows, MacOS X, Linux Ubuntu (Debian branch), Linux Fedora (RedHat branch)
- Has an installer for Windows/MacOS X and packages for Linux
- Code is clear and safe. A project could be built by Visual Studio 2019, gcc 10+, clang 11+
- Architecture allows users to provide their own custom functionality easily
- Simple interface for Python binding gives the opportunity to develop MeshLib-based Python modules
- Flexible and customizable UI
- Detailed library API documentation is located [here](https://doc.meshinspector.com/)

### Third parties: Core
- Windows 10. vcpkg - package manager.
- Math. eigen3 - linear algebra.
- C++. boost C++ libraries (pre-standart library). tlexpected - tiny error handler. parallel- hashmap - high performance hashmaps.
- Python. pybind11 and cpython - C++ exposers.
- Testing. gtest - google test tools.

### Third parties: Input/Output
- Logging. spdlog - advanced logging tool.
- HTTP. cpr - curl-based request tools.
- Config. tinyxml - *.xml. jsoncpp - *.json.
- File Formats. libzip - *.zip archive. libtiff - *.tiff image. gdcm - *.dicom data.

### Third parties: Graphics and UI
- OpenGL. glad - cross-platform loader. glfw3 - windows, contexts, events, basicIO. imgui - menu, dialogs.
- Fonts. freetype - converting symbols into meshes.
- Algorithms. openvdb - advanced voxels.
   
### Performance
 - Fast drawing up to 20+M triangles,
 - Hardware-accelerated object picker (finding triangle or point under the cursor).

### Viewport camera modes
 - Perspective and Orthographic (Perspective / orthographic view, FOV, Basis / axis, etc)
 - Customize drawing of objects (Components visibility, Transparent, Clipping, Colors, etc.)
 - Renderable objects
   - Cloud points,
   - Meshes,
   - Lines,
   - Voxels
   - Distance Maps
     
### Color and textures 
 - Vertices color map,
 - Triangles color map,
 - Static textures.

### Order independent transparency
### Convenient for mesh algorithms debugging, showing mesh edges, boundaries
### Computed-tomography reconstruction
An ability to reconstruct voxel objects from a set of projection images (radiographs) and known cone-beam CT scanner geometry parameters. Nvidia GPU is utilized via CUDA technology for the best reconstruction performance.
