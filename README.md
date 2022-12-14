# reducedTOGL

I have dismantled the original [TOGL](https://github.com/BorgwardtLab/TOGL) repo to only contain the TopologyLayer and adapted it so that it can be dropped in like any other layer. This is a work in progress and not all kwargs are supposed to work correctly yet. 

## Installation

The safest route is to first install `torch==1.12.1`, [then torch_persistent_homology](https://github.com/ExpectationMax/torch_persistent_homology) by cloning it and installing it via `pip install .` in its own directory, then the rest of the requirements. Finally, if you have everything installed that is listed in the `requirements.txt`, proceed with `pip install --no-deps .`. Tested with Python 3.7.13 in an Ubuntu 20.04 Docker Container within a conda env.

## Usage

```
$ python
Python 3.7.13 (default, Mar 29 2022, 02:18:16) 
[GCC 7.5.0] :: Anaconda, Inc. on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> from topognn import TopologyLayer
>>> import torch
>>> import torch_geometric as pyg
>>> edge_index = torch.tensor([[0, 1],
                           [1, 0],
                           [1, 2],
                           [2, 1]], dtype=torch.long)
>>> x = torch.tensor([[-1], [0], [1]], dtype=torch.float)
>>> data = pyg.data.Data(x=x, edge_index=edge_index.t().contiguous())
>>> layer = TopologyLayer(1,1)
>>> layer(data.x, data.edge_index)
(tensor([[0.1042],
        [0.1311],
        [0.1822]], grad_fn=<ReluBackward0>), None, None)
```
