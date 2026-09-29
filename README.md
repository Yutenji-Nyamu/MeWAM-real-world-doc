# MetisWAM4D real world doc

真机实验的讨论记录、相关工作证据与文档框架。更新：2026-09-29。

**仅做整理信息用，非正式论文段落。** 当前结果表保留空格，实验结论由后续测量填写。

## 从这里看

| 文件 | 回答的问题 |
|---|---|
| [01 真机图表总览](docs/01_figures_tables_overview.md) | 先看哪些工作？原论文的真机表、场景图、硬件图和预测图长什么样？ |
| [02 按论文部位整理](docs/02_by_paper_component.md) | 正文设置、结果论述、主表、任务图、附录分别怎么写？ |
| [03 数值逐项对照](docs/03_real_world_numbers.md) | 每个任务各方法多少分？提升多少百分点？有哪些共同规律？ |
| [04 OOD 原文口径](docs/04_ood_claims.md) | 位置、外观、背景各自怎样留出？论文具体声称到哪一层？ |
| [05 采集、处理与标定](docs/05_data_and_calibration.md) | UR5e 仓库已有什么？RGB-D、mask、track、标定各自做什么？ |
| [06 当前实验设定](docs/06_experiment_plan.md) | 四任务、两个基线、四条件、一张主表、120 秒时限 |
| [07 交付与变更记录](docs/07_delivery_changes.md) | 两个 Overleaf 项目的全部增改删、版本与云端 PDF 验收 |
| [逐项数值 CSV](data/real_world_results.csv) | 便于后续画图、计算与回查的长表 |

## 文档项目

- [干净 CVPR 模板项目](https://www.overleaf.com/project/6abb6f3ddbd37a2e4165260d)：面向 CVPR 2027 准备，保留当前官方 author kit。
- [MetisWAM4D real world](https://www.overleaf.com/project/6abb715e006aea59b1989d4d)：从干净项目复制，专门存放真机框架。
- [本仓库中的 LaTeX 源码快照](paper/main.tex)。工作入口以 Overleaf 为准，后续同步记入变更文件。

当前官方 [cvpr-org/author-kit](https://github.com/cvpr-org/author-kit) 的正文年份仍为 **CVPR 2026**；核对提交 `291758547e923160eb4d37079b7b9f0dfce82355`。2027 Author Guidelines 页面在本次核查时显示 Page not found。项目名称表明准备目标，模板版本另行记录。

## 已确定的设定

- 平台：现有单臂 UR5e，固定主视角与腕部视角。
- 任务：放入抽屉、放进盒子、积木分类、插接；道具细节和成功容差随后补齐。
- 方法：OpenWAM-Alpha、X-WAM、MetisWAM4D。
- 条件：ID、未见桌布、未见物体外观、未见干扰物；训练和测试均随机物体位置。
- 预算：每任务每方法 20 次，单次 120 秒；四条件之间的次数分配待填写。
- 关注问题：外观变化下是否更稳；精细操作是否获得更大提升。

## 证据约定

论文结果使用明确版本和 PDF 页码；成功率、阶段分数、时间与延迟分别记录。图中读数和本记录计算的差值会标明。图表摘录用于逐项比较并链接原始论文，版权归原作者。公开记录保存研究材料与实验框架；项目私有代码的逐文件阅读笔记保存在本地工作记录。
