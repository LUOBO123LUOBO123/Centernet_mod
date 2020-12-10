工程运行步骤：
一：环境准备
详见./readme/INSTALL.md



二：数据准备
1.将标注xml转coco数据集形式json；详见./notebook/convert_xml_coco.ipynb

2.创建自己数据集的类；src/lib/datasets/datasets  
示例：adc.py
--复制coco.py到自己的类.py
--修改类名
--修改类别数num_classes=
--修改分辨率(若有需要)
--测试自己数据集的均值和方差；详见./notebook/cal_mean.ipynb
--修改数据集的路径；self.data_dir=
--修改json文件路径
--修改类别名;self.class_name     self.valid_ids

3.将数据集加入src/lib/datasets/dataset_factory.py
--from ./datasets/adc import ADC
--dataset_factory = 

4.修改src/lib/opt.py
--修改默认数据 --dataset,default='adc'
--修改ctdet(检测)中的参数
  default_dataset_info('ctdet')
  --num_classes 数量
  --dataset    自己数据集的类名
--创建自己类别 adc_class_name =['others']
 








