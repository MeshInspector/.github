![image](https://github.com/MeshInspector/.github/assets/140729402/5aebb343-b37e-4c27-8ed8-39ccee0e75f4)![image](https://github.com/MeshInspector/.github/assets/140729402/9bd140e0-9c09-4577-8ffe-87678003d4ed)![image](https://github.com/MeshInspector/.github/assets/140729402/28cbe352-f106-4aec-ba25-24c2e46d5b0d)![image](https://github.com/MeshInspector/.github/assets/140729402/37b6c8e5-8bff-4f67-b16b-bed7a0267950)![image](https://github.com/MeshInspector/.github/assets/140729402/b1f82bcc-677b-4d91-a0df-6a1c4701dd94)![image](https://github.com/MeshInspector/.github/assets/140729402/f29b0458-fb76-4eba-9ed6-fbee477afbaf)![MeshInspector/MeshLib](https://user-images.githubusercontent.com/10034350/176395489-6349670a-b9eb-4f53-886a-35a75b55e6ac.png)
# Welcome to MeshInspector
3D scanning is becoming more and more ubiquitous. Robotic automation, self-driving cars and multitude of other industrial, medical and scientific applications require advanced computer vision to deliver the levels of automation customers expect these days. The great rise of AI gave another boost to computer vision and the need to utilize 3D data to make machines smarter. Not only are tasks at hand becoming more complex, but the size of data grows exponentially. 

There is a multitude of general purpose libraries which deal with 3D data. Some stem from popular CAD packages, some are open source. The commercial ones tend to be quite expensive while open source are free though tend to be limited in functionality provided. Also those libraries value generality above other features  to allow maximum number of applications, but with the growing amounts of 3D data, performance is critical as it never has  been. Some of it can be addressed by using the scale of a commercial cloud, last generation CPU or GPU but underlying complexity of data representation makes it very hard and laborsome.

 - [MeshLib](#meshlib) 3d processing library
 - [MeshInspector](#meshinspector) 3d processing application, based on MeshLib

# Useful links
[MeshInspector website](https://meshinspector.com/)

[MeshInspector web-browser version](https://meshinspector.com/)

[Download MeshInspector (Windows/Linux/Mac)](https://meshinspector.com/download/)

[MeshLib Documentation](https://meshinspector.com/MeshLib/doc)

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
- Detailed library API documentation is located [here](https://meshinspector.com/MeshLib/doc)

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
 - 
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
