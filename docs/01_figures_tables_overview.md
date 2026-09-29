# 真机图表总览与参考优先级

核查日期：2026-09-29。以下按本项目的可借鉴程度、材料完整度与真机协议清晰度排序。作者单位用于说明来源背景；公开版本均按 arXiv 记录，正式会议录用状态列为待核。

## 1. 优先看什么

| 优先级 | 工作与版本 | 单位背景 | 最适合本项目的部位／材料情况 |
|---|---|---|---|
| 1 | X-WAM v2 | 清华、小米、北大、中科院自动化所 | 已选对照、几何与精细操作直接相关；论文／项目／代码／权重入口齐；先看 T8、F4 与主页 OOD |
| 2 | OpenWAM v1 | 新国立、清华、北大、港大、浙大、港中文、上交 | 已选基座对照，发布资源完整；T8 是最直接的 ID/OOD 单表范例；Appendix C 的展示完整 |
| 3 | Efficient-WAM v3 | 港大、北大、Muka、中科院自动化所、南大 | 协议完整：示范、次数、时限、成功标准；代码／权重入口可定位；紧凑真机写法优先参考 |
| 4 | FlowWAM v1 | 中科院自动化所、国科大、FiveAges、MBZUAI、阿里 | 七任务双平台；代码／权重／数据入口齐；硬件和预测—执行展示最好复用 |
| 5 | WAM4D v3 | 北大、港科大、北京人形机器人创新中心 | 几何与四任务关系直接；有子动作判据表；论文所给 GitHub 入口本次为 404 |
| 6 | Track4Action v1 | 浙大、上交、上海创智学院、Noematrix | 四任务、50 demos、直观真实 OOD；项目页的模型代码／权重按钮仍指向占位 |
| 7 | Fast-WAM v2 | 清华交叉信息院、Galaxea AI | 开放实现与权重；真机单任务，主要用于理解视频训练与动作推理的关系 |

主题上：**主结果表优先 OpenWAM/X-WAM；协议优先 Efficient-WAM；简洁 OOD 优先 X-WAM/Track4Action/OpenWAM；硬件和预测图优先 FlowWAM；任务与几何关系优先 WAM4D。** 本轮补读 OpenWAM 的真机正文及实验附录，其他六篇沿用已通读的正文与实验附录并复核图表。

MetisWAM4D 是当前项目主体，其代码阅读要点已另存本地；本文将它作为待设计与评估的方法。公开同名论文与正式发表信息随后补入。

## 2. 原始链接

