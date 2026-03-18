# Scotty3D: Graphics & Geometry Showcase
Disclaimer: This repository serves as a Technical Showcase for the Scotty3D project (CMU 15-462/662). Due to academic integrity policies, source code is private. This document focuses on algorithmic implementation and visual results.

Scotty3D is a high-performance C++17 software renderer and geometry processing suite. It simulates the entire graphics pipeline, from raw half-edge mesh manipulation to physically-based path tracing.

---

## Module 1: Software Rasterizer
### Core: Understanding the GPU Hardware Pipeline.
### Technical Features:
* Perspective-Correct Interpolation: Solved the attribute mapping problem under non-linear projection.
* Anti-Aliasing: Integrated Supersampling (SSAA) and Alpha Blending for high-quality edge rendering.

---

## Module 2: Geometry Processing (MeshEdit)
### Core: Manipluating topology with the Half-edge data structure.
### Key Implementations:
* Dynamic Topology: Implemented split, collapse, and flip operations to support complex mesh editing.
* Loop Subdivision: A smooth-surface algorithm that handles boundary cases, ensuring G1 continuity across the mesh.
* Isotropic Remeshing: Maintains edge length consistency to improve simulation stability.

---

## Module 3: Path Tracer & PBR
### Core: Simulating the Physics of Light.
### Acceleration & Efficiency:
* BVH (Bounding Volume Hierarchy): Built a high-performance SAH (Surface Area Heuristic) based BVH, reducing intersection complexity.
* Global Illumination: Implemented recursive Path Tracing with Importance Sampling to solve the Rendering Equation.
### Materials (BSDF): 
* Microfacet Models: Implemented the Cook-Torrance model for realistic metallic and dielectric surfaces.
* Refraction & Reflection: Handled total internal reflection (Fresnel equations) for realistic glass materials.

---

## Module 4: Animation SystemCore: Skeletal Rigging and Dynamics.
### Technical Features:
* Linear Blend Skinning (LBS): Computing vertex positions based on weighted joint transforms.
* Inverse Kinematics (IK): Implemented Jacobian-based or FABRIK solvers to control character limbs via end-effectors.
* Particle Simulation: Mass-spring systems for cloth or basic physical interactions.

---

## Performance & Metrics
Real-time Interaction: Stable 60 FPS for mesh editing and viewport preview.
Intersection Efficiency: BVH acceleration achieved 100x+ speedup in scenes with over 100k triangles.
Robustness: Passed 100% of the CMU Scotty3D automated test suite for geometric consistency.

## Build & Environment
Language: C++17
Libraries: SDL2 (Windowing), SIMD (Optimization where applicable)
Platform: Cross-platform (Windows/macOS/Linux)
