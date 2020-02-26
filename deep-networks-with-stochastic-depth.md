# Deep Networks with Stochastic Depth

Huang, G., Sun, Y., Liu, Z., Sedra, D., & Weinberger, K. Q. (2016, October). Deep networks with stochastic depth. In European conference on computer vision (pp. 646-661). Springer, Cham.

## Paper Summary

The authors propose a dynamic layer skipping scheme for deep neural networks that reduced training time significantly but allows for competitive performance on benchmark tasks.

## Background and Research Problem
They review 3 core issues with training very deep neural networks:

Vanishing gradients: as gradients-based adjustments are propagated through the layers of a network, smaller weight magnitudes lead to lesser impact on earlier weights. Skip connections and batchnorm help this.

Diminishing reuse of features: representations from earlier layers don't inform later ones for similar reasons to the vanishing gradient issue. Resnets aim to fix this through identity skip connections.

Long training time: training of deeper networks is intuitively more time and compute intensive.

One of the key issues in Deep Learning, both at the time of writing this paper and today, is that small networks are not expressive enough to tackle complex problems, but large ones face serious learning problems (see above) through the current training schemes.

### Proposed Solution
The authors propose a mechanism to skip layer updates stochastically, through a decaying probability. At training, layers may or may not get updated, so computation is saved. At testing, all layers are involved, allowing for utilization of the whole network. Another perspective on this is that a given resnet becomes an ensemble of many smaller resnets that are basically graphs with skipped portions. The results are more than competitive.
