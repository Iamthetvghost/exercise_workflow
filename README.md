# exercise_workflow
This notebook presents a reproducible workflow for identifying halo eclipsing binary candidates from a sample of ZTF eclipsing binaries.

## Overview

The workflow uses astrometric and radial-velocity information to calculate
stellar positions and velocities, estimate the total orbital energy and
the z-component of angular momentum, and visualize the stellar population
in an energy–angular momentum ($E-L_z$) diagram.

The original analysis was developed as part of a bachelor thesis project.
This repository organizes and documents the workflow to make the
computational procedure easier to understand and reproduce.

## Workflow

The analysis consists of the following steps:

1. Load the ZTF eclipsing binary catalogue.

2. Extract right ascension, declination, proper motions, parallax, and
   radial velocity.

3. Estimate stellar distances from parallaxes.

4. Calculate stellar positions in a simplified Galactocentric coordinate
   system.

5. Estimate stellar velocities and correct them for the Solar motion and
   the Local Standard of Rest.

6. Calculate the total energy and the z-component of angular momentum.

7. Select halo candidates using the criterion

   $\frac{J_\phi}{J_{\mathrm{tot}}} \leq 0.6$.

8. Visualize the results in an $E-L_z$ diagram.

## Repository Structure

```text
ZTF-halo-EB-workflow/
├── README.md
├── LICENSE
├── environment.yml
├── ZTF_halo_EB.ipynb
└── data/
    └── ZTFEB.csv
```

## Requirements

The workflow is written in Python and uses:

* NumPy
* pandas
* Matplotlib
* Jupyter Notebook

The exact package versions are specified in `environment.yml`.

## How to Run

Clone or download this repository and make sure the required Python
environment is available.

Create the environment using:

```bash
conda env create -f environment.yml
```

Activate it with:

```bash
conda activate ztf-halo-eb
```

Then launch Jupyter Notebook:

```bash
jupyter notebook
```

Open `ZTF_halo_EB.ipynb` and run the cells sequentially.

The input catalogue should be located at:

```text
data/ZTFEB.csv
```

The workflow saves the resulting energy–angular momentum figure in the
data directory.

## Data

The workflow requires a catalogue containing the input quantities used in
the notebook, including:

* `ra`
* `dec`
* `pmra`
* `pmdec`
* `parallax`
* `radial_velocity`

If the original catalogue cannot be redistributed, the data should be
obtained from the appropriate original source and placed in the `data/`
directory.

## Limitations

The workflow uses simplified physical assumptions.

The gravitational potential is represented by a simple $-1/r$ potential
rather than a detailed Milky Way potential. The position and velocity
transformations are also simplified and are implemented directly in the
notebook.

Therefore, the resulting energy and halo classification should be
interpreted within the assumptions of this simplified model.

## Reproducibility

The computational environment is documented in `environment.yml`.
Dependency version pinning reduces the risk that future software updates
will change the behaviour of the workflow or prevent it from running.

The notebook contains the complete computational procedure and generated
figures.

## FAIR Principles

This workflow follows the FAIR principles by providing:

* **Findable:** a descriptive repository, README, metadata, and keywords.
* **Accessible:** publicly available workflow code and documented
  computational requirements.
* **Interoperable:** standard CSV data and widely used Python scientific
  computing libraries.
* **Reusable:** documented code, dependencies, workflow steps, and
  limitations.

## Keywords

ZTF, Gaia, eclipsing binaries, halo stars, stellar kinematics,
Galactic astronomy, angular momentum, orbital energy, Python,
reproducible research
