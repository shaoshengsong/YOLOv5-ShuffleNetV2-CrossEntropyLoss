# YOLOv5-ShuffleNetV2-CrossEntropyLoss

This repo code uses Softmax and CrossEntropyLoss instead of BCEWithLogitsLoss.The improved source code is fully compatible with the original version of YOLOv5:v5. At the same time, backbone supports mobilenetv3,shufflenetv2, the original backbone supports all, and so on.  

There are classes that contain relationships（subset） that can be people, men. Mutually exclusive relationships that the class such as people, cats, and dogs. Try to improve the loss function when the classes of the dataset is mutually exclusive.  


Because BCEWithLogitsLoss = Sigmoid + BCELoss.  
BCEWithLogitsLoss adds Sigmoid to the loss function. The Sigmoid probability sum does not need to be 1.This can be done easily by just applying sigmoid function to each of raw scores. Note that the output probabilities will NOT sum to 1. The output predictions will be those classes that can beat a probability threshold.  

CrossEntropyLoss = LogSoftmax + NLLLoss.  
About softmax, each element will be in the range of 0 to 1, and the elements will add up to 1. This way, they can be interpreted as a probability distribution. For more clarification, the larger the input number, the larger the probabilities will be. It makes sure that the sum of all our output probabilities is equal to 1（or close to 1）.  


PEOPLE WHO READ THIS ARTICLE ALSO READ  
[Object detection YOLOv5 - Early Stopping mechanism](https://flyfish.blog.csdn.net/article/details/120163286).  
[Object Detection YOLOv5 - Fusion of convolution layer and BN layer](https://flyfish.blog.csdn.net/article/details/120088043).  
[Object detection YOLOv5 - Sample Assignment](https://flyfish.blog.csdn.net/article/details/119332396).  
[Object Detection YOLOv5 - data augmentation](https://flyfish.blog.csdn.net/article/details/119968461).  
[Object Detection YOLOv5 - Learning rate](https://flyfish.blog.csdn.net/article/details/119875059).  
[Object detection YOLOv5 - multi-machine multi-gpu training](https://flyfish.blog.csdn.net/article/details/119786227).  
[Object Detection YOLOv5 - floating Point Modulation](https://flyfish.blog.csdn.net/article/details/119276814).  
[Object detection YOLOv5 - applying NMS (non-maximum suppression) in multiple categories](https://flyfish.blog.csdn.net/article/details/119177472).  
[Object detection YOLOv5 - loss for objectness and classification](https://flyfish.blog.csdn.net/article/details/118909723).  
[Object detection YOLOv5 - loss for bounding box regression](https://flyfish.blog.csdn.net/article/details/118858068).  
[Object Detection YOLOv5 - Evaluation metric for YOLOv5](https://flyfish.blog.csdn.net/article/details/117741939).  
[Object detection YOLOv5 - anchor setting](https://flyfish.blog.csdn.net/article/details/117594265).  
[Object detection YOLOv5 - SPP module](https://flyfish.blog.csdn.net/article/details/117425010).  
[Object Detection YOLOv5 - bounding box prediction](https://flyfish.blog.csdn.net/article/details/117425996).  
[Object Detection YOLOv5 - Custom Network structure (YOLOv5 - ShuffleNetV2)](https://flyfish.blog.csdn.net/article/details/117303291).  
[Object detection YOLOv5 - bounding box coordinate representation](https://flyfish.blog.csdn.net/article/details/117133648).  
[Object detection YOLOv5 - relationship between image size and loss weight](https://flyfish.blog.csdn.net/article/details/116832354).  
[Object detection YOLOv5 - change the depth and width of the network according to configuration](https://flyfish.blog.csdn.net/article/details/116666103).  
[Object Detection YOLOv5 - Mobile Device deployment](https://flyfish.blog.csdn.net/article/details/116604907).  
[Object detection YOLOv5 - Focus in YOLOv5 Backbone](https://flyfish.blog.csdn.net/article/details/115634582).  
[Object detection YOLOv5 - model train,val,test,export commands](https://flyfish.blog.csdn.net/article/details/115580062).  
[Object detection YOLOv5 - face dataset widerface convert to YOLOv5 format](https://flyfish.blog.csdn.net/article/details/118114704).  
[Object detection YOLOv5 - YOLOv5 dataset format](https://flyfish.blog.csdn.net/article/details/115485130).  
[Object detection YOLOv5 - using COCO dataset](https://flyfish.blog.csdn.net/article/details/115485209).  
[Object detection YOLOv5 - CrowdHuman dataset format converted to YOLOv5 format](https://flyfish.blog.csdn.net/article/details/115485814)
