# Robotics from an Optimization Perspective

Companion code for **Robotics from an Optimization Perspective: From Foundations to Contact-rich Systems**, by Majid Khadiv, ATARI Lab, Technical University of Munich.

## Find material by chapter

One folder per **book chapter**. Lecture L4 combines Chapters 4–6; lecture and chapter numbers are therefore listed separately. Only available material is linked.

| Chapter | Topic | Lecture | Material |
| --- | --- | --- | --- |
| 1 | Introduction to Modern Robotics | — | Planned |
| 2 | Configuration Space | — | Planned |
| 3 | [Rigid-Body Motion](chapters/03-rigid-body-motion/) | L3 | [Notebook](chapters/03-rigid-body-motion/01_screw_motion.ipynb) |
| 4 | [Forward Kinematics](chapters/04-forward-kinematics/) | L4 | [Notebook](chapters/04-forward-kinematics/01_planar_arm_and_pinocchio.ipynb) |
| 5 | [Velocity Kinematics](chapters/05-velocity-kinematics/) | L4 | [Jacobians and accelerations](chapters/05-velocity-kinematics/01_jacobians_and_accelerations.ipynb) · [Pinocchio analytic Jacobians and accelerations](chapters/05-velocity-kinematics/02_pinocchio_analytic_jacobians_and_accelerations.ipynb) · [Interactive manipulability](chapters/05-velocity-kinematics/03_interactive_manipulability.ipynb) |
| 6 | [Inverse Kinematics](chapters/06-inverse-kinematics/) | L4 | [Notebook](chapters/06-inverse-kinematics/01_inverse_kinematics.ipynb) |
| 7 | Robot Dynamics | — | Planned |
| 8 | Motion Planning | — | Planned |
| 9 | Robot Control | — | Planned |
| 10 | Optimal Control | — | Planned |
| 11 | Reinforcement Learning | — | Planned |
| 12 | Collision Detection and Contact Geometry | — | Planned |
| 13 | Rigid Contact and Complementarity | — | Planned |
| 14 | Compliant Contact and Deformable Models | — | Planned |
| 15 | Contact Planning and Control | — | Planned |
| 16 | Learning for Contact-rich Robotics | — | Planned |

Appendices on Lie theory, optimization, and holonomic/nonholonomic constraints will be added when examples are ready.

## Start with a lecture

