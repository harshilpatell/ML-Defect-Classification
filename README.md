# ML-Defect-Classification

This project applies supervised machine learning to XRD diffractogram data to automatically classify structural defects in materials.It extracts physically meaningful features from each detected peak — FWHM, d-spacing, crystallite size (Scherrer equation), and lattice strain (Williamson-Hall) — and trains five ML classifiers to assign a defect class to every peak.

What Data You Can Upload
Any two-column XRD scan file where the first column is the 2θ angle (degrees) and the second is intensity (counts). Supported formats are .xlsx or .xls.

The model processed 7,001 data points across 10–80°, detected 22 peaks, and classified each one:
Defect Class                    Peaks Found
Stacking Fault                       8
Amorphous Disorder                   6
Perfect Crystal                      5
Dislocation / Grain Boundary         3

The best model (Random Forest) hit 83.3% accuracy with 81.2% cross-validation mean. The three features that mattered most for telling defects apart were integral breadth, lattice strain, and crystallite size — all physically meaningful, not arbitrary. The output is a labeled peak table (CSV) plus a 7-panel visualization showing the annotated diffractogram, model comparison, confusion matrix, and feature importance chart.
