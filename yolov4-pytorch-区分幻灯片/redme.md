### 使用yolov4-pytorch来识别滑块缺口

### 食用方法

#### 1.作品使用github用户()的程序，完成识别缺口。原作者链接：https://github.com/bubbliiiing/yolov4-pytorch         观看作者bilibii视频，再上手项目会有更好的体验。

####  2.vott  标注数据集   视频教程 bilibili 搜 vott 教程 高效完成数据标注。

#### 3. vott 标注完成后，打包为 VOC 格式的 数据 上传至 矩池云 个人网盘（在线GPU训练平台）。

######  3.1上传流程    https://blog.csdn.net/weixin_48344945/article/details/107034346 

####  4. 训练步骤 
#####  4.1、本文使用VOC格式进行训练。  
#####  4.2、训练前将 标签文件 放在VOCdevkit文件夹下的VOC2007文件夹下的Annotation中。
#####  4.3、训练前将 图片文件 放在VOCdevkit文件夹下的VOC2007文件夹下的JPEGImages中。
#####  4.4、在训练前利用 voc2yolo4.py文件生成对应的txt。
#####  4.5、再运行根目录下的voc_annotation.py，运行前需要将classes改成你自己的classes。注意不要使用中文标签，文件夹中不要有空格！   
        classes = ["aeroplane", "bicycle", "bird", "boat", "bottle", "bus", "car", "cat", "chair", "cow", "diningtable", "dog", "horse", "motorbike", "person", "pottedplant", "sheep", "sofa", "train", "tvmonitor"]
#####  4.6、此时会生成对应的   2007_train.txt   ，每一行对应其图片位置及其真实框的位置。
#####  4.7、在训练前需要务必在  model_data  下新建一个 txt 文档，文档中输入需要分的类，在 train.py 中将 classes_path 指向该文件，示例如下：   
        classes_path = 'model_data/new_classes.txt'    
        model_data/new_classes.txt文件内容为：   
        cat
        dog
        ...
#####  4.8、运行train.py即可开始训练。


#### 注意
 注意 图片格式，png 或 jpg   ，  需要修改根目录下的 voc_ac    最后更改为 jpg  png。
