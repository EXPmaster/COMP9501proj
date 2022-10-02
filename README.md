# Repository for COMP9501 Project

Authors: Manwen Liao, Heng Zhang

This repository is based on the Pytorch implementation of [Online Deicsion Transformer](https://arxiv.org/abs/2202.05607) by [Qinqing Zheng](https://enosair.github.io/), [Amy Zhang](https://amyzhang.github.io/), and [Aditya Grover](https://aditya-grover.github.io/).


## Requirements
```console
conda env create -f conda_env.yml
source activate odt
```

### Tips
If you encounter the `libstdc++.so.6: version 'GLIBCXX_3.4.xx' not found` error, the following command might help:
```console
export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:<path-to-your-conda-env>/lib
```
I have also found that `tensorboard` wants `protobuf` version to be `3.20.x`, and this helped
```console
# you might need to uninstall dm-control
pip3 install --upgrade protobuf==3.20.0 
```

This project requires MuJoCo package, refer to [MuJoCo](https://github.com/openai/mujoco-py/blob/master/README.md) for installation.


## Example
To train an ODT agent for `hopper` with the `medium-v2` dataset:
```console
python main.py
```
This will produce the `exp` folder, where all the outputs are going to be logged including tensorboard blobs. One can attach a tensorboard to monitor training by running:
```console
tensorboard --logdir exp
```

## License
The majority of `online-dt` is licensed under CC-BY-NC, however portions of the project are available under separate license terms: 
* D4RL dataset -  Creative Commons Attribution 4.0 License (CC-BY)
* D4RL code, transformers, Lamb - Apache 2.0 License
* stable-baselines3, Gym, decision-transformer - MIT License

