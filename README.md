# Six Impossible Things Before Breakfast

Six Impossible Things Before Breakfast Ltd. is an Ireland-based company, working on quite a few interesting things, and releasing some (but not all ;-)) of them as open source here. 

## Released:
- [sixit/core](https://github.com/sixitbb/sixit-core/tree/main) - a collection of small but all-important libs which lay foundation for all the other sixit/ libs. 

## Other sixit libs we already have and plan to release soon:
- sixit/dmath - cross-platform deterministic math lib (as ~~seen on TV~~ presented on CppCon24)
- sixit/geometry - geometrical primitives and algorithms (both 2D and 3D), with cross-platform deterministic support
- sixit/rw - serialization lib aiming top efficiency, and able to support ABSOLUTELY ANY format (JSON, protobuf, custom binary competing speed-wise with FlatBuffers and Cap'nProto, you name it). Also supports arbitrary hashing (as a pseudo-serialization), including crypto-quality hashing (BLAKE2 ATM, more to be added). 
- sixit/graphics - comprehensive support for meshes (incl. skinning), textures, etc. Materials are PBR-only though. Also will contain basic helpers such as decimator half-edge-oriented framework (based directly on [A General Framework for Mesh Decimation](https://www.graphics.rwth-aachen.de/media/papers/mesh.pdf)).
- sixit/physics - simple physics, with cross-platform deterministic support
   + currently only rigid body physics , but we plan to add more
- sixit/osal - os abstraction library; abstracts less common OS features which are not a part of the std:: (yet?).
- sixit/wasm - abstracting wasm engines (the same host can use any of supported engines, from wasm3 to wasm2c, with adding more being easy)

### CI
- sixit/sarge: opinionated CI which is C++-aware, tightly integrated with build, has a pre-merge CI check option (prevents BS from ever getting into your trunk, HIGHLY recommended), supports build in identical VMs, and supports our "cpp-tight-ship" development model with lots of guideline checks (can be adjusted to your needs). Sarge is highly modular too.

### Bloom Game Engine
- sixit/bloom: a gaming engine, which uses most of the things above, and aiming to support modern development practices (WASM for scripting, PBR for materials, Vulkan & Metal for rendering), and aims to fully support Web too.
   + NB: some OPTIONAL features of Bloom engine represent our know-how, and will NOT be open-sourced. 
