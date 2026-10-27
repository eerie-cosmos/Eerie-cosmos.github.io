---
layout: page
title: “Coupled Deblurring and 3D Reconstruction from Image Sequences”
permalin: /master-thesis/
---

Master’s thesis • M.Sc. Automation and Robotics, TU Dortmund, 2025 • supervisor Prof. Dr. Christian Wöhler • grade 1.0

[2-page summary (PDF)](/Assets/docs/Master-thesis-summary-2p.pdf) • Full thesis on request

![Method overview: defocused input image, sharp regions, plane of focus fitted to 3D point cloud, CoC radius per pixel, spatially varying PSFs density before and after](/Assets/master-thesis/method-overview.png)

Figure 1. Method overview (Data set 1, image 2). (1) Defocused input image. (2) Sharp region (green) from LoG and Otsu thresholding. (3) SfM-MVS point cloud with fitted plane of focus (green), optical axis (blue) and camera pose (cyan). (4) Per-pixel circle of confusion r_b image array. (5) Sampled local Gaussian PSFs: larger and brighter spots indicate stronger local blur. (6) Point density map before (left) and after (right) Richardson-Lucy deblurring on a common scale. 

## Problem

The microscopic camera CAM-M on the Rashid-1 lunar rover captures images of the regolith at 20-27 µm per pixel ([Els et al., 2024](https://doi.org/10.1007/s11214-024-01117-7)). It has no focus or aperture adjustment mechanism, its depth of field is 22 mm and its optical axis is tilted 40°. These features lead to uneven terrains pushing parts of every frame out of focus. Depth-from-focus and depth-from-defocus methods require focus stacks or several apertures adjustments, respectively, both of which the microscopic camera CAM-M by design cannot provide.

**Research Question:** can spatially varying defocus blur be estimated and deblurred using only overlapping image sequences from monocular camera with a fixed depth of field (focus) and aperture?

## Approach

1. **Reconstruct** the initial 3D point cloud from the image sequence using SfM-MVS (Agisoft Metashape Pro Python scripted API).
2. **Estimate the plane of focus (sharpness)**: detect sharp regions (Laplacian of Gaussian + Otsu), match them to 3D tie points of the initial point cloud and fit a plane to these 3D points (SVD).
3. **Derive Blur from optics geometry**: each point’s distance to the plane of focus gives a value describing its defocus which is substituted with in the image formation model to obtain the circle-of-confusion radius r_b on the sensor plane, interpolated and processed to a per-pixel map.
4. **Spatially varying deconvolution**: a Gaussian PSF with σ = α·r_b^β per 8x8 local window with 50% overlap, and each image is restored using the linear Wiener filter and the nonlinear, iterative Richardson-Lucy algorithm.
5. **Evaluate on the downstream task**: reconstruct the 3D point cloud from the restored deblurred images and compare point density maps after ICP alignment.

The 3D model informs us how far each patch of the regolith surface was from the plane of sharpness, the optics tells us how blurred that distance makes it, and then one can undo exactly that much blur in each patch.

## Results

![Dense clouds and density maps before and after deblurring, Data set 1 and 2](/Assets/master-thesis/results-density.jpg)

Figure 2. Density maps are normalized after the ICP alignment for efficient comparison.

- Deblurred images gave **denser clouds with fewer data gaps** in both data sets, a significantly **increased areal point density** and thus a much **higher spatial resolution** than the initial 3D reconstruction.
- **Method with highest performance and best results is dependent on the data**: Richardson-Lucy performed best on Data set 1, while Wiener filter was densest on Data set 2 but contained small gaps in one corner. However Wiener filer was the most consistent of the two.
- **Visual quality is not always an indication of providing more useful information**: some settings that produced visibly sharper images produced fewer feature correspondences, so restoration should be evaluated based on the downstream output quality, information gain and tuned for the geometric task.

## Limitations

- The evaluation is qualitative (density map, with no ground-truth surface reconstruction, and parameters were tuned on the test data.
- Intrinsics were estimated by self-calibration in bundle adjustment and the scale from the nominal working distance.
