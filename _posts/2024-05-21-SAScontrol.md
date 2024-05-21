---
title: 'SAS学习笔记6-SAS控制语句'
date: 2024-05-21
permalink: /posts/2024/05/SAScontrol/
tags:
  - cool posts
  - guide
  - experience
  - learning
  - SAS
---

# SAS控制语句

## IF-THEN ELSE语句

- 该语句主要在DATA步中起到控制处理作用
- IF-THEN语句也可以单独使用，但then后面只能写1句程序 

```sas
if age>50 then agegp=2;
if age<=50 then agegp=1; run;
```

```sas
if age>50 then agegp=2;else agegp=1; run;
```

## DO-END语句

- 由于IF-THEN ELSE语句一般只能执行1条命令，当程序需要重复做同样一件事，我们就可以用循环语句(DO-END)来执行。
- 如:如何求从1一直加到100的结果 ?

```sas
data a;
y=0;
do x=1 to 100;
y=y+x; output; /*将每一次循环的累加结果都输送到数据集中*/
end;
proc print;
run;
```

### 3种药物疗效的观察结果

| 疗效 |   | 药物 |   |
|--------|---------|---------|---------|
|      |  a  | b   | c |
| 治愈 | 15 | 4 | 1 |
| 显效 | 49 | 9 |15 |
| 好转 | 31 |50 |45 |
| 无效 | 5  |22 |24 |

表中是等级资料，列变量是单项有序变量，设计的目的是比较3种药物的疗效是否有差别?如何录入数据 ?

- 直接录入(使用input/cards语句)
    - 简单易学，但是遇到行列比较多的时候就会显得比较麻烦、低效

```sas
data a;
input r c n;
cards;
1 1 15
1 2 4
1 3 1
2 1 49
2 2 9
2 3 15
3 1 31
3 2 50
3 3 45
4 1 5
4 2 22
4 3 24
proc print;
run;
```

- DO-END录入数据

```sas
data a;
do r=1 to 4;
do c=1 to 3;
input n@@; output;
end;
end;
cards;
15 4 1
49 9 15
31 50 45
5 22 24
;
proc print;
run;
```

## SAS过程步简介

| 过程步名      | 功能                                                                                     |
|---------------|------------------------------------------------------------------------------------------|
| SORT          | 将指定的数据集按指定变量排序                                                             |
| PRINT         | 将数据集中的数据列表输出                                                                 |
| GCHART        | 绘出高分辨率的统计图                                                                     |
| UNIVARIATE    | 对指定的数值变量进行详细的统计描述                                                       |
| MEANS         | 对指定的数值变量进行简单的统计描述                                                       |
| FREQ          | 对指定的分类变量进行详细的统计描述，加上 TABLES 选项可进行卡方检验                       |
| NPAR1WAY      | 进行非参数检验                                                                           |
| TTEST         | 进行两样本t检验                                                                          |
| ANOVA         | 进行方差分析                                                                             |
| GLM           | 拟合一般线性模型                                                                         |
| REG           | 拟合多重线性模型，包括两变量的线性回归模型                                               |
| CORR          | 进行指定变量间的相关分析，包括两变量的线性相关分析                                       |
| LOGISTIC      | 拟合 logistic 回归模型                                                                   |
| LIFETEST      | 进行生存数据的生存率估计和Log-rank 检验                                                 |
| PHREG         | 拟合COX比例风险模型                                                                      |
