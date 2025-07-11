---
layout: post
title: Transformer Architecture
---

This project implements a Transformer block from scratch, using PyTorch for tensor operations and certain pre-built layers. The block consists of the following components:

## Diagram
<img src="/images/transformer_block.png" alt="Transformer Block Diagram" width="600"/>

- **Layer Normalization**: A from-scratch implementation of [`LayerNorm`](https://github.com/amruth6002/Transformer_Block/blob/main/Transformer_Block.ipynb). It uses `nn.Parameter` for trainable scale and shift parameters.
- **Masked Multi-Head Attention**: The [`MultiHeadAttention`](https://github.com/amruth6002/Transformer_Block/blob/main/Transformer_Block.ipynb) logic is implemented from scratch. It utilizes PyTorch's `nn.Linear` for the weight matrices and `nn.Dropout`.
- **Dropout**: Applied via PyTorch's `nn.Dropout` for regularization within the attention mechanism and on the residual connections.
- **Shortcut Connections (Residual Connections)**: Implemented by adding the input of a sublayer to its output.
- **Feed Forward Network**: A [`FeedForward`](https://github.com/amruth6002/Transformer_Block/blob/main/Transformer_Block.ipynb) network that uses PyTorch's `nn.Linear` layers and a custom-implemented `GELU` activation function.

## Implementation Details

- The configuration for the Transformer block is defined in the `GPT_CONFIG_124M` dictionary. This includes parameters such as embedding dimension, number of attention heads, and dropout rate.
- The [`TransformerBlock`](https://github.com/amruth6002/Transformer_Block/blob/main/Transformer_Block.ipynb) class combines all the components into a single block.

## Usage

An example implementation is provided in the notebook to demonstrate how to use the `TransformerBlock`.

```python
# example implementation
torch.manual_seed(123)
x = torch.rand(2, 4, 768)
block = TransformerBlock(GPT_CONFIG_124M)
output = block(x)
print("Input Shape:", x.shape)
print("Output shape:", output.shape)
```
