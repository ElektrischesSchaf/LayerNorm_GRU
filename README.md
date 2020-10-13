## LayerNorm_GRU
* Implement layer normalization GRU in pytorch, followed the instruction from the paper [Layer normalization](https://arxiv.org/abs/1607.06450).
* Code modified from [this repo](https://github.com/seba-1511/lstms.pth/blob/master/lstms/lstm.py).
* Environment: Docker image ```pytorch/pytorch:1.4-cuda10.1-cudnn7-runtime```

### Why we need LayerNorm
Activation functions ![](/Figures/sigmoid_and_tanh.png) have saturation area, as showed the their first derivatives ![](/Figures/derivative_sigmoid_and_tanh.png).


### What is LayerNorm in GRU
The structure of a GRU cell ![](/Figures/GRU_cell.png) has two tanh and one sigmoid function, 

![](/Figures/activation_histogram_after.png)

### How does it improve our model

The result from one of model for BCI 
![](/Figures/loss_to_epoch.png)

## References
Ba, Jimmy Lei, Jamie Ryan Kiros, and Geoffrey E. Hinton. "Layer normalization." arXiv preprint arXiv:1607.06450 (2016)