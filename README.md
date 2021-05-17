# SHAPEAI PYTHON AND DEEP LEARNING BOOTCAMP

Hi I made this project during the 7 Days Free Bootcamp, conducted by <b> SHAPEAI

</b>.

The instructor during the session was Mr. Shaurya Sinha (Data Analyst Intern at Jio). I got to

learn a lot during these 7 days and it was an amazing experience learning with SHAPEAI.

<br><br>Here's the link for you to watch the sessions as well<br>

<a href="https://www.youtube.com/playlist?list=PL7zl8TDRnbune5TnrfBgFbxT87E98cfo9"> <img src="https://github.com/ShapeAI/PYTHON-AND-DATA-ANALYTICS/blob/main/Python_and_deep_learning.png"> </a>

<br>I got to have hands on experience on:

<li>Python

<li>Tensorflow

<li>Deep Learning

<br>during these 7 days, and everything was explained from the very basics so that

anyone with zero experience on programming can learn.

I enjoyed these 7 days, you can as well. To register for next free 7 days bootcamp, visit:

www.shapeai.tech

or follow SHAPEAI on:

<li><a href=

"https://in.linkedin.com/company/shapeai">LinkedIn</a>

<li><a href=

"https://www.instagram.com/shape.ai/?hl=en">Instagram</a>

<li><a

href=

"https://www.youtube.com/channel/UCTUvDLTW9meuDXWcbmISPdA">YouTu

be</a>

<li><a href=

"https://github.com/shapeai">GitHub</a>

{
  "nbformat": 4,
  "nbformat_minor": 0,
  "metadata": {
    "colab": {
      "name": "Adarsh_K.ipynb",
      "provenance": []
    },
    "kernelspec": {
      "name": "python3",
      "display_name": "Python 3"
    },
    "language_info": {
      "name": "python"
    }
  },
  "cells": [
    {
      "cell_type": "code",
      "metadata": {
        "id": "zSB-TmSRfCzY"
      },
      "source": [
        " from keras.datasets import mnist\n",
        "data = mnist.load_data()"
      ],
      "execution_count": null,
      "outputs": []
    },
    {
      "cell_type": "code",
      "metadata": {
        "id": "880w0KsJfRfN"
      },
      "source": [
        " ((x_train, y_train),(x_test ,y_test))  = data"
      ],
      "execution_count": null,
      "outputs": []
    },
    {
      "cell_type": "code",
      "metadata": {
        "id": "8diKj7IOfWwZ"
      },
      "source": [
        " x_train = x_train.reshape((x_train.shape[0], 28*28)).astype('float32')\n",
        "x_test = x_test.reshape((x_test.shape[0], 28*28)).astype('float32')"
      ],
      "execution_count": null,
      "outputs": []
    },
    {
      "cell_type": "code",
      "metadata": {
        "id": "Roo2MI4LfbnR"
      },
      "source": [
        " x_train = x_train / 255\n",
        "x_test = x_test / 255"
      ],
      "execution_count": null,
      "outputs": []
    },
    {
      "cell_type": "code",
      "metadata": {
        "id": "WHFCt20Off7P"
      },
      "source": [
        " from keras.utils import np_utils\n",
        "y_train = np_utils.to_categorical(y_train)\n",
        "y_test = np_utils.to_categorical(y_test)\n",
        "num_classes = y_test.shape[1]\n",
        "print(y_test.shape)"
      ],
      "execution_count": null,
      "outputs": []
    },
    {
      "cell_type": "code",
      "metadata": {
        "id": "lWzLoEF5fjb9"
      },
      "source": [
        " from keras.models import Sequential\n",
        "from keras.layers import Dense"
      ],
      "execution_count": null,
      "outputs": []
    },
    {
      "cell_type": "code",
      "metadata": {
        "id": "DCpwsAoPfoEr"
      },
      "source": [
        " model = Sequential()\n",
        "model.add(Dense(32, input_dim = 28*28, activation= 'relu'))\n",
        "model.add(Dense(64, activation='relu'))\n",
        "model.add(Dense(10, activation='softmax'))"
      ],
      "execution_count": null,
      "outputs": []
    },
    {
      "cell_type": "code",
      "metadata": {
        "id": "nqIzVMROfrcT"
      },
      "source": [
        " model.compile(loss='categorical_crossentropy', optimizer='adam', metrics=['accuracy'])"
      ],
      "execution_count": null,
      "outputs": []
    },
    {
      "cell_type": "code",
      "metadata": {
        "id": "WZcba1QHfvJv"
      },
      "source": [
        " model.summary()"
      ],
      "execution_count": null,
      "outputs": []
    },
    {
      "cell_type": "code",
      "metadata": {
        "id": "gZa5wb-6gxRX"
      },
      "source": [
        " score = model.evaluate(x_test, y_test)\n",
        "print(score)"
      ],
      "execution_count": null,
      "outputs": []
    },
    {
      "cell_type": "code",
      "metadata": {
        "id": "AIV_tWTLg0aN"
      },
      "source": [
        ""
      ],
      "execution_count": null,
      "outputs": []
    }
  ]
}
