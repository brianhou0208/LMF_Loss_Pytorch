# LMFLOSS: A Hybrid Loss for Imbalanced Medical Image Classification

This is an unofficial PyTorch implementation of the Large Margin aware Focal (LMF) Loss as described in the paper: [**LMFLOSS: A Hybrid Loss For Imbalanced Medical Image Classification.**](https://arxiv.org/abs/2212.12741)

This repository provides a PyTorch implementation of the LMF Loss that combines Focal Loss and Label Distribution Aware Margin (LDAM) Loss, specifically designed for addressing class imbalance in medical image classification.

## Installation
You can use these loss functions by cloning this repository:

```bash
git https://github.com/brianhou0208/LMF_Loss_Pytorch.git
cd LMF_Loss_Pytorch
```
## Usage Example
Here is a simple example of how to use the LMF Loss in your PyTorch model:

```python
import torch
from src.losses.lmf_loss import LMFLoss
from src.losses.focal_loss import FocalLoss
from src.losses.ldam_loss import LDAMLoss

# Assume you have a model, input, and target
model = ...  # Your PyTorch model
inputs = ...  # Your input data, e.g., torch.randn(1, 1, 256, 256)
targets = ...  # Your target labels, e.g., torch.rand(1, 1, 256, 256)

# Initialize the loss functions
focal_loss = FocalLoss()
ldam_loss = LDAMLoss()
lmf_loss = LMFLoss(focal_loss, ldam_loss)

# Compute the loss
predictions = model(inputs)
loss = lmf_loss(predictions, targets)
loss.backward()  # Backpropagation

```

## Contributions
This is an open-source project, and contributions of any kind are welcome, including suggestions and bug reports.

## License
This project is licensed under the [MIT License.](https://github.com/brianhou0208/LMF_Loss_Pytorch/blob/main/LICENSE)
