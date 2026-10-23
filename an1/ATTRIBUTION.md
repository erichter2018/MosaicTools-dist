# An1 - abdominal aorta outer-wall model: data and attribution

`an1-r1.onnx` outlines the abdominal aorta's OUTER WALL (lumen + thrombus + wall), the iliac arteries and the IVC /
iliac veins on a 160 x 160 mm crop of one axial CT image (1.0 mm grid), from true Hounsfield units. MosaicTools uses
the aorta class to measure an aortic aneurysm perpendicular to the vessel centerline. It was trained by the
MosaicTools author; nothing here is endorsed by the dataset authors.

Trained on:
- TotalSegmentator CT dataset v3 (v3.0.0, Zenodo) - Wasserthal J. et al., "TotalSegmentator: Robust Segmentation of
  104 Anatomic Structures in CT Images", Radiology: Artificial Intelligence 2023; licensed CC BY 4.0. Labels used:
  aorta, iliac_artery_left / right, inferior_vena_cava, iliac_vena_left / right, and the vertebrae (L1-L5, to find
  the abdominal aorta's range). 999 training and 95 validation scans (the dataset's own split); the test scans were
  never trained on.

No other data was used. Two UWA 4D-CTA abdominal aortic aneurysm sets (Zenodo 10.5281/zenodo.15477710 and 19182978,
CC BY 4.0) were looked at during development: the 20-patient set was dropped before training (its wall surfaces did
not line up with its images) and the 10-patient set was not used for training.

Changes from the source data: the abdominal aorta's range (T12 to the iliac arteries) cropped with a 100 mm margin;
labels merged into four classes (background, aorta outer wall, iliac artery, IVC or iliac vein); slices resampled on
the fly to a 1.0 mm grid around the aorta; training-time augmentation (shift, scale, rotation, intensity, noise).

Licence of this model file: the training data is CC BY 4.0, which allows a derived model to be shared with this
attribution.
