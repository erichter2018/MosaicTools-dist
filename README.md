# MosaicTools model files

Downloaded by MosaicTools on first use. Not needed by anyone else.

## a1/ - A1, one-slice CT anatomy model

`a1-v2.onnx` (+ `a1-v2_classes.json`): labels 68 structures on one axial CT slice as displayed.
Input [1,1,256,256] grey 0..1; output [1,69,256,256] logits (0 = background, k = the k-th class name).

Trained on:
- TotalSegmentator CT dataset v2.0.1 - Wasserthal J. et al., Radiology: Artificial Intelligence 2023.
  Zenodo 10.5281/zenodo.10047292, licensed CC BY 4.0.
- AMOS 2022 - Ji Y. et al., NeurIPS 2022. Zenodo 10.5281/zenodo.7262581, licensed CC BY 4.0.

## xr1/ - XR1, plain X-ray anatomy model

`xr1-v2.onnx` (+ `xr1-v2_classes.json`): labels 130 bones and organs on a plain film as displayed.
Input [1,1,512,512] grey 0..1; output [1,130,512,512] logits, multi-label (sigmoid), one channel per class name.

Trained on:
- Synthetic radiographs projected from the TotalSegmentator CT dataset v2.0.1 - Wasserthal J. et al.,
  Radiology: Artificial Intelligence 2023. Zenodo 10.5281/zenodo.10047292, licensed CC BY 4.0.
- FleXray real-film datasets (CC BY 4.0), the Montgomery County chest set (U.S. National Library of
  Medicine), and Roboflow Universe community sets (licenses as set by each uploader).

## xl1/ - XL1, plain X-ray landmark-point model

`xl1-v3cd_a.onnx` + `xl1-v3cd_b.onnx` (+ `xl1-v3cd_points.json`): puts named bony landmark points (joint centres, styloid
tips, malleoli, epicondyles, tuberosities, glenoid rim, finger and toe joints...) on a plain film as displayed - 211 names
over 12 views (`views` in the json). Two training runs; MosaicTools averages their heatmaps.
Input [1,1,512,512] grey 0..1; output [1,211,256,256] heatmaps, one channel per name (`names`), peak = the point.

Trained on (labels: the author's hand-placed points, points copied between films by RadiographLandmarkMatching and kept
only where the references agreed, and the datasets' own annotations where noted):
- MURA - Rajpurkar P. et al., Stanford AIMI. Stanford University School of Medicine MURA Dataset Research Use Agreement.
- RAM-H1200 (hand radiographs; its joint boxes and bone masks give the finger and carpal points) and RAM-W600 (wrist) -
  TokyoTechMagicYang on Hugging Face, licensed CC BY-NC-SA 4.0.
- FracAtlas - Abedeen I. et al., Scientific Data 2023, figshare 22363012, licensed CC BY 4.0.
- BTXRD - figshare 27865398, licensed CC BY 4.0.
- OrthoFrac-XR - figshare 32021085, licensed CC BY 4.0.
- "Ankle joints" radiographs - Mendeley Data dskmk9cb8g v2, licensed CC BY-NC 3.0.
- CGMH Knee Segmentation Database - github.com/yaufan/Knee_Segmentation_Database (MIT; image rights not stated).
- Roboflow Universe "pelvis_xray" v5 (uploader-declared Public Domain).
