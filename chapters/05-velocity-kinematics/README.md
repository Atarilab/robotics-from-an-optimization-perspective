# Chapter 5 — Velocity kinematics

Lecture: **L4** · [All chapters](../../README.md) · [Current slide-to-notebook map](../../README.md#l4-slide-to-notebook-map)

| Notebook | What it covers |
| --- | --- |
| [01 jacobians and accelerations](01_jacobians_and_accelerations.ipynb) | Reference-frame conventions, finite-difference checks, acceleration, and singularities. |
| [02 Pinocchio analytic Jacobians and accelerations](02_pinocchio_analytic_jacobians_and_accelerations.ipynb) | L4 slide 24 and slides 26–27: LOCAL/WORLD/LWA Jacobians, RPY and rotation-vector analytic Jacobians, spatial/classical accelerations, transport terms, and a one-link centripetal example. |
| [03 Interactive manipulability](03_interactive_manipulability.ipynb) | L4 slides 30 and 32: joint-angle sliders, the 2R arm, velocity/force ellipses, eigenvalues of J J^T, and singular reaction directions. |

From the repository root:

```bash
python -m pip install -r requirements-kinematics.txt
jupyter lab chapters/05-velocity-kinematics/01_jacobians_and_accelerations.ipynb
```

For analytic Jacobians (slide 24) and accelerations (slides 26–27), open `02_pinocchio_analytic_jacobians_and_accelerations.ipynb` instead. It builds its own spatial three-joint arm, verifies the formulas against finite differences, and includes saved plots and numerical results.

For slides 30 and 32, open `03_interactive_manipulability.ipynb` and run all cells to enable the sliders. It needs `requirements.txt` (including ipywidgets), without Pinocchio.

Select **Run All Cells**. Each notebook is self-contained and states frames, units, dependencies, and checks. GitHub displays saved results but does not execute notebooks.

## Browser GUI

[Open the velocity and force ellipse GUI](https://htmlpreview.github.io/?https://github.com/Atarilab/robotics-from-an-optimization-perspective/blob/main/chapters/05-velocity-kinematics/manipulability.html). Move the joint-angle sliders or select regular, straight, folded, and near-singular postures. The GUI displays the arm, both sets, the Jacobian, and principal values. No Python is needed.

For offline use, download [manipulability.html](manipulability.html) and open it in a browser. L4 slides 30 and 32 link directly to the GUI; the notebook contains the derivation and Python implementation.
