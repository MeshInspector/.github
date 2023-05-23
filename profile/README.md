![MeshInspector/MeshLib](https://user-images.githubusercontent.com/10034350/176395489-6349670a-b9eb-4f53-886a-35a75b55e6ac.png)
# Welcome to MeshInspector
3D scanning is becoming more and more ubiquitous. Robotic automation, self-driving cars and multitude of other industrial, medical and scientific applications require advanced computer vision to deliver the levels of automation customers expect these days. The great rise of AI gave another boost to computer vision and the need to utilize 3D data to make machines smarter. Not only are tasks at hand becoming more complex, but the size of data grows exponentially. 

There is a multitude of general purpose libraries which deal with 3D data. Some stem from popular CAD packages, some are open source. The commercial ones tend to be quite expensive while open source are free though tend to be limited in functionality provided. Also those libraries value generality above other features  to allow maximum number of applications, but with the growing amounts of 3D data, performance is critical as it never has  been. Some of it can be addressed by using the scale of a commercial cloud, last generation CPU or GPU but underlying complexity of data representation makes it very hard and laborsome.

 - [MeshLib](#meshlib) 3d processing library
 - [MeshInspector](#meshinspector) 3d processing application, based on MeshLib

# Useful links
[MeshInspector web-browser version](https://app.meshinspector.com/)

[G-Code visualizer](https://gcode.meshinspector.com/)

[Slides about MeshLib and MeshInspector](https://docs.google.com/presentation/d/1D0Ry6SE2J25PBtO_G9ZIp1cavoX2wyyY8jgvtjeayC4/edit?usp=sharing)

[MeshInspector YouTube channel](https://www.youtube.com/channel/UCv9bNhwoVDPaLPPyWJeVPNg)

[MeshInspector Releases for Windows/Linux/Mac](https://github.com/MeshInspector/MeshInspector/releases)

[Documentation](https://meshinspector.github.io/MeshLib/html/index.html)

[Email us](mailto:support@meshinspector.com)

[Contact us anonymously](https://meshinspector.github.io/ReportIssue/)

[Follow us on LinkedIn](https://www.linkedin.com/company/meshinspector/)

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

## Some features
This list is not full and updating each day
### Technology
 - OpenGL v4 by default, v3 for a compatibility
### Performance
 - Fast drawing up to 20+M triangles,
 - Hardware-accelerated object picker (finding triangle or point under the cursor).
### Viewport camera modes
 - Perspective and Orthographic,
 - Renderable objects
   - Cloud points,
   - Meshes,
   - Lines,
   - Voxels
   - DistanceMaps
### Color and textures 
 - Vertices color map,
 - Triangles color map,
 - Static textures.
### Order independed transparency
### Convenient for mesh algorithms debugging, showing mesh edges, boundaries
### Computed-tomography reconstruction
An ability to reconstruct voxel object from a set of projection images (radiographs) and known cone-beam CT scanner geometry parameters. Nvidia GPU is utilized via CUDA technology for the best reconstruction performance.
