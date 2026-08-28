<p align="center">
  <img alt="MeshInspector — 3D mesh processing library and application" src="https://meshinspector.com/wp-content/uploads/2024/03/3D-mesh-processing-library.png" width="70%">
</p>

# 3D data processing, from SDK to finished application

We build software for meshes, point clouds and volumes — the data your scanners, CT machines and CAD systems produce every day. Two products, one engine:

| | | |
|---|---|---|
| 🧩 **[MeshLib](https://github.com/MeshInspector/MeshLib)** | The SDK. Mesh boolean, repair, simplification, offset, point cloud triangulation, ICP and voxel processing for **C++, C, C#, Python and WebAssembly**. | [Try the live demo](https://demo.meshlib.io) · [meshlib.io](https://meshlib.io/) |
| 🔍 **[MeshInspector](https://github.com/MeshInspector/MeshInspector)** | The application. An STL editor, viewer and mesh repair tool for 3D scans and 3D printing — on your desktop or in a browser tab. | [Open the web app](https://app.meshinspector.com/sign-in) · [meshinspector.com](https://meshinspector.com/) |

MeshInspector is built entirely on MeshLib, so every algorithm you see in the UI is available as an API — and every SDK release is dogfooded on real production data before it ships.

## What we are good at

- **Geometry algorithms engineered to revolutionize.** We help software engineers process, repair, measure and optimize 3D data with next-generation algorithms, reducing development time and costs.
- **Manifold by construction.** A half-edge data structure in which most non-manifold situations are simply not representable, so topology errors surface where they happen instead of three pipeline stages later.
- **One engine, five languages.** The same algorithms and the same results on the desktop, on a server, and in the browser.
- **Measured performance.** Our public boolean benchmark compares MeshLib across nine libraries on 2M-triangle models — [method and data](https://meshlib.io/blog/comparing-3d-boolean-libraries/). The [simplification benchmark](https://meshlib.io/blog/comparing-3d-simplification-libraries/) does the same across 11 libraries.
- **Proven in regulated workflows.** [SmileInspector](https://smileinspector.io/), our [FDA-cleared](https://smileinspector.io/news/smileinspector-launches-after-fda-clearance/) clear-aligner platform, runs on the same engine.
- **25+ years** in 3D geometry, 100+ engineers, and a support team that answers.

## Where our software is used

3D printing and additive manufacturing · scan-to-print workflows · digital dentistry · medical and surgical planning · metrology and quality inspection · GIS and BIM · robotics and simulation.

## Start here

| I want to… | Go to |
|---|---|
| Try the SDK without installing anything | [demo.meshlib.io](https://demo.meshlib.io) |
| Install the SDK | `pip install meshlib` · [Installation Guide](https://meshlib.io/documentation/InstallationGuide.html) |
| Read the docs | [meshlib.io/documentation](https://meshlib.io/documentation/index.html) |
| Use the application | [Web app](https://app.meshinspector.com/sign-in) · [Download](https://meshinspector.com/download/) |
| Report a bug | [MeshLib issues](https://github.com/MeshInspector/MeshLib/issues) · [MeshInspector issues](https://MeshInspector.github.io/ReportIssue/) |
| Talk to us about licensing | [Book a call](https://meshlib.io/book-a-call/) |

## Licensing

MeshLib is **source-available**: free for non-commercial and educational use, commercial use requires a licence. See the [licence page](https://meshlib.io/license/).
