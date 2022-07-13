### 预训练模型，多个路口(end_edge_cloud)
```
python MiVeCC_main.py --s_exp_name Edge_baseline --mat_path arvTimeNewVeh_new_900_multi3_3.mat --priori_knowledge --type test --m_exp_name Cloud_baseline --visible --video_name test
```
> 函数：multi_intersections_test()


### 训练模型，多个路口（end_edge_cloud）:
```
python MiVeCC_main.py --mat_path arvTimeNewVeh_new_900_multi3_3.mat --type m_train --priori_knowledge --m_exp_name cloud_demo
```


### 生成初始的环境文档
```
matlab gen_multi_arvTime.m
```
> 函数：multi_intersections_train