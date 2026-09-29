> 本文件为首轮交付记录；第二轮论文重构见 [09](09_revision2_changes.md)。当前公开仓库为 [MeWAM-real-world-doc](https://github.com/Yutenji-Nyamu/MeWAM-real-world-doc)。

# 2026-09-29 交付与完整变更记录

## 1. 已创建项目

| 项目 | 地址 | 用途 |
|---|---|---|
| CVPR2027 clean template (current official kit) | [Overleaf](https://www.overleaf.com/project/6abb6f3ddbd37a2e4165260d) | 保存当前官方完整模板，为 2027 准备 |
| MetisWAM4D real world | [Overleaf](https://www.overleaf.com/project/6abb715e006aea59b1989d4d) | 从干净项目复制的真机信息框架 |
| MetisWAM4D real world doc | [公开 GitHub](https://github.com/Yutenji-Nyamu/MetisWAM4D-real-world-doc) | 相关工作、讨论、数据与文档快照 |

当前官方模板来源为 [cvpr-org/author-kit](https://github.com/cvpr-org/author-kit)，提交 `291758547e923160eb4d37079b7b9f0dfce82355`。官方正文仍写 CVPR 2026；2027 Author Guidelines 在核查时显示 Page not found。干净项目的 15 个上游文件已逐个核对 Git blob 和工作文件哈希一致。

## 2. Overleaf 全部变更计数

| 范围／比较基准 | 新增 | 修改 | 删除 |
|---|---:|---:|---:|
| 新建干净模板，相对 Overleaf 初始空白项目 | 15 | 1 | 0 |
| 新建真机项目，相对复制出的官方模板 | 6 | 4 | 10 |
| 其他既有 Overleaf 项目 | 0 | 0 | 0 |
| UR5e-RoboTwin-Real 代码仓库 | 0 | 0 | 0 |

复制真机项目的操作发生在干净模板导入完成之后。真机项目 `cvpr.sty` 保留原始官方版本。项目设置改为 XeLaTeX / TeX Live 2026；干净项目使用 pdfLaTeX。

## 3. 干净模板：逐文件改前／改后

基准 `65594058d0e78dec43aa8b348c76346446845564` → `d47f451e06b64d3711d23fb076fe926391444a89`。全量文本差异见 [clean_template_changes.diff](../records/clean_template_changes.diff)。

| 状态 | 文件 | 改前 | 改后 |
|---|---|---|---|
| A | `.github/workflows/latex-build.yml` | 无 | 当前官方源文件，逐字节保留 |
| A | `.gitignore` | 无 | 当前官方源文件，逐字节保留 |
| A | `README.md` | 无 | 当前官方源文件，逐字节保留 |
| A | `TEMPLATE_STATUS.md` | 无 | 2027 目标／当前官方版本／来源提交说明 |
| A | `cvpr.sty` | 无 | 当前官方源文件，逐字节保留 |
| A | `fig/teaser.tex` | 无 | 当前官方源文件，逐字节保留 |
| A | `ieeenat_fullname.bst` | 无 | 当前官方源文件，逐字节保留 |
| A | `main.bib` | 无 | 当前官方源文件，逐字节保留 |
| M | `main.tex` | Overleaf 自动生成的最小文档 | 当前官方源文件，逐字节保留 |
| A | `preamble.tex` | 无 | 当前官方源文件，逐字节保留 |
| A | `rebuttal.tex` | 无 | 当前官方源文件，逐字节保留 |
| A | `sec/0_abstract.tex` | 无 | 当前官方源文件，逐字节保留 |
| A | `sec/1_intro.tex` | 无 | 当前官方源文件，逐字节保留 |
| A | `sec/2_formatting.tex` | 无 | 当前官方源文件，逐字节保留 |
| A | `sec/3_finalcopy.tex` | 无 | 当前官方源文件，逐字节保留 |
| A | `sec/X_suppl.tex` | 无 | 当前官方源文件，逐字节保留 |

## 4. 真机项目：逐文件改前／改后

基准 `8a7d6eadfa8e85feddaf60334a288dfa61a3b31e` → `62ffd001ea243332887e0eeda21bba135dbf188b`。全量文本差异见 [metis_changes.diff](../records/metis_changes.diff)。

| 状态 | 文件 | 改前 | 改后 |
|---|---|---|---|
| D | `.github/workflows/latex-build.yml` | 官方模板样例／辅助文件 | 删除，与真机框架无关 |
| M | `README.md` | 官方 author kit 使用说明 | 真机项目目录、编译方式、材料链接和当前预算口径 |
| M | `TEMPLATE_STATUS.md` | 干净模板来源说明 | 复制关系、2027 准备目标、当前 2026 官方样式和导出版说明 |
| D | `fig/teaser.tex` | 官方模板样例／辅助文件 | 删除，与真机框架无关 |
| D | `ieeenat_fullname.bst` | 官方模板样例／辅助文件 | 删除，与真机框架无关 |
| D | `main.bib` | 官方模板样例／辅助文件 | 删除，与真机框架无关 |
| M | `main.tex` | CVPR 样例文章入口 | 四页真机整理框架；前置用途说明；正文和两节附录 |
| M | `preamble.tex` | 官方可选样式示例 | 中文 XeLaTeX 支持、表格、空格和占位框命令 |
| D | `rebuttal.tex` | 官方模板样例／辅助文件 | 删除，与真机框架无关 |
| D | `sec/0_abstract.tex` | 官方模板样例／辅助文件 | 删除，与真机框架无关 |
| D | `sec/1_intro.tex` | 官方模板样例／辅助文件 | 删除，与真机框架无关 |
| D | `sec/2_formatting.tex` | 官方模板样例／辅助文件 | 删除，与真机框架无关 |
| D | `sec/3_finalcopy.tex` | 官方模板样例／辅助文件 | 删除，与真机框架无关 |
| D | `sec/X_suppl.tex` | 官方模板样例／辅助文件 | 删除，与真机框架无关 |
| A | `sec/appendix_data.tex` | 无 | 硬件、采集、标定、分支训练与展示材料 |
| A | `sec/appendix_protocol.tex` | 无 | 示范、随机化、次数、时限、汇总和任务终点表 |
| A | `sec/real_world.tex` | 无 | 平台、四任务、三方法、ID/OOD、目的与任务图占位 |
| A | `sec/results.tex` | 无 | 主表、结果论述填空顺序、OOD 与机制图占位 |
| A | `tables/real_results.tex` | 无 | 四任务、三方法、四条件及均值的空结果表 |
| A | `tables/task_criteria.tex` | 无 | 四任务成功标准空表 |

保留且内容一致的文件：`.gitignore`、`cvpr.sty`。删除项包括样例摘要／引言／格式说明／终稿说明／补充页、teaser、示例参考文献、rebuttal 和模板 CI；完整名单如上。

## 5. 云端编译与完整 PDF 验收

通过 Git 推送，在 Codex 内置浏览器打开项目、读取云端日志与 PDF；静默获取浏览器实际加载的完整云端 PDF，再逐页渲染和检查。

| 项目 | 页数 | 错误 | 警告 | 验收 |
|---|---:|---:|---:|---|
| 干净模板 | 5 | 0 | 0 | 原版图、表、参考文献及全部五页渲染正常 |
| 真机框架 | 4 | 0 | 0 | 中文、主表、空标准表、图占位和全部四页渲染正常 |

最终 PDF：[干净模板](../output/cvpr-clean.pdf)、[真机框架](../output/metis-real.pdf)。

- `cvpr-clean`：216914 bytes，SHA256 `1310027398ad36ddc831c94da2de5374cf2e695ea5c845e59eada08a0f244645`。
- `metis-real`：246417 bytes，SHA256 `205e57f3366faae440b25ae1beaaa3005a5985c97949a357babbe633fc4a81b3`。

## 6. 公开仓库内容

- README 与 7 份主题 MD：图表、论文部位、数值、OOD、数据／标定、当前方案、交付记录。
- 27 处论文图表摘录及逐项来源清单。
- 444 条指标记录的 CSV，逐项标注论文、图表、任务、方法、指标、数值及分母含义。
- 12 个真机 LaTeX 项目文件快照、2 个完整云端 PDF、全量 Overleaf diff 与验证记录。

当前实物道具、成功容差、示范量和四条件试验分配留空。原始实验结果填写位置均为占位。
