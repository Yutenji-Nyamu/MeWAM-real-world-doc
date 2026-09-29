# 真机数值逐项对照

更新：2026-09-29。**同一论文内比较，提升用百分点（pp）**；各论文的任务、数据量、平台与指标分别记录。表中 SR 为完整任务成功率；Progress／Score 为阶段或元素完成分数。原表／图摘录见 [图表总览](01_figures_tables_overview.md)。

## 1. 先看整体量级

| 工作／真实设置 | 该工作方法 | 对比方法 | 绝对提升 | 指标 |
|---|---:|---:|---:|---|
| FlowWAM，七任务 | 75.7 | π0.5 61.4；Motus 57.1 | +14.3；+18.6 | 完整 SR，% |
| Efficient-WAM v3，五任务 | 65.0 | Motus 64.0；π0.5 60.0 | +1.0；+5.0 | 完整 SR，% |
| Track4Action，四任务 | 67.5 | π0.5 65.0；去对齐 42.5 | +2.5；+25.0 | 完整 SR，% |
| OpenWAM，单臂六任务 | 82.5 | LingBot-VA 77.5；π0.5 55.0 | +5.0；+27.5 | 完整 SR，% |
| OpenWAM，RoboDojo 18 任务 | 24.4 | π0.5 12.8 | +11.6 | 完整 SR，% |
| WAM4D，七个子动作列 | 90 | LingBot-VA 84；Fast-WAM 80；π0.5 74 | +6；+10；+16 | 子动作均值，原表 0–1 换成 % |
| X-WAM，新位置 | 70.8 | XR-0 58.3 | +12.5 | Progress，% |
| Fast-WAM，叠毛巾 | 约 75 | π0.5 100；IDM 90；去视频 10 | 约 −25；−15；+65 | SR，图读数 |

“七十多对五六十”确实出现在 FlowWAM，其他论文有不同量级。简单任务可接近 100%，复杂任务或分布变化可在 10–40%。总体平均、逐任务差异和对比对象应一起读。

## 2. X-WAM v2：进度与用时

