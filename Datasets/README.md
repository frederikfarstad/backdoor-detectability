# Datasets

This folder is intentionally empty in the repository — datasets are not
shipped with the source. Download or symlink them here as needed before
running the detection or attack code.

Expected layout (created on first use):

```
Datasets/
├── cifar-10-batches-py/      # CIFAR-10, from torchvision or the original 
├── MNIST/                    # torchvision MNIST cache (raw/ + processed/)
└── Imagenette/               # https://github.com/fastai/imagenette
```

The first time you run a config that needs a dataset, the corresponding
adapter / data loader will either download it automatically (torchvision
defaults) or fail with a clear error pointing at the missing path.
