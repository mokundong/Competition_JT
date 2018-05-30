#任务

2014年，一种未知的疾病在全球肆虐，让人类束手无策。致病蛋白质很多，它们的结构序列都藏在df_protein.csv 数据集中（Sequence特征）。经过科学家的不懈努力，能与这些致病蛋白相结合的小分子（df_molecule.csv中的Fingerprint特征表示了其结构）也被发现，并附上了它们的理化属性。此外，在df_affinity.csv数据集中，包含了蛋白质和小分子之间的亲和力数值（Ki特征）。 时间紧迫！作为算法科学家，你能够仅仅在六周时间里，从测试集（df_affinity_test_toBePredicted.csv）中预测出致病蛋白与小分子的亲和力值，从而找出最有效的药物分子吗？

#数据

*注 : 报名参赛或加入队伍后，可获取数据下载权限。


#总体概述 

主办方晶泰科技搜集到了2万条数据（部分原始数据来源于BindingDB数据库），包含了蛋白质与小分子亲和力预测值以及蛋白质的一级结构序列，还有小分子的分子指纹及对应的18种物化属性。
根据蛋白质的信息，数据被分为两部分，一部分蛋白质的相关信息作为训练集，另一部分蛋白质的相关信息作为测试集，分别标注以train和test。

#数据文件解释

##1.蛋白质信息 df_protein.csv

数据共两列，分别是蛋白质id和蛋白质的一级结构序列的矢量化结果。（关于结构序列是什么形式，可参考[wiki链接](https://zh.wikipedia.org/wiki/%E8%9B%8B%E7%99%BD%E8%B3%AA%E4%B8%80%E7%B4%9A%E7%B5%90%E6%A7%8B))

 例如： Protein_ID, Sequence

4,MEPVPSARAELQFSLLANVSDTFPSAFPSASANASGSPGARSASSLALAIAITALYSAVCAVGLLGNVLVMFGIVRYTKLKTATNIYIFNLALADALATSTLPFQSAKYLMETWPFGELLCKAVLSIDYYNMFTSIFTLTMMSVDRYIAVCHPVKALDFRTPAKAKLINICIWVLASGVGVPIMVMAVTQPRDGAVVCTLQFPSPSWYWDTVTKICVFLFAFVVPILIITVCYGLMLLRLRSVRLLSGSKEKD   

##2.蛋白质小分子亲和力值信息 df_affinity.csv 

数据共三列， 分别是蛋白质id， 小分子id，亲和力值Ki（是经过函数变换后的值）
例如： Protein_ID, Molecule_ID, Ki   

             0           0           8.309803963  

             1           1          10.29242992

##3.小分子信息 df_molecule.csv（会存在缺失值） 

数据共二十列，其中每个特征的含义如下：  
Molecule_ID：小分子id，  
Fingerprint：分子指纹；  
cyp_sc9, cyp_sa4, cyp_2d6 ：三种cyp酶；  
Ames_toxicity: ames毒性测试  
Fathead_minnow_toxicity：黑头呆鱼毒性测试  
Tetrahymena_pyriformis_toxicity：梨型四膜虫毒性测试  
Honey_bee_toxicity：蜜蜂毒性测试  
Cell_permeability： 细胞渗透性  
LogP：油水分配数  
Renal_organic_cation_transporter： 肾脏阳离子运输性  
CLtotal： 血浆清除率  
Hia: 人体肠道吸收水平  
Biodegradation：生物降解水平  
Vdd：表观分布容积  
P_glycoprotein_inhibition： p糖蛋白抑制物  
NOAEL：无可见有害作用剂量  
Solubility：药物溶解度  
Bbb：血脑屏障    
Half-life：药物半衰期  