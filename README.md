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
