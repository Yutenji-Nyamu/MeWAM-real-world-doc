# 第二轮论文草稿重构：完整修改记录

2026-09-29。项目：[MetisWAM4D real world](https://www.overleaf.com/project/6abb715e006aea59b1989d4d)。

## 交付结果

两页论文片段：第 1 页为正文设置、结果段落、主结果表与任务/OOD 场景合图；第 2 页为附录平台、任务、OOD 与评估协议、任务指令表、平台照片空框。逐句依据见 [08](08_paper_draft_sentence_map.md)。

本轮 Overleaf **新增 2、修改 8、删除 1**。干净 CVPR 模板项目 **新增 0、修改 0、删除 0**；其他 Overleaf 项目 **新增 0、修改 0、删除 0**。

改前提交 `62ffd001ea243332887e0eeda21bba135dbf188b`，改后提交 `a13185d5921e942b17e409bf88871ad719f76526`。完整源文件差异见 [diff](../records/round2_overleaf_changes.diff)，机器校验见 [verification](../records/round2_verification.json)。

## 全部 Overleaf 文件前后对照

| 操作 | 文件 | 改前 | 改后 |
|---|---|---|---|
| 新增 | `figures/real_world_scenes_20260929.drawio` | 无 | 37 个原生对象；四任务各五帧，右侧三类 OOD，共 23 个空照片框 |
| 新增 | `figures/real_world_scenes_20260929.pdf` | 无 | 对应单页矢量导出，2 px 白边，PDF 中栅格图像数 0 |
| 修改 | `main.tex` | 四页材料文档；正文、结果及两个附录分别强制分页 | 两页论文片段；正文一节、附录一节；首页一句草稿说明；接入场景图 |
| 修改 | `preamble.tex` | 材料占位宏与 strip 排版 | 原生跨栏浮动、连续表格底色和附录分栏支持；移除待补／面板宏 |
| 修改 | `sec/real_world.tex` | 目的、平台、任务、条件、预算、任务与方法关系、参考与模板说明 | 四句正文设置；任务、共享示范、ID/OOD、基线、指标、附录指向 |
| 修改 | `sec/results.tex` | 结果填空顺序、记录字段、机制与视频材料 | 一段三句结果草稿：总体、外观泛化、精细操作 |
| 修改 | `sec/appendix_protocol.tex` | 五个小节：清单字段、随机化记录、预算选项、结束分类、参考说明 | 四个短段落：平台、任务与示范、OOD、评估协议；平台照片空框 |
| 修改 | `tables/real_results.tex` | 任务重复分组共 15 行方法，条件各列 | 三行方法，四任务各 ID/OOD 两列，末尾 ID/OOD 平均；30 个数值空格 |
| 修改 | `tables/task_criteria.tex` | 五列任务／道具难度／初始条件／成功终点／容差空表 | 参照 OpenWAM T12 的两列任务／语言指令，四行任务 |
| 修改 | `README.md` | 信息整理文档说明 | 论文草稿编译与文件入口；改名后的讨论仓库链接 |
| 删除 | `sec/appendix_data.tex` | B 章硬件、数据与展示产物 | 整个文件删除；论文需要的平台说明并入附录 A |

原有 `.gitignore`、`cvpr.sty`、`TEMPLATE_STATUS.md` 字节对应的 Git blob 保持一致。Overleaf 项目名称保持 `MetisWAM4D real world`。

## 用户本轮意见逐项落实

| 意见 | 本轮处理 |
|---|---|
| 从粗到细广泛参考，写成论文对应部分 | 横向重读七篇工作的对应正文和附录；08 按五类部件列原文与逐句映射 |
| 正文设置尝试写一段 | 四句短设置段落，见正文左栏 |
| 结果段简洁精准，先按拟展示结论起草 | 三句结果段落，见正文右栏；数字为空，首页标明草稿状态 |
| B 章整章不合适 | 删除 `sec/appendix_data.tex` |
| A.5 参考使用说明删除 | 从论文删除，参考依据集中在独立 MD |
| A.1/A.2 过度细碎 | 改为任务示范与 OOD 短段落 |
| 超参数“填入复现记录”等句删除 | 移除所有这类写作指令 |
| A.3 的两套预算和公式过多 | 只保留每任务每方法 20 次、120 秒、完整任务成功率 |
| A.4 结束与失败类型过多 | 改为一句逐任务终点要求 |
| 每句话核查相关工作 | M1–M4、R1–R3、A1–A14 与全部图注／表头／指令逐项映射 |
| 表2充分参考原文 | 按 OpenWAM T12 两列任务／指令重建 |
| 删除旧图2、旧图3 | 两个独立 OOD／机制占位图删除；现图2为新平台照片框 |
| 删除2.2结果记录字段 | 整段移出论文 |
| 删除2.3机制与视频材料 | 整段及其图移出论文 |
| 回顾先前 Overleaf/Draw.io 协作经验 | 阅读“0927 pipeline”聊天及公开流程的 WRITING、DRAWIO、PIPELINE 文件，沿用原生图、Git、云端全 PDF 验收与完整报告 |
| 主表每行方法、每列任务、ID/OOD两子列 | 结合 OpenWAM T6 与 T8；三行方法，全宽紧凑表 |
| 具体 OOD 用文字说 | 附录单独一段说明三类单因素变化，主表聚合为 OOD |
| 删“任务与方法的关系”长段 | 正文该小节删除；附录用一句任务覆盖说明 |
| 删参考材料、公开索引、模板来源正文 | 全部移出论文；模板来源原文件保留 |
| 重做正文场景图 | 按 OpenWAM F21 的四行执行序列与右侧 OOD 分区复刻 |
| Draw.io原生框架、实图留空、导入Overleaf | 37 个可编辑对象与23个空框；原生矢量 PDF 已接入 |
| 详细硬件与评估放附录 | 集中于附录 A 的平台与协议段落 |
| 去掉“实验目的／待检验问题” | 正文直接使用设置段落与结果段落 |
| 按正文段落、表、场景图、附录组织 | 最终两页结构与这些部件一一对应 |
| 仿 OpenWAM F20 做平台全家福空框 | 附录图2单张全景照片空框，配简短硬件图注 |
| 仓库改为 MeWAM-real-world-doc，仍公开 | 已改名并核验 Public；本地 origin 已同步 |
| 标定是什么、为什么要、和论文关系 | 聊天直接解释，并在05新增简答；实现说明集中于独立文档 |

## 渲染与校验

- XeLaTeX 云端编译：2 页，Errors 0、Warnings 0、Info 0。
- 已静默获取完整云端 PDF，逐页检查、修正段落短尾、附录图表位置、表格底色和图表编号。
- 图号 Figure 1/2，表号 Table 1/2，附录 A；各引用与页面内容一致。
- 场景图使用已安装 Draw.io 29.3.0 原生导出，检查整图与论文尺寸；文字、框与边界均可编辑。
- 主表 30 格空值、任务表四行、23 个照片空框逐项核验。
- 最终 PDF SHA256：`fe0c0826902ff900a0d8347adcfbc7c15e524812949a7a6d0ba68b848fc51b3d`。
- LaTeX 镜像共 13 个文件，逐字节与 Overleaf 本地工作树对应。

## 仓库与其他对象

公开仓库现名 [MeWAM-real-world-doc](https://github.com/Yutenji-Nyamu/MeWAM-real-world-doc)。同步 README、当前设定、数据简答、逐句依据、修改记录、LaTeX、矢量图与最终 PDF；首轮交付记录保留为历史。

仓库简介保留原文。本轮自动审批曾拦下改名操作，核对用户粘贴意见第202行后改名成功；附带的简介重写被判定超出改名授权，随后撤回该编辑。Draw.io 导出使用独立临时配置完成。Gitee 模型代码、UR5e 采集代码与其他论文项目修改均为 0。

## 公开仓库本轮文件清单

新增 7、修改 14、删除 1；同步后共 60 个文件。

| 操作 | 文件 |
|---|---|
| M | README.md |
| A | assets/draft/scene-framework.png |
| M | docs/02_by_paper_component.md |
| M | docs/05_data_and_calibration.md |
| M | docs/06_experiment_plan.md |
| M | docs/07_delivery_changes.md |
| A | docs/08_paper_draft_sentence_map.md |
| A | docs/09_revision2_changes.md |
| M | output/metis-real.pdf |
| M | paper/README.md |
| A | paper/figures/real_world_scenes_20260929.drawio |
| A | paper/figures/real_world_scenes_20260929.pdf |
| M | paper/main.tex |
| M | paper/preamble.tex |
| D | paper/sec/appendix_data.tex |
| M | paper/sec/appendix_protocol.tex |
| M | paper/sec/real_world.tex |
| M | paper/sec/results.tex |
| M | paper/tables/real_results.tex |
| M | paper/tables/task_criteria.tex |
| A | records/round2_overleaf_changes.diff |
| A | records/round2_verification.json |
