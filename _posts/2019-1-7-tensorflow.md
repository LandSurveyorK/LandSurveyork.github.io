---
layout: post
title: Quotes About Tensorflow
---

众多科技巨头在其商业chanp里使用了tensorflow框架。例如ARM,Google, Intel, eBay, Qualcomm, SAM, Dropbox, Twitter

* 关于tensorflow的安装(cpu版) [tensorflow configuration](https://plus.google.com/+PENGWEI-AI/posts/AEcDEXnZzLN)
  似乎 pip install tensorflow,(pip install keras) 比conda install 靠谱一些，以为pip会将重复，不兼容的文件去掉。
  折腾tensorflow用了好长时间，下次安装package的时候还是得注意兼容问题。
  
  * 测试是否成功安装
  
  ''' python
  import tensorflow as tf 
  hello = tf.constant("Hello, World")
  sess = tf.Session()
  print(sess.run(hello))
  '''
   
* tf.layers, tf.metrices, tf.losses, tf.keras这几个模块使得tensorflow十分适用于高级别神经网络运算;
* Tensorflow提供了一个非常灵活的构架，使得你可以仅仅用一个API在桌面，服务器或者移送设备等平台上的一个或者多个CPU或者GPU上部署运算;
* Tensorflow能够自动对内存的使用和数据进行管理和优化。现在，可以使用NIVIDA，cuDNN和CUDA工具包，在自己的计算机上进行大规模，数据密集型GPU运算;
* 可扩展，有强大的community


Keras:

Keras is a high-level neural networks API, written in Python and capable of running on top of Tensorflow, CNTK, Theano. 
It was developed witha focus on enabling fast experimentation Beging able to go from idea to result with the least possible delay is 
key to doing good reasearch.

* Allows for easy and fast prototyping
* Suports both convolution networks and recurrent networkds, as well as conbinations of the two
* Runs seamlessly on CPU and GPU

''' python
import keras
from keras.models import Sequential
model = Sequential()
from keras.layers import Dense
model.add(Dense(units=64,activation='relu',input_dim=100))
model.add(Dense(units=10,activation='softmax'))
# model.compile(loss='categorical_crossentropy',
             optimizer = 'sgd',
             metrics = ['accuracy'])
model.compile(loss=keras.losses.categorical_crossentropy,
             optimizer=keras.optimizers.SGD(lr=0.01,momentum=0.9,nesterov=True))

model.fit(x_train, y_trian, epochs = 5, batch_size=32)
loss_and_metrics = model.evaluate(x_text,y_test,batch_size=128)
classes = model.predict(x_text,batch_size=128)

'''
