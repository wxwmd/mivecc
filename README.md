### 预训练模型，多个路口(end_edge_cloud)
```
python MiVeCC_main.py --s_exp_name Edge_baseline --mat_path arvTimeNewVeh_new_900_multi3_3.mat --priori_knowledge --type test --m_exp_name Cloud_baseline --visible --video_name test
```

### 训练模型，多个路口（end_edge_cloud）:
```
python MiVeCC_main.py --mat_path arvTimeNewVeh_new_900_multi3_3.mat --type m_train --priori_knowledge --m_exp_name cloud_demo
```


### 生成初始的环境文档
```
matlab gen_multi_arvTime.m
```

To see more intermediate results, run 
```
tensorboard --logdir ./model_data/cloud_demo/log
```
- Test the model:
```
python MiVeCC_main.py --mat_path arvTimeNewVeh_new_900_multi3_3.mat --type test --priori_knowledge --exp_name cloud_demo --visible --video_name cloud_demo
```
Note:the visual prarameters "--visible" and "--video_name" is optional. If use the "--visible", there will be a simulation interface to show the running interface of the vehicle in real time. the "--video_name cloud_demo" is used to generate a video ,named "cloud_demo.avi", saved in "./results_img/".

### Edge train/test (on the "single_intersection" branch)
- generate the arriveTime file
```
git checkout single_intersection
matlab gen_single_arvTime.m
```
- Train a model:
```
python MiVeCC_main.py --mat_path arvTimeNewVeh_new_900_l.mat --type train --priori_knowledge --exp_name edge_demo
```
To see more intermediate results, run 
```
tensorboard --logdir ./model_data/edge_demo/log
```
- Test the model:
```
python MiVeCC_main.py --mat_path arvTimeNewVeh_new_900.mat --type test --priori_knowledge --exp_name edge_demo --visible --video_name edge_demo
```
Note:the visual prarameters "--visible" and "--video_name" is optional. If use the "--visible", there will be a simulation interface to show the running interface of the vehicle in real time. the "--video_name edge_demo" is used to generate a video ,named "edge_demo.avi", saved in "./results_img/".
