# Optimization of VLSI chip area using Mixed Integer Linear Programming

NOTE: This repository uses the cvxpy library in Python to solve the problem. Click [here](https://github.com/ShuvoNewaz/MILP-VLSI-Floorplanning-CPP) to view the repository in C++.

To use this repository, please follow these steps:

- Clone this repository or download as a zip.
- Make sure your system has Anaconda installed. Open a terminal to the root directory and enter the following command: "conda env create -f environment.yml". This will create a conda environment with the required libraries.
- This project makes use of an LP-solver named MOSEK. The tool can be downloaded and the license can be obtained from https://www.mosek.com/resources/getting-started/. Once registered, follow the instructions regarding the directory setup for MOSEK in the email.
- The environment is now ready. Activate the environment by typing
    "conda activate MILP_Floorplan"
- A trial run can be performed as follows:
    "python main.py --num_blocks 30 -u True -sa True --runtime 15 -vis True -lp True"

The command above takes the file with 30 modules and runs a successive augmentation technique for faster optimization. Each superblock is given 15 seconds to optimize, and the superblock is visulized after optimized. The final floorplan created using the superblocks is also visualized and the dimensions are stored. It also generates a *.lp formatted file which can be used with the LPSolve tool (https://sourceforge.net/projects/lpsolve/) to optimize. Note: the LPSolve tool takes forever to optimze a 30-module system. Try with a 5 or 10-module system first.