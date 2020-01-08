## 数据集
使用的时候把需要测试的数据集和txt文件放在data文件夹下，模型文件在checkpoints文件夹下
```markdown

|-data
|---Annotation
|---Image
|---test.txt
|-----core_battery00000003.xml
|-----core_battery00000004.xml
|-checkpoints
|--model_submit.pth
|-...
```


## 测试(计算在测试集上的mAP)
进入最近版本torch:source activate torch
使用以下命令开始测试：
CUDA_VISIBLE_DEVICES=0 python submit.py --image-root data/test/Image --imagesetfile data/test.txt --annopath data/test/Annotation --iou-thresh 0.5 --model-path /home/zhangsh/ml/portable_detection_zx/checkpoints/model_submit.pth

参数说明：image-root是测试数据的图片所在文件夹路径
         imagesetfile是测试集使用的图片名(.txt)
         annopath是测试数据txt文件所在路径
         model-path是模型所在路径（需要写绝对路径，不然可能报错）
