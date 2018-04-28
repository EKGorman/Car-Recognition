# Facial Expression Prediction


This repository is to do car recognition by fine-tuning ResNet-152 with Cars Dataset from Stanford.


## Dependencies

- [NumPy](http://docs.scipy.org/doc/numpy-1.10.1/user/install.html)
- [Tensorflow](https://www.tensorflow.org/versions/r0.8/get_started/os_setup.html)
- [Keras](https://keras.io/#installation)
- [OpenCV](https://opencv-python-tutroals.readthedocs.io/en/latest/)

## Dataset

We use the Cars Dataset, which contains 16,185 images of 196 classes of cars. The data is split into 8,144 training images and 8,041 testing images, where each class has been split roughly in a 50-50 split.

 ![image](https://github.com/foamliu/Car-Recognition/raw/master/images/random.png)

You can get it from [Cars Dataset](https://ai.stanford.edu/~jkrause/cars/car_dataset.html), make sure cars_train.tgz, cars_test.tgz and car_devkit.tgz are is in mart folder:

```bash
$ mkdir mart
$ cd mart
$ wget http://imagenet.stanford.edu/internal/car196/cars_train.tgz
$ wget http://imagenet.stanford.edu/internal/car196/cars_test.tgz
$ wget https://ai.stanford.edu/~jkrause/cars/car_devkit.tgz
```

## ImageNet Pretrained Models

Download [ResNet-152](https://drive.google.com/file/d/0Byy2AcGyEVxfeXExMzNNOHpEODg/view?usp=sharing) into imagenet_models folder.

## Usage

### Data Pre-processing
Extract 8,144 training images, and split them by 80:20 rule (6,549 for training, 1,595 for validation):
```bash
$ python pre-process.py
```
 When complete, folder structure looks like:

 ![image](https://github.com/foamliu/Car-Recognition/raw/master/images/data.png)

### Train
```bash
$ python train.py
```
 ![image](https://github.com/foamliu/Car-Recognition/raw/master/images/train.png)

If you want to visualize during training, run in your terminal:
```bash
$ tensorboard --logdir path_to_current_dir/logs
```

### Analysis
Use 8,041 testing images for result analysis.


### Predict
```bash
$ python predict.py --i [image_path]
```