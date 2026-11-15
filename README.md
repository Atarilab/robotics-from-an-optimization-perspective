# Robotics from an Optimization Perspective

Companion code for **Robotics from an Optimization Perspective: From Foundations to Contact-rich Systems**, by Majid Khadiv, ATARI Lab, Technical University of Munich.

The examples support the book and the courses **Foundations of Modern Robotics** and **Contact-rich Robotics: An Optimization Perspective**.

Examples are added incrementally as the teaching material develops.

## Available examples

| Lecture | Notebook | Interactive output |
| --- | --- | --- |
| L3, slides 32–33 | [Screw motion](L3_screw_motion.ipynb) | [Download the standalone GUI](L3_screw_motion.html) |

The L3 notebook replaces the external screw-axis demo with an editable, reproducible course example. Enter a target pose using rotation angles and a position, edit its homogeneous matrix, or specify screw parameters. The GUI animates the frame and a rigid body, draws the screw axis and point paths, and decomposes point velocity into rotation and translation. Presets cover an offset helix, pure rotation, pure translation, the slide-33 worked example, a half-turn, and identity motion.

### Run the notebook

Use Python 3.10 or later, from the repository directory:

```bash
python -m venv .venv
source .venv/bin/activate
python -m pip install -r requirements.txt
jupyter lab L3_screw_motion.ipynb
```

On Windows, activate the environment with `.venv\Scripts\activate` instead. Select **Run All Cells**. The notebook displays the GUI and writes `L3_screw_motion.html` in its working directory. Open that HTML file directly for a full browser view. It includes Plotly.js and works offline, with no Python kernel needed after generation. GitHub's notebook preview does not run interactive code.

The notebook includes numerical checks against SciPy's matrix exponential. Its browser formulas were also cross-checked on near-zero and half-turn rotations. All twists use `(v, omega)`, linear components first.

## Planned coverage

Examples will be organized by book chapter, with references to the corresponding lectures.

| Book chapters | Topics |
| --- | --- |
| 2 | Configuration spaces, degrees of freedom, and topology |
| 3 | Rigid-body motion, rotations, poses, and Lie-group operations |
| 4–6 | Forward kinematics, Jacobians, acceleration kinematics, and inverse kinematics |
| 7 | Robot dynamics |
| 8–11 | Motion planning, control, optimal control, and reinforcement learning |
| 12–16 | Contact geometry, contact models, contact planning and control, and learning |
| Appendices | Lie theory, optimization, and holonomic/nonholonomic constraints |

The initial examples will use Python, NumPy, and Matplotlib, with Pinocchio for robot-model computations. Each example will include a run command, its dependencies, and the expected result.

## Notation and implementation conventions

- `T_ab` maps coordinates from frame `b` to frame `a`.
- Twists use translation-first ordering: `(v, omega)`.
- Wrenches use force-first ordering: `(f, moment)`.
- Hat and vee convert between vector coordinates and Lie-algebra matrices.
- `M(q)` denotes the mass matrix, `N` a null-space projector, and `Z` a null-space basis.
- Examples state coordinate frames, reference points, and units explicitly.
- Quaternion storage order is declared at each library interface.
- Configuration updates use manifold integration when ordinary vector addition is not appropriate.

## Adding an example

Keep each example focused on a concept from the book. Include its chapter/section reference, a short explanation, a reproducible run command, and a simple check against a known result. Record the source and license of any external robot model or dataset.

Examples intended for a simulator should identify that simulator and its required version. Hardware-specific instructions belong with the corresponding example.

## About

[ATARI Lab — Applied and Theoretical Aspects of Robot Intelligence](https://www.ce.cit.tum.de/en/aipd/home/), Technical University of Munich.