| 工作 | 论文版本 | 项目／演示 | 实现／模型 |
|---|---|---|---|
| X-WAM | [v2](https://arxiv.org/pdf/2604.26694v2) | [项目页](https://sharinka0715.github.io/X-WAM/) | [代码](https://github.com/sharinka0715/X-WAM) · [权重](https://huggingface.co/sharinka0715/X-WAM-checkpoints) · [RoboTwin 数据](https://huggingface.co/datasets/sharinka0715/X-WAM-RoboTwin) · [RoboCasa 数据](https://huggingface.co/datasets/sharinka0715/X-WAM-RoboCasa) |
| OpenWAM | [v1](https://arxiv.org/pdf/2609.07398v1) | [项目](https://openwam-official.github.io/) · [实验](https://openwam-official.github.io/results/) | [代码](https://github.com/OpenWAM-Official/OpenWAM) · [Alpha 模型卡](https://huggingface.co/OpenWAM/OpenWAM-Alpha-Pretrain-Foundation-Model) |
| Efficient-WAM | [v3](https://arxiv.org/pdf/2606.10040v3) | [项目](https://efficientwam.github.io/) | [代码](https://github.com/jiajun613/Efficient-WAM) · [权重](https://huggingface.co/jiajun0613/Efficient-WAM_RoboTwin) |
| FlowWAM | [v1](https://arxiv.org/pdf/2607.13017v1) | [项目](https://flow-wam.github.io/) | [代码](https://github.com/YixiangChen515/FlowWAM) · [权重](https://huggingface.co/YixiangChen/FlowWAM) · [数据](https://huggingface.co/datasets/YixiangChen/FlowWAM_RoboTwin) |
| WAM4D | [v3](https://arxiv.org/pdf/2606.14048v3) | 论文图表 | [论文给出的代码入口（本次 404）](https://github.com/myendless1/wam4d) |
| Track4Action | [v1](https://arxiv.org/pdf/2608.03727v1) | [项目](https://wing0night.github.io/track4action-project-page/) | 项目页面仓库可访问；模型实现／checkpoint 链接为占位 |
| Fast-WAM | [v2](https://arxiv.org/pdf/2603.16666v2) | [项目](https://yuantianyuan01.github.io/FastWAM/) | [代码](https://github.com/yuantianyuan01/FastWAM) · [权重](https://huggingface.co/yuanty/fastwam) |

## 3. 快速索引

| 工作 | 真机定量 | 任务／场景／硬件／机制 |
|---|---|---|
| X-WAM | T8 p21 | F4 p21；主页泛化视频 |
| OpenWAM | T6 p25；T7/T8 p26 | F17 p25；T11/F18 p35；F19 p36；T12/F20 p37；F21 p38 |
| Efficient-WAM | T2 p8 | F3 p7；F5/F6 p14 |
| FlowWAM | F3 p8 | F6 p21；F9 p26 |
| WAM4D | T2 p8 | F4 p8；T4 p10 |
| Track4Action | F3 p6 OOD；F4/F5 p7 | F3 同时含硬件、任务阶段、OOD 条件 |
| Fast-WAM | F4 p9 | F3 p7 |

下面保存 27 处图表摘录。每张图链接到原始版本和页码；数字转录与计算见 [数值文件](03_real_world_numbers.md)。X-WAM v2 耳机实验与其当前主页新增三任务协议分别标记；Efficient-WAM 以 v3 五任务结果为准。


## X-WAM

### Table 8 · PDF p.21

任务规模与 OOD 同表；Progress + Time。[原图所在页](https://arxiv.org/pdf/2604.26694v2#page=21)

![X-WAM Table 8](../assets/literature/x_wam_table8_p21.png)

### Figure 4 · PDF p.21

真机耳机装盒：10 张执行关键帧。[原图所在页](https://arxiv.org/pdf/2604.26694v2#page=21)

![X-WAM Figure 4](../assets/literature/x_wam_figure4_p21.jpg)

## OpenWAM

### Table 6 · PDF p.25

六个单臂任务，三方法 SR 与原始 k/n。[原图所在页](https://arxiv.org/pdf/2609.07398v1#page=25)

![OpenWAM Table 6](../assets/literature/openwam_table6_p25.png)

### Table 8 · PDF p.26

四个灵巧手任务，ID/OOD 同表；Score 与 SR。[原图所在页](https://arxiv.org/pdf/2609.07398v1#page=26)

![OpenWAM Table 8](../assets/literature/openwam_table8_p26.png)

### Table 7 · PDF p.26

RoboDojo 三具身 18 任务；每格 Score/SR。[原图所在页](https://arxiv.org/pdf/2609.07398v1#page=26)

![OpenWAM Table 7](../assets/literature/openwam_table7_p26.png)

### Figure 17 · PDF p.25

单臂、双臂、灵巧手的任务与平台总览。[原图所在页](https://arxiv.org/pdf/2609.07398v1#page=25)

![OpenWAM Figure 17](../assets/literature/openwam_figure17_p25.jpg)

### Table 11 · PDF p.35

六个单臂任务的语言指令表。[原图所在页](https://arxiv.org/pdf/2609.07398v1#page=35)

![OpenWAM Table 11](../assets/literature/openwam_table11_p35.png)

### Figure 18 · PDF p.35

单臂工作台、相机与夹爪标注。[原图所在页](https://arxiv.org/pdf/2609.07398v1#page=35)

![OpenWAM Figure 18](../assets/literature/openwam_figure18_p35.jpg)

### Figure 19 · PDF p.36

六任务各六帧的执行序列。[原图所在页](https://arxiv.org/pdf/2609.07398v1#page=36)

![OpenWAM Figure 19](../assets/literature/openwam_figure19_p36.jpg)

### Table 12 · PDF p.37

四个灵巧手任务的语言指令表。[原图所在页](https://arxiv.org/pdf/2609.07398v1#page=37)

![OpenWAM Table 12](../assets/literature/openwam_table12_p37.png)

### Figure 20 · PDF p.37

灵巧手平台、相机、工作台与道具。[原图所在页](https://arxiv.org/pdf/2609.07398v1#page=37)

![OpenWAM Figure 20](../assets/literature/openwam_figure20_p37.jpg)

### Figure 21 · PDF p.38

任务执行过程旁列 ID/OOD：布局、背景、物体、光照。[原图所在页](https://arxiv.org/pdf/2609.07398v1#page=38)

![OpenWAM Figure 21](../assets/literature/openwam_figure21_p38.jpg)

## Efficient-WAM

### Table 2 · PDF p.8

五任务三方法成功率，附推理延迟。[原图所在页](https://arxiv.org/pdf/2606.10040v3#page=8)

![Efficient-WAM Table 2](../assets/literature/efficient_wam_table2_p08.png)

### Figure 3 · PDF p.7

五任务执行场景与关键帧。[原图所在页](https://arxiv.org/pdf/2606.10040v3#page=7)

![Efficient-WAM Figure 3](../assets/literature/efficient_wam_figure3_p07.jpg)

### Figure 5 · PDF p.14

AstriBot S1、头部和双腕相机标注。[原图所在页](https://arxiv.org/pdf/2606.10040v3#page=14)

![Efficient-WAM Figure 5](../assets/literature/efficient_wam_figure5_p14.jpg)

### Figure 6 · PDF p.14

抓取偏差、漏分积木、碰撞等失败序列。[原图所在页](https://arxiv.org/pdf/2606.10040v3#page=14)

![Efficient-WAM Figure 6](../assets/literature/efficient_wam_figure6_p14.jpg)

## FlowWAM

### Figure 3 · PDF p.8

七任务成功率柱图，下方配任务照片。[原图所在页](https://arxiv.org/pdf/2607.13017v1#page=8)

![FlowWAM Figure 3](../assets/literature/flowwam_figure3_p08.jpg)

### Figure 6 · PDF p.21

Franka/ARX 双平台与相机标注。[原图所在页](https://arxiv.org/pdf/2607.13017v1#page=21)

![FlowWAM Figure 6](../assets/literature/flowwam_figure6_p21.jpg)

### Figure 9 · PDF p.26

七个真实任务的预测 RGB/光流与执行画面。[原图所在页](https://arxiv.org/pdf/2607.13017v1#page=26)

![FlowWAM Figure 9](../assets/literature/flowwam_figure9_p26.jpg)

## WAM4D

### Table 2 · PDF p.8

七个子动作列的成功率；10 rollouts/task。[原图所在页](https://arxiv.org/pdf/2606.14048v3#page=8)

![WAM4D Table 2](../assets/literature/wam4d_table2_p08.png)

### Figure 4 · PDF p.8

四任务：指令、能力标签、初始／交互／完成。[原图所在页](https://arxiv.org/pdf/2606.14048v3#page=8)

![WAM4D Figure 4](../assets/literature/wam4d_figure4_p08.jpg)

### Table 4 · PDF p.10

任务—阶段—成功标准，正文中的明确判据表。[原图所在页](https://arxiv.org/pdf/2606.14048v3#page=10)

![WAM4D Table 4](../assets/literature/wam4d_table4_p10.png)

## Track4Action

### Figure 3 · PDF p.6

硬件、四任务、三种真实 OOD 及其柱图。[原图所在页](https://arxiv.org/pdf/2608.03727v1#page=6)

![Track4Action Figure 3](../assets/literature/track4action_figure3_p06.jpg)

### Figure 4 · PDF p.7

四任务完整成功率，四方法。[原图所在页](https://arxiv.org/pdf/2608.03727v1#page=7)

![Track4Action Figure 4](../assets/literature/track4action_figure4_p07.jpg)

### Figure 5 · PDF p.7

四阶段过程得分堆积柱图。[原图所在页](https://arxiv.org/pdf/2608.03727v1#page=7)

![Track4Action Figure 5](../assets/literature/track4action_figure5_p07.jpg)

## Fast-WAM

### Figure 3 · PDF p.7

真实叠毛巾八帧序列。[原图所在页](https://arxiv.org/pdf/2603.16666v2#page=7)

![Fast-WAM Figure 3](../assets/literature/fast_wam_figure3_p07.jpg)

### Figure 4 · PDF p.9

成功率—完成时间散点与推理延迟。[原图所在页](https://arxiv.org/pdf/2603.16666v2#page=9)

![Fast-WAM Figure 4](../assets/literature/fast_wam_figure4_p09.jpg)

## 补充材料与版本

WAM4D F5/F6 的注意力、RGB-D 和点云展示来自 RoboTwin 模拟场景，另作为几何机制形式参考。X-WAM 主页的 RoboCasa 重建同属仿真；其耳机、装盒等执行与泛化视频是真机部分。FlowWAM F9 则明确展示真机预测和执行。

图表原作者、论文版本、页码、裁剪范围和文件哈希见 [figure_manifest.json](../data/figure_manifest.json)。原始完整 PDF 链接保留在上表。
