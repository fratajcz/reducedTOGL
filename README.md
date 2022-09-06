# reducedTOGL

I have dismantled the original [TOGL](https://github.com/BorgwardtLab/TOGL) repo to only contain the TopologyLayer and adapted it so that it can be dropped in like any other layer. This is a work in progress and not all kwargs are supposed to work correctly yet. 

## Installation

The safest route is to first install `torch==1.12.1`, [then torch_persistent_homology](https://github.com/ExpectationMax/torch_persistent_homology) by cloning it and installing it via `pip install .` in its own directory, then the rest of the requirements. Finally, if you have everything installed that is listed in the `requirements.txt`, proceed with `pip install --no-deps .`. Tested with Python 3.7.13 in an Ubuntu 20.04 Docker Container within a conda env.
