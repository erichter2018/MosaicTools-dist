# Ca1 - carotid sheath 2.5-D segmentation model: data and attribution

`ca1-r1.onnx` segments the ipsilateral common carotid artery (CCA), internal carotid artery (ICA), internal jugular
vein (IJV), and adjacent vessels on an 80 x 80 mm axial CT crop (0.5 mm grid, 160 x 160 px) with +/-2.0 mm neighbour
context from true Hounsfield units. MosaicTools uses it to exclude touching jugular veins and identify the true ICA
branch during carotid stenosis tracing. It was trained by the MosaicTools author; nothing here is endorsed by the
dataset authors.

Trained on:
- TotalSegmentator CT dataset v3 (v3.0.0, Zenodo) - Wasserthal J. et al., "TotalSegmentator: Robust Segmentation of
  104 Anatomic Structures in CT Images", Radiology: Artificial Intelligence 2023; licensed CC BY 4.0 (head/neck vessel
  labels; all held-out evaluation scans strictly excluded).
- SegRap 2023 (Segmentation of Organs-at-Risk and Gross Tumor Volume of NPC for Radiotherapy Planning) - Luo X. et al.,
  licensed CC BY 4.0 (used with teacher vessel labels; strictly separated from held-out evaluation sets).

Changes from the source data: unilateral 80 x 80 mm crops centred on the carotid sheath at 0.5 mm in-plane resolution
with +/-2.0 mm neighbour slices across soft-tissue (40/400), CTA lumen (250/700), and bone/calcium (500/1500) windows;
training-time spatial, rotation, noise, and bolus-attenuation augmentation.

Licence of this model file: the training data is CC BY 4.0, which allows a derived model to be shared with this
attribution.
