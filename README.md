# mobilevit-pytorch 
根据网络结构自己修改的训练和推理的代码 
## 训练+推理
权重是自制的小规模imagenet上训练的，建议自己训练。
这里我主要是要验证智能算法在边缘设备上可以正常推理，因此对模型的推理精度没有要求，对于需要进行算子融合操作的使用者，可能需要有以下改动： 

![image](https://github.com/bez-ciebie/mobilevit-pytorch-train-infer/assets/47070146/99d8988c-b1fc-4b07-ae87-ba0165a22fdf) 

 （option：若在TPU机器上，算子融合无法使用，需要将.shape表征换为numels表征，具体做法是：使用shape和numel函数先查看cpu上的维度和个数，注释掉globel representation行，使用三次输入的维度来判断，这样算子融合就可以正确运行）


