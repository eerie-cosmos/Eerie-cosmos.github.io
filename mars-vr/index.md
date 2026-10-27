---
layout: page
title: 3D Models of Planetary Surfaces in Virtual Reality
permalin: /master-thesis/
---

M.Sc. project group • TU Dortmund, 2022 • Role: rover-image photogrammetry pipeline

The team built a workflow that placed orbital elevation models (stereo plus sharp from shading) and rover-based 3D rock models reconstruction of Jezero crater in one virtual reality scene. My role was the Uncalibrated photogrammetry and meshing pipeline that reconstructed raw Perseverance images of the rock “Cheiron” and other Sols into a textured model light enough for VR integration. 

![My pipeline, photo alignment, dense cloud, textured mesh](/Assets/mars-vr/pipeline.jpg)

Figure 1. (1) My pipeline across Metashape Pro, CloudCompare and MeshLab. (2) Uncalibrated alignment: estimated camera poses, sparse cloud and manual markers. (3) Stitche dense cloud of the Cheiron rock (sol 238). (4) Decimate, textured mesh for Unity VR. Source images: [NASA Mars 2020 raw images](https://mars.nasa.gov/mars2020/multimedia/raw-images/)(NASA/JPL-Caltech).

## Problem

3D models give planetary scientists a better sense of shape and scale than 2D maps. Perseverance‘s raw images are publicly provided by NASA, captured from several cameras (Navcam, Hazcam, Mastcam-Z), lacking the metadata needed for automatic calibration. The images also include rover shadows and large viewpoint changes. Reconstructing a complete, lightweight 3D models from these images require careful image selection, registeration and meshing.
Multi-view and Multi-camera Uncalibrated Perseverance imagery used for a textured 3D reconstruction of VR-ready model of the Cheiron Martian rock. The pipeline was based on uncalibrated stereo vision, SfM-MVS, and bundle adjustment concepts to generate dense point clouds from imagery acquired on the surface of Mars by the NASA Perseverance rover. For the resulting multi-view 3D point cloud, data fusion, spatial alignment and stitching based on ICP and RANSAC techniques, as well as geometrical refinement were carried out for the reconstruction of 3D surface models integrated into an interactive, physics-enabled VR environment. The pipeline employed a variety of free and commercial programming environments, such as MATLAB, OpenCV, Agisoft Metashape Pro, OpenCV, MeshLab, CloudCompare, and Unity.


## My pipeline

1. **Image selection**: 250 candidate images(sol 235-285) of which 160 were selected for the reconstruction. The redundant images providing no new accurate feature correspondences and the images containing mostly rover-shadows were removed. Some regions of the images that interfered with the key point matching were masked, and 21 manual markers aided the feature points matching.
2. **Uncalibrated SfM** in Agisoft Metashape Pro using bundle adjustment for poses and intrinsics, followed by dense matching with mild depth filtering.
3. **Divide, stitch and align**: two point clouds reconstructed individually with top (96 images, 16 markers) and bottom (48 images, 8 markers) were registered to form the complete rock structure point cloud in CloudCompare.Point pairs were used for coarse alignment and ICP with scale adjustment for fine alignment. The stitched cloud had about 89 million points.
4. **Meshing**: Octree subsampling, normal estimation with 99 neighbours, screened Poisson reconstruction at Octree depth 15 in MeshLab, trimming of low-density extrapolated surfaces.
5. **VR-ready model**: Decimation of the 105 million face mesh then importing into unity.

Multiple images with different views captured from different angles are matched in order to estimate camera positions and orientations. The matched pixels become millions of 3D points with which smooth closed surfaces are fitted through. The resulting surface is simplified and textured according to the captured images so a VR headset can render it smoothly.

## Results

- A textured, watertight model of the Cheiron rock (sol 238) that runs in the team’s Unity VR scene without lagging.
- MeshLab and CloudCompare provided comparable mesh quality, on a 32 GB laptop CloudCompare crashed above decree depth 12, so MeshLab was used.
- The same pipeline was implemented for a sub-team’s sol 195 cloud, filling holes caused by shadows and missing views originating from the point cloud reconstruction.

## Limitations

Evaluation was visual and qualitative, without ground truth. The gaps and holes were filled through interpolation and not measurements or further feature correspondences due to ambiguity from repeated textures or patches with no distinct features.

## My role

Member of the VR-integration sub-team. I developed and documented the 3D point cloud and 3D model pipeline and the rock model results. Assisted in the MATLAB/OpenCV rover reconstructions. The Unity scene and the DEMs were built by other team members.
