# Crash Course in Deep Learning with Google TensorFlow/Python

TensorFlow examples from: 
https://www.udemy.com/tensorflow-getting-started

## Installing TensorFlow

### Using TensorFlow in docker:
https://www.tensorflow.org/install/docker
```
docker pull tensorflow/tensorflow:latest-py3-jupyter
docker run -it --rm tensorflow/tensorflow:latest-py3-jupyter \
    python -c "import tensorflow as tf; tf.enable_eager_execution(); \
               print(tf.reduce_sum(tf.random_normal([1000, 1000])))"
docker run -it tensorflow/tensorflow:latest-py3-jupyter bash
docker run -it -p 8888:8888 tensorflow/tensorflow:latest-py3-jupyter
docker run -it --rm -v $PWD:/tmp -w /tmp \
    tensorflow/tensorflow:latest-py3-jupyter python \
    ./01_installation-test.py
```

### Install TensorFlow with anaconda:
http://docs.anaconda.com/anaconda/install/linux/
* install tensorflow package in anaconda-navigator
* or install it with anaconda CLI (FIXME)

If you choose not to activate anaconda virtualenv by default then you can activate it with:
```
conda activate
```

## Running the examples

### House price prediction example

This example can be executed in docker or in Spyder,
but it contains animation with matplotlib which will be visible only if executed in local terminal:
```
python 02_House-Price-Prediction-with-anim.py
```

### Simple handwritten digit recognition with MNIST data set

```
python 03_SimpleMNIST.py
```
or executing it in docker:
```
docker run -it --rm -v $PWD:/tmp -w /tmp \
    tensorflow/tensorflow:latest-py3-jupyter \
    python ./03_SimpleMNIST.py
```
the result:
```
Test Accuracy: 90.74%
```

### MNIST handwritten digit recognition with convolutional Neural Network

```
python 04_DeepMNIST.py
```
the result:
```
Test accuracy 96.390%
```

### MNIST example with TensorBoard

```
python 05_DeepMNIST_TensorBoard.py
```
in a new terminal:
```
tensorboard --logdir ./tb_logs/
```

### Recognize birds with transfer learning using Google Inception

```
python 06_retrain.py --image_dir ./bird_photos/train/
python 07_try-retrain.py <IMAGE>
```
