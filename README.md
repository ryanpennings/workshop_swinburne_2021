# Workshop: Robotic Fabrication with COMPAS FAB

## Swinburne University of Technology

> 15., 16., and 17.06.2021

![Flyer](images/flyer.png)

## Overview

* Intro
* Kinematics
* Path planning
* Scene and end effectors
* Pick and Place
* Assemblies
* Robot control

👉 [Slides](https://docs.google.com/presentation/d/1q8ZO1cg-EHn0g0nu1sDULYFoRuld-sci59pUsOhEBe0/edit?usp=sharing)

## Examples

### Introduction

* Primitives
  * [Primitives](examples/001_primitives.py)
  * [Operations](examples/002_primitives_operations.py)
  * [Constructors](examples/003_primitives_constructors.py)
  * [Equivalences to built-ins](examples/004_primitives_equivalence.py)
  * [Transforms](examples/005_primitives_transforms.py)
* Shapes
  * [Shapes](examples/006_shapes.py)
  * [Shapes in Rhino](examples/007_shapes_rhino.py)
* Mesh datastructure
  * [Mesh in Rhino](examples/010_mesh_rhino.py)
  * [Mesh in Blender](examples/011_mesh_blender.py)
  * [Mesh in GHPython](examples/012_mesh_ghpython.py)
  * [Mesh from scratch](examples/013_mesh_from_scratch.py)
  * [Mesh stand-alone viewer](examples/014_mesh_plotter.py)
  * [Queries: vertex degree](examples/015_mesh_info_vertex_degree.py)
  * [Queries: vertices on boundary](examples/016_mesh_info_vertices_on_boundary.py)
  * [Queries: face neighbors](examples/017_mesh_info_face_neighbors.py)
  * [Queries: vertex neighbors](examples/018_mesh_info_vertex_neighbors.py)
  * [Queries: edge strip](examples/019_mesh_info_edge_strip.py)
  * [Queries: edge loop](examples/020_mesh_info_edge_loop.py)
  * [Vertex normals in Rhino](examples/021_mesh_vertex_normals_rhino.py)
  * [Flip cycles](examples/022_mesh_flip_cycles_rhino.py)
  * [Artists in Rhino](examples/023_mesh_rhino.py)
  * [Boolean operations with CGAL](examples/024_mesh_booleans.py)
  * [Boolean operations in Rhino](examples/025_mesh_booleans_rhino.py)

* Network datastructure
  * [Network from scratch](examples/030_network_from_scratch.py)
  * [Network in Rhino](examples/031_network_from_scratch_rhino.py)
  * [Network attributes](examples/032_network_from_scratch_rhino.py)
  * [Network stand-alone viewer](examples/032_network_plotter.py)
  * [Queries: node neighbors](examples/033_network_info_node_neighbors.py)
  * [Queries: shortest path](examples/034_network_info_shortest_path.py)
  * [Interactive network](examples/035_network_interactive.py)
  * [Serialization](examples/036_network_serialization.py)
  * [Serialization in Rhino](examples/037_network_serialization_rhino.py)
  * [Serialization of complex types](examples/038_network_serialization_complex_type.py)
  * [Network Koch snowflake](examples/039_network_koch.py)

* Remote Procedure calls
  * [Basic remote procedure call](examples/040_rpc_basic_example.py)

### Robotic fundamentals

* Frame
  * [Construct a frame](examples/101_several_ways_to_construct_frame.py)
  * [Point in frame](examples/102_point_in_frame.py)
  * [Frame in frame](examples/103_frame_in_frame.py)
  * [Box from world to local](examples/104_box_from_the_world_to_local.py)
  * [Box from world to local in Rhino](examples/105_box_from_the_world_to_local_rhino.py)

* Transformation
  * [Examples](examples/106_examples_transformation.py)
  * [Inverse transformation](examples/107_inverse_transformation.py)
  * [Pre-multiplication](examples/108_premultiply_transformations.py)
  * [Pre vs post multiplication](examples/109_pre_vs_post_multiplication.py)
  * [Matrix decomposition](examples/110_decompose_transformation.py)
  * [Transform point and vector](examples/111_transform_point_and_vector.py)
  * [Transform multiple](examples/112_transform_multiple.py)
  * [Change of basis](examples/113_change_basis_transformation.py)
  * [Transform between frames](examples/114_transformation_between_frames.py)
  * [Box from world to local in Rhino](examples/115_box_from_the_world_to_local_rhino.py)

* Rotation
  * [Construct a rotation](examples/116_several_ways_to_construct_rotation.py)
  * [Robot TCP orientations](examples/117_robot_tcp_orientations.py)
  * [Euler angles](examples/118_euler_angles.py)
  * [Axis angle](examples/119_axis_angle.py)
  * [Quaternions](examples/120_quaternion.py)


## Requirements

* Minimum OS: Windows 10 Pro or Mac OS Sierra 10.12
* [Anaconda 3](https://www.anaconda.com/distribution/)
* [Docker Desktop](https://www.docker.com/products/docker-desktop) Docker Toolbox would also work but it's a bit more annoying. After installation on Windows, it is required to enable "Virtualization" on the BIOS of the computer.
* [Rhino 6/7 & Grasshopper](https://www.rhino3d.com/download)
* [Visual Studio Code](https://code.visualstudio.com/): Any python editor works, but we recommend VS Code + extensions [as mentioned in our docs](https://gramaziokohler.github.io/compas_fab/latest/getting_started.html#working-in-visual-studio-code-1)

## Installation

We use `conda` to make sure we have clean, isolated environment for dependencies.

First time using `conda`? Make sure you run this at least once:

    (base) conda config --add channels conda-forge

Clone this repository and create a new conda environment:

    (base) cd path/to/workshop_swinburne_2021
    (base) conda env create -f environment.yml
    (base) conda activate swinburne

<details><summary>Alternatively, create environment manually</summary>
<p>

The conda environment can also be manually created:

    (base) conda create -n swinburne python=3.8 compas_fab>=0.19.1 --yes
    (base) conda activate swinburne

</p>
</details>

**Mac**

Also install `python.app` after activating the environment:

    (swinburne) conda install python.app

### Verify installation

    (swinburne) python -m compas

    Yay! COMPAS is installed correctly!

    COMPAS: 1.7.1
    Python: 3.8.10 | packaged by conda-forge | (default, May 11 2021, 06:25:23) [MSC v.1916 64 bit (AMD64)]
    Extensions: ['compas-fab', 'compas-slicer', 'compas-cgal', 'compas-rrc']

### Install on Rhino

    (swinburne) python -m compas_rhino.install
    (swinburne) python -m compas_rhino.install -v 7.0

### Update installation

To update your environment:

    (swinburne) conda env update -f environment.yml
