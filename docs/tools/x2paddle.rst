模型转换工具 X2Paddle
=====================

X2Paddle可以将caffe、tensorflow、onnx模型转换成Paddle支持的模型。

`X2Paddle <https://github.com/PaddlePaddle/X2Paddle>`_ 支持将Caffe/TensorFlow模型转换为PaddlePaddle模型。目前X2Paddle支持的模型参考 `x2paddle_model_zoo <https://github.com/PaddlePaddle/X2Paddle/blob/develop/docs/introduction/x2paddle_model_zoo.md>`_ 。


多框架支持
----------------

================  =====  ==========  ====
      模型        caffe  tensorflow  onnx
================  =====  ==========  ====
mobilenetv1       Y      Y           F
mobilenetv2       Y      Y           Y
resnet18          Y      Y           F
resnet50          Y      Y           Y
mnasnet           Y      Y           F
efficientnet      Y      Y           Y
squeezenetv1.1    Y      Y           Y
shufflenet        Y      Y           F
mobilenet_ssd     Y      Y           F
mobilenet_yolov3  F      Y           F
inceptionv4       F      F           F
mtcnn             Y      Y           F
facedetection     Y      F           F
unet              Y      Y           F
ocr_attention     F      F           F
vgg16             F      F           F
================  =====  ==========  ====


安装
---------------

.. code:: shell

	pip install x2paddle


安装最新版本，可使用如下安装方式

.. code:: shell

	pip install git+https://github.com/PaddlePaddle/X2Paddle.git@develop

使用
------------

Caffe
>>>>>>>>>>>>>>

.. code:: shell

	x2paddle --framework caffe \
		--prototxt model.proto \
		--weight model.caffemodel \
		--save_dir paddle_model

TensorFlow
>>>>>>>>>>

.. code:: shell

	x2paddle --framework tensorflow \
		--model model.pb \
		--save_dir paddle_model


转换结果说明
--------------

在指定的 `save_dir` 下生成两个目录  

1. inference_model : 模型结构和参数均序列化保存的模型格式
2. model_with_code : 保存了模型参数文件和模型的python代码

**问题反馈**

X2Paddle使用时存在问题时，欢迎您将问题或Bug报告以 `Github Issues <https://github.com/PaddlePaddle/X2Paddle/issues>`_ 的形式提交给我们，我们会实时跟进。
