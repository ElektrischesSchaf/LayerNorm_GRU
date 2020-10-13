- [LayerNorm GRU](#LayerNorm-GRU) <br>
    - [Why we need LayerNorm](#Why-we-need-LayerNorm) <br>
    - [What is LayerNorm in GRU](#What-is-LayerNorm-in-GRU) <br>
    - [How does it improve our model](#How-does-it-improve-our-model) <br>
    - [References](#References) <br>

# LayerNorm GRU
* Implement layer normalization GRU in pytorch, followed the instruction from the paper [Layer normalization](https://arxiv.org/abs/1607.06450).
* Code modified from [this repository](https://github.com/seba-1511/lstms.pth/blob/master/lstms/lstm.py).
* Environment: [Official pytorch docker image](https://hub.docker.com/r/pytorch/pytorch/tags) from [Docker Hub](https://hub.docker.com/) ```pytorch/pytorch:1.4-cuda10.1-cudnn7-runtime```

## Why we need LayerNorm
Activation functions, such as tanh and sigmoid,
![](/Figures/sigmoid_and_tanh.png)  
have saturation area, as showed the their first derivatives 
![](/Figures/derivative_sigmoid_and_tanh.png)  
For the values outside (-4, +4), the output will be very close to zero, and their gradients might also vanish, incurring the gradient vanishing problem.  

## What is LayerNorm in GRU
The structure of a GRU cell ![](/Figures/GRU_cell.png) has two tanh and one sigmoid function, with the equation: 
![](/Figures/GRU_eq.png)  
and the equation of a LN-GRU cell is: 
![](/Figures/LN-GRU_eq.png)  
For more insight, where we simulate two extreme distributions of data:
![](/Figures/activation_histogram_before.png)
After passing them into LayerNorm, the new distributions lie inside (-4, +4), perfect working area for activation functions.
![](/Figures/activation_histogram_after.png)

## How does it improve our model
The result from one of my research in BCI (Brain-computer interface)
![](/Figures/loss_to_epoch.png)

## References
Ba, Jimmy Lei, Jamie Ryan Kiros, and Geoffrey E. Hinton. "Layer normalization." arXiv preprint arXiv:1607.06450 (2016)