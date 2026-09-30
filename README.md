# MosaicTools model files

Downloaded by MosaicTools on first use. Not needed by anyone else.

## a1/ - A1, one-slice CT anatomy model

`a1-v2.onnx` (+ `a1-v2_classes.json`): labels 68 structures on one axial CT slice as displayed.
Input [1,1,256,256] grey 0..1; output [1,69,256,256] logits (0 = background, k = the k-th class name).

Trained on:
- TotalSegmentator CT dataset v2.0.1 - Wasserthal J. et al., Radiology: Artificial Intelligence 2023.
  Zenodo 10.5281/zenodo.10047292, licensed CC BY 4.0.
- AMOS 2022 - Ji Y. et al., NeurIPS 2022. Zenodo 10.5281/zenodo.7262581, licensed CC BY 4.0.
