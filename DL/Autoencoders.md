
Parts:
1. Encoder
	1. Embeds the input to latent space.
2. Decoder
	1. Decodes the embedded vector from latent space to reconstruct the original input.

**Loss free encoding:** If $\hat x$ is constructed perfectly($x=\hat x$) from $h$.  

**Under complete:** $dim(h) \lt dim(x)$.  
- Can be used for embedding.

**Over complete:** $dim(h) \ge dim(x)$.  
- The model trivially map $x \to \hat x$. Copy $x$ to $h$.

Autoencoder is equivalent to PCA if:
1. Linear encoder and decoder is used.
2. Squared error loss function is used.
3. Inputs are normalized.

Preventing overfitting:
1. [Regularization](./Preventing%20Overfitting.md)
2. Tie weights of the encoder and decoder: $W^\ast = W^T$

Denoising autoencoder: Denoising is the inherent characteristic of auto encoders.  
To train noise is added to the input and trained as usual.  

