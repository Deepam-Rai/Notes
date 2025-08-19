> Quantization if model reduction technique that converts weights from high precision floats to low precision floats thus enhancing training speed, decreasing memory bandwidth, increasing cache utilization without sacrificing too much accuracy.


Some of the low precision representation are:
- `UINT8`: unsigned `INT8`
- `INT16`
`INT8` representation is colloquially considered as quantized.  



Points:
- Quantization introduce tradeoff between accuracy and model size.  
- First and last layers of the network are more sensitive towards quantization<sup>[1]</sup>, thus these layers can be computed using floating precision.

## Calibration
>We need to squeeze high dynamic range format to low dynamic range format, the estimation of this scale at which to squeeze is called calibration.

![Calibration](../Images/DL/quantization/quantization_calibration.png)

Squeezing high dynamic representation to low precision formats leads to great loss of information.  
To mitigate this challenge techniques have been developed.  


## Types
1. Quantization Aware Training(QAT)
	1. It is done during model training process.
2. Post Training Quantization(PTQ)



----
# Citations
1. M. Rastegari, V. Ordonez, J. Redmon, and A. Farhadi, “Xnor-net: Imagenet classification using binary convolutional neural networks,” CoRR, vol. abs/1603.05279, 2016. [Online]. Available: [http://arxiv.org/abs/1603.05279](http://arxiv.org/abs/1603.05279)