- **L3:** [Screw-motion notebook](chapters/03-rigid-body-motion/01_screw_motion.ipynb) · [Open the GUI](https://htmlpreview.github.io/?https://github.com/Atarilab/robotics-from-an-optimization-perspective/blob/main/chapters/03-rigid-body-motion/screw_motion.html).
- **L4:** [Forward kinematics](chapters/04-forward-kinematics/01_planar_arm_and_pinocchio.ipynb) → [Jacobians and accelerations](chapters/05-velocity-kinematics/01_jacobians_and_accelerations.ipynb) → [Inverse kinematics](chapters/06-inverse-kinematics/01_inverse_kinematics.ipynb).
- **L4 slide 24 and slides 26–27:** [Retrieve analytic Jacobians and frame accelerations with Pinocchio](chapters/05-velocity-kinematics/02_pinocchio_analytic_jacobians_and_accelerations.ipynb), with spatial-arm and one-link worked examples.

- **L4 slides 30 and 33:** [Interactive velocity and force ellipses](chapters/05-velocity-kinematics/03_interactive_manipulability.ipynb), with joint-angle sliders and singularity examples. [Open the browser GUI](https://htmlpreview.github.io/?https://github.com/Atarilab/robotics-from-an-optimization-perspective/blob/main/chapters/05-velocity-kinematics/manipulability.html) without installing Python.

### L4 slide-to-notebook map

Numbering follows the 47-slide deck revised on 24 November 2026. Titles identify the topic if the slides are reordered later.

| Slide(s) | Topic | Notebook |
| --- | --- | --- |
| 12 | Robot descriptions: DH, PoE, and URDF | [Planar arm and Pinocchio](chapters/04-forward-kinematics/01_planar_arm_and_pinocchio.ipynb) |
| 24 | Analytic Jacobians | [Pinocchio analytic Jacobians and accelerations](chapters/05-velocity-kinematics/02_pinocchio_analytic_jacobians_and_accelerations.ipynb#analytic-jacobians) |
| 26 | Spatial acceleration | [Pinocchio acceleration examples](chapters/05-velocity-kinematics/02_pinocchio_analytic_jacobians_and_accelerations.ipynb#accelerations) |
| 27 | Constant joint speed and centripetal acceleration | [Jacobians and accelerations](chapters/05-velocity-kinematics/01_jacobians_and_accelerations.ipynb) |
| 30 | Velocity manipulability ellipse | [Interactive velocity and force ellipses](chapters/05-velocity-kinematics/03_interactive_manipulability.ipynb) |
| 33 | Force ellipsoids and reaction directions | [Browser GUI](https://htmlpreview.github.io/?https://github.com/Atarilab/robotics-from-an-optimization-perspective/blob/main/chapters/05-velocity-kinematics/manipulability.html) · [Notebook](chapters/05-velocity-kinematics/03_interactive_manipulability.ipynb) |
| 39, 41 | Numerical IK step and finite log-error Jacobian | [Inverse kinematics](chapters/06-inverse-kinematics/01_inverse_kinematics.ipynb) |

## Run the notebooks

Use Python 3.10–3.13 in an isolated environment. The examples were executed with Python 3.13, NumPy 2.3.5, and Pinocchio 3.9.0.

```bash
git clone https://github.com/Atarilab/robotics-from-an-optimization-perspective.git
cd robotics-from-an-optimization-perspective
python -m venv .venv
source .venv/bin/activate
python -m pip install -r requirements-kinematics.txt
jupyter lab
```

On Windows activate with `.venv\Scripts\activate`. For L3 alone, install `requirements.txt`; Pinocchio is not required. Its pip distribution is named **pin**, while the Python import is `pinocchio`.

Open the chapter notebook and select **Run All Cells**. Each L4 notebook contains a complete example, numerical checks, and plots; no meshes, private files, or robot assets are needed. The L3 notebook generates a self-contained HTML GUI that can be opened offline. GitHub's preview displays saved notebook outputs but does not run code.

## Repository structure

```text
chapters/
  03-rigid-body-motion/
    README.md
    01_screw_motion.ipynb
    screw_motion.html
  04-forward-kinematics/
    README.md
    01_planar_arm_and_pinocchio.ipynb
  05-velocity-kinematics/
    README.md
    01_jacobians_and_accelerations.ipynb
    02_pinocchio_analytic_jacobians_and_accelerations.ipynb
    03_interactive_manipulability.ipynb
    manipulability.html
  06-inverse-kinematics/
    README.md
    01_inverse_kinematics.ipynb
requirements.txt
requirements-kinematics.txt
```

The former root-level L3 files are compatibility entry points for existing slide links. New material belongs under `chapters/`.

## Conventions

- `T_ab` maps coordinates from frame `b` to frame `a`; frames are right-handed.
- Twists use `(v, omega)`, linear components first. Wrenches use `(force, moment)`.
- Hat/vee connect vector coordinates and Lie-algebra matrices.
- `M(q)` is reserved for the mass matrix, `N` for a null-space projector, and `Z` for a null-space basis.
- Each example states units, coordinate frames, reference origins, and quaternion ordering when relevant.
- Use manifold integration when configuration storage and tangent coordinates differ.

## Add material for a chapter

1. Use `chapters/NN-topic/` with the book's chapter number and slug. Create the folder when its first example is ready.
2. Add a short `README.md` listing the notebooks, lecture references, prerequisites, and run instructions.
3. Number notebooks in teaching order: `01_topic.ipynb`, `02_topic.ipynb`, etc. Keep each runnable from top to bottom, with a simple check and a plot where useful.
4. Put necessary model files in that chapter's `assets/` folder and credit external sources and licenses. Prefer small, original, self-contained examples.
5. Update this chapter table and lecture index. Link slides directly to the relevant notebook; avoid embedding code screenshots.
6. Run every changed notebook from a fresh kernel. Keep compact illustrative outputs; do not commit environments, checkpoints, private datasets, or large generated files.

[ATARI Lab — Applied and Theoretical Aspects of Robot Intelligence](https://www.ce.cit.tum.de/en/aipd/home/), Technical University of Munich.
