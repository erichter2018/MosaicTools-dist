# An1 - abdominal aorta outer-wall model: data and attribution

`an1-r2.onnx` (and prior `an1-r1.onnx`) outlines the abdominal aorta's OUTER WALL (lumen + thrombus + wall), the iliac
arteries and the IVC / iliac veins on a 160 x 160 mm crop of one axial CT image (1.0 mm grid), from true Hounsfield
units. MosaicTools uses the aorta class to measure an aortic aneurysm perpendicular to the vessel centerline. It was
trained by the MosaicTools author; nothing here is endorsed by the dataset authors.

Trained on:
- TotalSegmentator CT dataset v3 (v3.0.0, Zenodo) - Wasserthal J. et al., "TotalSegmentator: Robust Segmentation of
  104 Anatomic Structures in CT Images", Radiology: Artificial Intelligence 2023; licensed CC BY 4.0. Labels used:
  aorta, iliac_artery_left / right, inferior_vena_cava, iliac_vena_left / right, and the vertebrae (L1-L5, to find
  the abdominal aorta's range). Official train/val split only; the test scans were never trained on.
- `an1-r2.onnx` additionally fine-tunes on the training split of Siriapisith T. et al., "Abdominal Aortic Aneurysm
  CT Dataset (Pre- and Post-EVAR)", Figshare 10.6084/m9.figshare.19090052; licensed CC BY 4.0 (strictly held-out
  AAA_Test and EVAR_Test splits were excluded from training and validation).

External UWA 4D-CTA abdominal aortic aneurysm sets (Zenodo 10.5281/zenodo.15477710 and 19182978, CC BY 4.0) were not
used for training (the 10-patient set was used strictly for held-out evaluation).

Changes from the source data: the abdominal aorta's range cropped around the vessel; labels merged into four classes
(background, aorta outer wall, iliac artery, IVC or iliac vein); slices resampled to a 1.0 mm grid around the aorta
with +/-3 mm neighbour context; training-time augmentation (shift, scale, rotation, intensity, noise).

Licence of this model file: the training data is CC BY 4.0, which allows a derived model to be shared with this
attribution.
