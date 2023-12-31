# Modified_Bprime

In this repository we provide code to generate unified B' tables with positive and negative normalized mass flux. The underlying theory is presented in Padovan, A. et al., "An extended B' formulation for ablating-surface boundary conditions," <i> Int. J. of Heat and Mass Transfer </i>, 2023 available [here](https://www.sciencedirect.com/science/article/pii/S0017931023009158?dgcid=author).

## Dependencies
- [Mutation++](https://github.com/mutationpp/Mutationpp) (and dependencies therein). 
- Python modules `numpy` `pandas` `subprocess` `scipy`

## Instructions
- Install Mutation++ following their [installation guide](https://github.com/mutationpp/Mutationpp/blob/master/docs/installation.md#top)
- Clone the `Modified_Bprime` repo into the local directory `Modified_Bprime_cloned`
- `cd Modified_Bprime_cloned && cmake .` 
- `make generate_bprime_tables` (the file `generate_bprime_tables.cpp` is a modified version of the file `bprime.cpp` available in `${MPP_DIRECTORY}/src/apps`)
- `python3 generate_table.py`
- This should have generated a file `Bprime_table.bpt` containing the modified Bprime table

## Debugging hints
- Check that Mutation++ is properly installed by running their [tests](https://github.com/mutationpp/Mutationpp/blob/master/docs/installation.md#top)
- If running on Linux, check if the Mutation++ library way installed in `${CMAKE_INSTALL_PREFIX}/lib` or `${CMAKE_INSTALL_PREFIX}/lib64`. Then, verify that the correct path is used in the `target_link_libraries()` command in the `CMakeLists.txt` file that ships with the `Modified_Bprime` repository.
