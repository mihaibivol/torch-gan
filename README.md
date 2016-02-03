## Alter models from [skaae/torch-gan](https://github.com/skaae/torch-gan) to generate [Cyanide and Happyness](http://explosm.net/) Comics

Main differences:
* Reduce feature map size so we can train on a lapotp
* Add an extra layer for phun


## Torch convolutional GAN
To run the code clone the repository

```
git clone https://github.com/skaae/torch-gan.git
```

`cd` to the `datasets` subfolder and run `./download.sh`. This will download an awesome collage of C&H Comics. See [this notebook](dataset_explorer) for a sample of the dataset.

Then run

```
th train.lua -g 0 -b 20
```

You can try bigger batches if you haz the RAM for it.

where `-g 0` specifies the GPU you want to use. The code will only run on GPU, but you can easily modify to run on CPU by removing the cudnn dependencies.

The code will plot ~~100~~  20 generated images after each epoch because we don't have enough memory to plot 100.
After a 5-10 epochs you should see something that has the shapes of a C&H comic.

The code was written by [Anders Boesen Lindbo Larsen](https://github.com/andersbll) and [Søren Kaae Sønderby](https://github.com/skaae). Our code is based on code released with the [LAPGAN paper](https://github.com/facebook/eyescream). 

#### 100 Epochs, Few Feature maps



##### Dependencies
 *  Torch
 *  numpy
 *  skimage
 *  h5py
 *  [torch hdf5](https://github.com/deepmind/torch-hdf5)
 *  [cudnn for torch](https://github.com/soumith/cudnn.torch)
