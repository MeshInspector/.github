![MeshInspector/MeshLib](https://user-images.githubusercontent.com/10034350/176395489-6349670a-b9eb-4f53-886a-35a75b55e6ac.png)
# Welcome to MeshInspector
The MeshInspector application is a cutting-edge tool for diverse 3D data types, like point clouds, CT scans, meshes, voxel data, and polylines. This all-in-one tool offers a modern, intuitive interface, ensuring efficient 3D data handling. It's lightning-fast, supports all platforms, and is browser-accessible. Ideal for 3D scanning and printing industry experts, engineers, and scientists, MeshInspector is your essential tool.

Experience the advantages of MeshInspector:
- Rapidly convert massive point clouds (over 1GB in size) into optimized meshes, achieving a 10x speed boost.
- Easily employ manual repair tools or automatically repair low-quality meshes in seconds.
- Effectively handle CT or MRI scans with high-quality volume rendering, isolate components by density, segment them, and convert them into meshes for advanced processing.

MeshInspector is an all-in-one tool built upon the robust open-source MeshLib 3D processing library. With MeshInspector, you can take your 3D data analysis to the next level and unlock new insights into your work.

 - [MeshLib](#meshlib) 3d processing library
 - [MeshInspector](#meshinspector) 3d processing application, based on MeshLib

# Useful links
[MeshInspector website](https://meshinspector.com/)

[MeshInspector web-browser version](https://meshinspector.com/)

[Download MeshInspector (Windows/Linux/Mac)](https://meshinspector.com/download/)

[MeshLib Documentation](https://meshlib.meshinspector.com/documentation/)

[Submit an issue](https://meshinspector.github.io/ReportIssue/)

# MeshLib
[MeshLib](https://github.com/MeshInspector/MeshLib) is open source 3d procesing library.

The goal which we set when designing MeshLib was to value simplicity and performance while providing a wide gamut of useful computational algorithms. The library also supports the most important data structures today’s sensors can produce - pointcloud, mesh, volume and more. For example, mesh is represented by half-edge data structure and cannot be made non-manifold. Some applications may require non-manifoldness, but most practical scans can be represented as manifoldness meshes without an issue. 

## Some features
This list is not full and updating each day
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
   - Laplassian deformation,
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
 - Fixing holes in mesh
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
   - Finding a contour representing intersection of two meshes, meshes remain unchanged,
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
[MeshInspector](https://github.com/MeshInspector/MeshInspector) is an application for geometry processing based on [MeshLib](https://github.com/MeshInspector/MeshLib).

![image](https://user-images.githubusercontent.com/3136125/153055383-a86e9e4f-f260-476c-af5e-c5e28e7a1632.png)
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
[Overview](https://meshinspector.com/features-overview)
This list is not full and updating each day

## Developer Features
- Support for most popular operating systems: Windows, MacOS X, Linux Ubuntu (Debian branch), Linux Fedora (RedHat branch)
- Has an installer for Windows/MacOS X and packages for Linux
- Code is clear and safe. Project could be built by Visual Studio 2019, gcc 10+, clang 11+
- Architecture allows users to easily provide their own custom functionality
- Simple interface for python binding gives the opportunity to develop MeshLib-based python modules
- Flexible and customizable UI
- Detailed library API documentation is located [here](https://meshlib.meshinspector.com/documentation/)

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