[Table 8，PDF p.21](https://arxiv.org/pdf/2604.26694v2#page=21)。AC One 双臂，约 20 小时示范；每条件 6 次。进度按完成阶段计，表中分母为阶段数；用时只在到达 100% progress 的 episode 上平均。

| 条件 | XR-0 Progress % | X-WAM Progress % | Δ pp | XR-0 时间 s | X-WAM 时间 s |
|---|---|---|---|---|---|
| Pack 1 earphone | 100.0 (24/24) | 100.0 (24/24) | 0 | 54.66 | 41.63 |
| Pack 2 earphones | 79.1 (38/48) | 93.8 (45/48) | +14.7 | 115.44 | 113.25 |
| Pack 3 earphones | 63.9 (46/72) | 68.0 (49/72) | +4.1 | 195.66 | 160.72 |
| Novel placements | 58.3 (14/24) | 70.8 (17/24) | +12.5 | 89.63 | 46.68 |
| Unseen tablecloth | 66.7 (16/24) | 66.7 (16/24) | 0 | 65.73 | 62.01 |
| Unseen distractors | 66.7 (16/24) | 75.0 (18/24) | +8.3 | 76.32 | 51.53 |

印刷值按原表保留：例如 38/48 写为 79.1，49/72 写为 68.0；上表 Δ 使用印刷百分比相减。π0.5 在附录中另有训练尝试和 25–50% 单耳机进度的定性说明，T8 的正式逐条件对照为 XR-0 与 X-WAM。

当前 [项目页](https://sharinka0715.github.io/X-WAM/) 另展示 Phone Packing、Box Packing、Printer Refilling × ID/桌布/光照 × 每格 20 次，共 180 次。主页协议、演示与 v2 耳机表分开记录，新增三任务的逐方法定量表留待公开材料补齐。

## 3. OpenWAM：单臂、双臂与 ID/OOD

### 3.1 单臂六任务

[Table 6，p.25](https://arxiv.org/pdf/2609.07398v1#page=25)。Franka Research 3，每任务 100 条示范、20 次试验。以下全部为完整 SR（%）。

| 任务 | π0.5 | LingBot-VA | OpenWAM-α | Δ vs LingBot | Δ vs π0.5 |
|---|---|---|---|---|---|
| Stack Jenga | 65 | 80 | 85 | +5 | +20 |
| Stack Ring | 35 | 75 | 60 | -15 | +25 |
| Put Chili in Drawer | 70 | 85 | 100 | +15 | +30 |
| Put Jenga in Drawer | 75 | 85 | 100 | +15 | +25 |
| Hang on M | 35 | 65 | 65 | 0 | +30 |
| Hang on Cup | 50 | 75 | 85 | +10 | +35 |
| 平均 | 55 | 77.5 | 82.5 | +5 | +27.5 |

### 3.2 灵巧手：同表 ID/OOD

[Table 8，p.26](https://arxiv.org/pdf/2609.07398v1#page=26)。两方法都以原表完整成功率和阶段分数记录；OOD 列汇总该任务的全部变化。每格 `百分比 (分子/分母)`。

| 任务 | 条件 | π0.5 SR | OpenWAM SR | SR Δ pp | π0.5 Score | OpenWAM Score |
|---|---|---|---|---|---|---|
| Stack Toy Tower | ID | 10 (1/10) | 40 (4/10) | +30 | 53.3 (16/30) | 70 (21/30) |
| Stack Toy Tower | OOD | 10 (1/10) | 30 (3/10) | +20 | 40 (12/30) | 56.7 (17/30) |
| Collect Shuttlecocks | ID | 20 (2/10) | 60 (6/10) | +40 | 31.4 (11/35) | 82.9 (29/35) |
| Collect Shuttlecocks | OOD | 20 (3/15) | 26.7 (4/15) | +6.7 | 31.5 (17/54) | 52.6 (30/57) |
| Put Away Clothes | ID | 60 (6/10) | 100 (10/10) | +40 | 86.7 (26/30) | 100 (30/30) |
| Put Away Clothes | OOD | 45 (9/20) | 85 (17/20) | +40 | 75 (45/60) | 91.7 (55/60) |
| Twist off Bottle Cap | ID | 30 (3/10) | 70 (7/10) | +40 | 80 (8/10) | 100 (10/10) |
| Twist off Bottle Cap | OOD | 30 (6/20) | 80 (16/20) | +50 | 65 (13/20) | 90 (18/20) |

羽毛球 OOD 的过程分母为 54 与 57，反映对应试验里操作元素的累计数量；完整任务分母均为 15。此例说明报告 `k/n` 很有帮助。

### 3.3 RoboDojo 18 任务：完整转录

[Table 7，p.26](https://arxiv.org/pdf/2609.07398v1#page=26)。每格 **Score / SR（%）**；以下三个表按原表任务顺序展开。总体值采用论文印刷值。

#### ARX X5

| 任务 | X-VLA | Xiaomi-Robotics-0 | GalaxeaVLA (G0) | InternVLA-A1 | pi0.5 | OpenWAM-alpha |
|---|---|---|---|---|---|---|
| cover_blocks | 0 / 0 | 24 / 20 | 1 / 0 | 0 / 0 | 24.6 / 20 | 31 / 0 |
| make_bread | 0 / 0 | 0 / 0 | 0 / 0 | 0 / 0 | 1.8 / 0 | 0 / 0 |
| make_food | 0 / 0 | 3 / 0 | 3 / 0 | 0 / 0 | 25.8 / 10 | 13 / 0 |
| pack_and_pour_fruit | 2 / 0 | 4 / 0 | 6 / 0 | 0 / 0 | 47 / 20 | 52 / 20 |
| store_in_safe | 20.7 / 10 | 40 / 20 | 0 / 0 | 48 / 20 | 40 / 20 | 100 / 100 |
| insert_tubes | 18 / 0 | 19 / 10 | 10.3 / 0 | 12 / 0 | 26.8 / 10 | 38 / 20 |
| 平台均值 | 6.8 / 1.7 | 15 / 8.3 | 3.4 / 0 | 10 / 3.3 | 27.7 / 13.3 | 39 / 23.3 |

#### Piper

| 任务 | X-VLA | Xiaomi-Robotics-0 | GalaxeaVLA (G0) | InternVLA-A1 | pi0.5 | OpenWAM-alpha |
|---|---|---|---|---|---|---|
| stack_and_cover_blocks | 0 / 0 | 0 / 0 | 0 / 0 | 0 / 0 | 10 / 10 | 8.3 / 0 |
| fill_pen_holder | 5.3 / 0 | 0 / 0 | 32.7 / 10 | 7.3 / 0 | 28 / 0 | 60 / 40 |
| put_objects_into_basket | 0 / 0 | 0 / 0 | 13.3 / 10 | 0 / 0 | 10 / 10 | 36.7 / 30 |
| insert_charger | 0 / 0 | 0 / 0 | 0 / 0 | 0 / 0 | 0 / 0 | 0 / 0 |
| stack_bowls | 53 / 50 | 23 / 20 | 56 / 50 | 73 / 70 | 72 / 60 | 100 / 100 |
| stand_up_bottles | 37 / 0 | 22.7 / 0 | 30 / 10 | 59 / 40 | 72 / 50 | 75 / 50 |
| 平台均值 | 15.9 / 8.3 | 7.6 / 3.3 | 22 / 13.3 | 23.2 / 18.3 | 32 / 21.7 | 46.7 / 36.7 |

#### Piper X

| 任务 | X-VLA | Xiaomi-Robotics-0 | GalaxeaVLA (G0) | InternVLA-A1 | pi0.5 | OpenWAM-alpha |
|---|---|---|---|---|---|---|
| classify_objects | 0 / 0 | 0 / 0 | 0 / 0 | 0 / 0 | 0 / 0 | 0 / 0 |
| disassemble_LEGO | 0 / 0 | 0.7 / 0 | 0 / 0 | 0 / 0 | 14.8 / 10 | 28 / 10 |
| hang_mugs | 0 / 0 | 4 / 0 | 0 / 0 | 4 / 0 | 0 / 0 | 18 / 0 |
| pack_objects_into_backpack | 0 / 0 | 0 / 0 | 0 / 0 | 2 / 0 | 29.5 / 10 | 52.3 / 20 |
| sweep_blocks | 0 / 0 | 0 / 0 | 4 / 0 | 0 / 0 | 7.5 / 0 | 40 / 40 |
| cap_pen | 0.7 / 0 | 2.7 / 0 | 6 / 0 | 10 / 0 | 3 / 0 | 24.7 / 10 |
| 平台均值 | 0.1 / 0 | 1.2 / 0 | 1.7 / 0 | 2.7 / 0 | 9.1 / 3.3 | 27.2 / 13.3 |

| 方法 | 总体 Score | 总体 SR |
|---|---|---|
| X-VLA | 7.6 | 3.3 |
| Xiaomi-Robotics-0 | 7.9 | 3.9 |
| GalaxeaVLA (G0) | 9 | 4.4 |
| InternVLA-A1 | 12 | 7.2 |
| pi0.5 | 22.9 | 12.8 |
| OpenWAM-alpha | 37.6 | 24.4 |

OpenWAM 对 π0.5：总体 Score +14.7 pp，完整 SR +11.6 pp。三个具身的 SR 分别提升 +10.0、+15.0、+10.0 pp（按原表均值计算）。高难度统一基准的绝对成功率明显低于上面的单臂小任务集。

## 4. Efficient-WAM v3：五任务

[Table 2，p.8](https://arxiv.org/pdf/2606.10040v3#page=8)。前四任务 Astribot S1，各 100 demos；毛巾使用另一个双臂人形平台与 Pika UMI，1000 demos。每任务每方法 20 次，3 分钟时限。数值为完整 SR（%）。

| 任务 | π0.5 | Motus | Efficient-WAM | Δ vs Motus | Δ vs π0.5 |
|---|---|---|---|---|---|
| Pipette-tray grasping | 100 | 85 | 95 | +10 | -5 |
| Reagent-bottle transfer | 75 | 80 | 75 | -5 | 0 |
| LEGO color sorting | 30 | 65 | 65 | 0 | +35 |
| Pen uncapping | 10 | 25 | 30 | +5 | +20 |
| Towel folding | 85 | 65 | 60 | -5 | -25 |
| 平均 | 60 | 64 | 65 | +1 | +5 |

RTX 4090 的 chunk 延迟：π0.5 113 ms、Motus 3215 ms、Efficient-WAM 98 ms。均摊到 16 个动作：7.1、200.9、6.1 ms/action。它们分别描述计算块耗时和均摊计算量。

项目页的旧四任务平均 66.25% 与本表五任务 65% 使用不同任务集合；当前整理锁定 v3。

## 5. FlowWAM：七任务

[Figure 3，p.8](https://arxiv.org/pdf/2607.13017v1#page=8)。每任务 100 demos、10 trials，随机物体位姿；完整 SR（%）。

| 任务 | π0.5 | Motus | FlowWAM | Δ vs π0.5 | Δ vs Motus |
|---|---|---|---|---|---|
| Franka: Stack Bowls | 80 | 80 | 90 | +10 | +10 |
| Franka: Place in Drawer | 70 | 80 | 90 | +20 | +10 |
| Franka: Put in Plate | 80 | 80 | 100 | +20 | +20 |
| Franka: Place Two Cups | 40 | 30 | 60 | +20 | +30 |
| ARX: Fold Towel | 40 | 30 | 40 | 0 | +10 |
| ARX: Stack Bowls II | 70 | 70 | 90 | +20 | +20 |
| ARX: Clean Plate | 50 | 30 | 60 | +10 | +30 |
| 平均 | 61.4 | 57.1 | 75.7 | +14.3 | +18.6 |

FlowWAM 叠毛巾与 π0.5 同为 40%；七任务总体提高，逐项表现包含持平和提升。相对 π0.5，单臂平均提升 17.5 pp，双臂平均提升 10 pp；相对 Motus，单臂为 17.5 pp，双臂约 20 pp。这里按 Fig.3 逐任务读数计算，便于对照正文关于双臂收益的解释。

## 6. WAM4D：子动作粒度

[Table 2，p.8](https://arxiv.org/pdf/2606.14048v3#page=8)，每任务 10 rollouts。下面保留原表 0–1 尺度；子动作前序失败时，后续记 0。

| 方法 | Plate S1 | Bottle S1 | Blocks S1 | Blocks S2 | Blocks S3 | Pen S1 | Pen S2 | 原表平均 |
|---|---|---|---|---|---|---|---|---|
| pi0.5 | 1.0 | 0.8 | 0.7 | 0.6 | 0.5 | 0.8 | 0.8 | 0.74 |
| LingBot-VA | 1.0 | 1.0 | 1.0 | 0.7 | 0.4 | 0.9 | 0.9 | 0.84 |
| Fast-WAM | 0.9 | 1.0 | 0.8 | 0.7 | 0.5 | 0.9 | 0.8 | 0.80 |
| WAM4D | 0.9 | 0.9 | 1.0 | 0.9 | 0.8 | 0.9 | 0.9 | 0.90 |

| 子动作 | WAM4D 相对 LingBot pp | 相对 Fast-WAM pp | 相对 π0.5 pp |
|---|---|---|---|
| Plate S1 | -10 | 0 | -10 |
| Bottle S1 | -10 | -10 | +10 |
| Blocks S1 | 0 | +20 | +30 |
| Blocks S2 | +20 | +20 | +30 |
| Blocks S3 | +40 | +30 | +30 |
| Pen S1 | 0 | 0 | +10 |
| Pen S2 | 0 | +10 | +10 |

Table 4 定义了 Bottle S1 抓取和 S2 放入托盘；Table 2 实际只展示 Bottle S1。上表按实际七列转录。90% 是七个子动作列的平均，普通完整任务 SR 的比较放在其他表中。

## 7. Track4Action：完整成功率、过程分数与 OOD

[Figures 3–5，pp.6–7](https://arxiv.org/pdf/2608.03727v1#page=6)。四任务，每任务 50 demos；ID 每方法每任务 10 次。

### 完整成功率（%）

| 任务 | pi0.5 | DreamZero | Track4Action w/o align | Track4Action | Δ vs π0.5 | Δ vs w/o align |
|---|---|---|---|---|---|---|
| Chilies into plate | 70 | 40 | 60 | 80 | +10 | +20 |
| Pens in drawer and close | 60 | 40 | 50 | 80 | +20 | +30 |
| Fold towel | 70 | 30 | 20 | 40 | -30 | +20 |
| Cabbage into pot and close | 60 | 10 | 40 | 70 | +10 | +30 |
| 平均 | 65.0 | 30.0 | 42.5 | 67.5 | +2.5 | +25 |

### 过程分数（满分 100）

| 任务 | pi0.5 | DreamZero | Track4Action w/o align | Track4Action |
|---|---|---|---|---|
| Chilies into plate | 80 | 42.5 | 70 | 85 |
| Pens in drawer and close | 80 | 47.5 | 67.5 | 92.5 |
| Fold towel | 60 | 40 | 40 | 47.5 |
| Cabbage into pot and close | 80 | 30 | 65 | 75 |
| 平均（计算） | 75.0 | 40.0 | 60.625 | 75.0 |

完整方法过程均值 75.0，与 π0.5 相同；去对齐均值精确算得 60.625，原文四舍五入为 60.6，并报告约 +14.4 分。

### 真实 OOD（完整 SR，%）

| 条件 | w/o align | Track4Action | Δ pp |
|---|---|---|---|
| Chilies: unseen layout / distractors | 30 | 60 | +30 |
| Towel: red to green | 10 | 20 | +10 |
| Cabbage: textured background | 30 | 70 | +40 |

这组 OOD 对照是去对齐消融与完整方法。毛巾和布局的真实照片见 Fig.3，具体轴的解释见 [OOD 文件](04_ood_claims.md)。

## 8. Fast-WAM：单任务性能／速度折中

[Figure 4，p.9](https://arxiv.org/pdf/2603.16666v2#page=9)。Galaxea R1 Lite，60 小时示范、30k 训练步。左图坐标读数使用约数；右图延迟有印刷标签，设备为 RTX 5090D V2。试验次数在所读协议中未单列。

| 方法 | SR %（图读数） | 完成时间约 s | 推理延迟 ms |
|---|---|---|---|
| pi0.5 | 100 | 120 | 180 |
| pi0.5 w/o pretrain | 40 | 205 | — |
| Fast-WAM | 75 | 150 | 190 |
| Fast-WAM Joint | 70 | 225 | 580 |
| Fast-WAM IDM | 90 | 175 | 810 |
| Fast-WAM w/o video cotrain | 10 | 240 | 190 |

Fast-WAM 的主要优势在于保留视频共同训练收益的同时，使延迟接近动作模型；此任务中 π0.5 的成功率更高。因而该图适合学习如何报告性能—速度折中。

## 9. 可形成的共识

1. **成功率随任务与设置变化。** 同组材料里既有 100% 的简单项，也有 10–40% 的困难项；任务定义、终点和分布决定绝对量级。
2. **均值提升与逐项差异一起看。** Efficient-WAM +1 pp、Track4Action +2.5 pp、FlowWAM +14.3 pp 都有实际先例；部分任务会持平或下降。
3. **同基座消融往往比跨方法差异更能解释新增信息。** Track4Action 对去对齐版 +25 pp，而对 π0.5 +2.5 pp。当前选定对比先保留 OpenWAM-Alpha、X-WAM；后续机制问题可在同基座上单独检验。
4. **保留原始 k/n。** 10 次试验中一次成败对应 10 pp，20 次对应 5 pp。表格同时列分母，读者更容易判断差异的粒度。
5. **明确 SR 与 Progress。** X-WAM 的阶段进度、WAM4D 的子动作均值与整任务 SR 各自回答不同问题。本项目主表优先用完整 SR，阶段进度用于附录诊断。
6. **一张表覆盖 ID/OOD 有直接范例。** OpenWAM T8 同任务下并列 ID/OOD；本项目展开三类 OOD 后，可以直接读出哪一种外观变化带来差异。

数据文件：[逐项数值 CSV](../data/real_world_results.csv)。其中 `n` 的含义随 metric 变化；阶段／元素分母在 note 中明确标记。提升计算依据本文件转录值；它们属于本文整理计算。
