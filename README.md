![36b1d038bdb1b5d4392f2b9ee71059a](https://github.com/user-attachments/assets/924fa77c-c092-4342-a48f-bb086394b607)  
# modules.py:  
  
##### 推荐独立设置一个专门的导出环境和一个独立的训练环境  
##### 这是修改完成，实测可安装的modules.py  
##### 替换路径：导出虚拟环境下-Lib-site-packages-ultralytics-nn-modules.py  
  

# best.param & best.bin:  
  
##### 这是按照我的步骤全程下来导出的可用模型  
##### 大家可以拿我这个模型和自己的导出的模型做对比查漏补缺  
##### 当然也可以拿我这个模型去玩玩  
##### 这个模型是由yolov8预训练模型做迁移训练导出的模型，数据集是恶搞之家的主角的面部特征，因为训练的轮数不是很多，所以精度不是很高  
##### 重点还是给大家做参考嘛  

# onnx2ncnn & onnx2ncnn.exe:  

#### 用于onnx2ncnn部分，转换结果为param&bin（ncnn格式）  
#### 使用方法为放置在转换脚本同级文件夹下，于terminal中输入下行命令  
#### ./onnx2ncnn pt2onnx部分完成的模型.onnx 导出的模型名称.param 导出的模型名称.bin  
#####
# 注意事项
#### 修改ultralytics后，修改了的环境将无法进行模型训练，原因是修改的参数导致训练的中间模块断链  
#### fucn1：给修改完的ultralytics一个新的包名，如transform，之后调用该包时换用调用方法。重载ultralyrics==8.0.50，实现两包在同一环境下分割  
#### fucn2：创建新的环境（ultralytics==8.0.50无修改）专门用于训练，修改完的环境仅用于导出模型，实现训练和测试项目与导出项目分割  

