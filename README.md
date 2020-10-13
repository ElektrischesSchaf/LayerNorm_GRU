## LayerNorm_GRU
* Implement layer normalization in GRU, followed the instruction by [this paper](https://arxiv.org/abs/1607.06450).
* Code modified from [this repo](https://github.com/seba-1511/lstms.pth/blob/master/lstms/lstm.py).

### Why we need LayerNorm
Activation functions ![](/Figures/sigmoid_and_tanh.png) have saturation area, as showed the their first derivatives ![](derivative_sigmoid_and_tanh.png).


## References
Ba, Jimmy Lei, Jamie Ryan Kiros, and Geoffrey E. Hinton. "Layer normalization." arXiv preprint arXiv:1607.06450 (2016)