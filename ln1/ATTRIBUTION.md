# LN1 - neck lymph node level model: data and attribution

`ln1-r1.onnx` labels neck lymph node LEVELS (right/left II, III, Va, IV, Vb+Vc, Ib) on one standard axial CT image,
from true Hounsfield units. It was trained by the MosaicTools author; nothing here is endorsed by the dataset authors.

Trained on:
- LNCTVSeg - lymph node clinical target volumes of the neck, 290 CT cases (Luo X. et al.; github.com/Luoxd1996/LNCTVSeg),
  figshare 10.6084/m9.figshare.26793622, licensed CC BY 4.0. Its grouped volumes (II+III+Va, IV+Vb+Vc, Ib per side) were
  split into single levels by the 2013 consensus landmarks (hyoid body edges; the posterior border of the
  sternocleidomastoid), found with TotalSegmentator's head-and-neck tasks (Apache-2.0).
- TotalSegmentator CT dataset v3 - Wasserthal J. et al., Radiology: Artificial Intelligence 2023 (CC BY 4.0): slices
  without a neck, as "no level here" examples.

Changes from the source data: resampled to 1 mm, cropped about the body, level splits added as described above.
