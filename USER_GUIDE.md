# 用户使用指南 / User Guide

## 新功能说明 / New Features

### 1. 快速设置成熟度 / Quick Set Maturity

每个维度（安全管理、安全技术、安全运营、开发安全、数据安全）的表格下方都新增了"快速设置成熟度"输入区域。

A "Quick Set Maturity" input area has been added below each dimension's table (Security Management, Security Technology, Security Operations, Development Security, Data Security).

#### 使用方法 / How to Use

1. **找到输入框** / **Locate the input field**
   - 在每个维度表格的下方
   - Below each dimension table

2. **输入目标成熟度** / **Enter target maturity**
   - 输入范围：1.0 到 5.0
   - Range: 1.0 to 5.0
   - 可以使用小数，如 3.5
   - Decimals are supported, e.g., 3.5

3. **点击"应用"按钮** / **Click "Apply" button**
   - 系统自动计算各级别完成度
   - System automatically calculates completion for all levels

4. **查看结果** / **View results**
   - 表格中的数值会自动更新
   - Values in the table will update automatically

#### 示例 / Examples

**示例 1：设置成熟度为 2.0**
- 1级：全部完成 (100%)
- 2级：全部完成 (100%)
- 3级：未完成 (0%)
- 4级：未完成 (0%)
- 5级：未完成 (0%)

**示例 2：设置成熟度为 3.5**
- 1级：全部完成 (100%)
- 2级：全部完成 (100%)
- 3级：部分完成 (50%)
- 4级：未完成 (0%)
- 5级：未完成 (0%)

**示例 3：设置成熟度为 4.8**
- 1级：全部完成 (100%)
- 2级：全部完成 (100%)
- 3级：全部完成 (100%)
- 4级：大部分完成 (80%)
- 5级：未完成 (0%)

### 2. 改进的成熟度分布堆叠图 / Improved Maturity Distribution Stacked Chart

堆叠图现在显示**加权贡献**，更准确地反映各级别对整体成熟度的影响。

The stacked chart now displays **weighted contributions**, more accurately reflecting each level's impact on overall maturity.

#### 理解堆叠图 / Understanding the Stacked Chart

- **颜色含义** / **Color meanings**:
  - 🔴 红色 (1级)：基础级别，权重最低 / Red (Level 1): Basic level, lowest weight
  - 🟠 橙色 (2级)：初级改进，权重较低 / Orange (Level 2): Initial improvement, lower weight
  - 🟡 黄色 (3级)：标准化级别，中等权重 / Yellow (Level 3): Standardized level, medium weight
  - 🔵 蓝色 (4级)：量化级别，较高权重 / Blue (Level 4): Quantified level, higher weight
  - 🟢 绿色 (5级)：优化级别，最高权重 / Green (Level 5): Optimized level, highest weight

- **如何阅读** / **How to read**:
  - 条形越高 = 该级别贡献越大 / Higher bar = greater contribution from that level
  - 高级别（蓝色、绿色）占比高 = 整体成熟度高 / High proportion of advanced levels (blue, green) = high overall maturity
  - 低级别（红色、橙色）占比高 = 需要改进 / High proportion of basic levels (red, orange) = needs improvement

- **鼠标悬停** / **Mouse hover**:
  - 将鼠标悬停在图表上可查看具体数值
  - Hover mouse over chart to see specific values
  - 显示格式：级别名称: XX.X% (加权贡献)
  - Display format: Level name: XX.X% (weighted contribution)

## 常见问题 / FAQ

### Q1: 快速设置会覆盖我手动输入的数据吗？/ Will quick set overwrite my manually entered data?

**A**: 是的，点击"应用"后会重新计算所有级别的完成度。如果您想保留手动输入的数据，请不要使用快速设置功能。

**A**: Yes, clicking "Apply" will recalculate completion for all levels. If you want to keep manually entered data, do not use the quick set feature.

### Q2: 我可以同时使用两种输入方式吗？/ Can I use both input methods simultaneously?

**A**: 可以。您可以先使用快速设置设定一个基准，然后手动微调各级别的数据。

**A**: Yes. You can first use quick set to establish a baseline, then manually fine-tune the data for each level.

### Q3: 为什么输入 3.0 和 3.5 的结果不同？/ Why are the results different when entering 3.0 vs 3.5?

**A**: 小数部分表示目标级别的完成度。3.0 表示完成到3级，3.5 表示3级完成了50%。

**A**: The decimal part represents the completion of the target level. 3.0 means completion up to level 3, while 3.5 means level 3 is 50% complete.

### Q4: 堆叠图的"加权贡献"是什么意思？/ What does "weighted contribution" mean in the stacked chart?

**A**: 加权贡献考虑了不同级别的重要性。高级别（4级、5级）对整体成熟度的影响更大，因此权重更高。

**A**: Weighted contribution considers the importance of different levels. Higher levels (4 and 5) have greater impact on overall maturity, thus higher weights.

### Q5: 我输入的成熟度等级和最终报告的成熟度不一致？/ The maturity level I entered differs from the final report?

**A**: 这是正常的。快速设置仅作用于单个维度。整体成熟度是所有维度的加权平均（或木桶原则最小值），可能与单个维度不同。

**A**: This is normal. Quick set only affects a single dimension. Overall maturity is the weighted average of all dimensions (or the minimum value in barrel principle mode), which may differ from individual dimensions.

## 技巧和建议 / Tips and Recommendations

### 💡 提示 1: 快速建立基准 / Tip 1: Quickly Establish Baseline

如果您要进行快速评估，可以为每个维度使用快速设置功能，输入预估的成熟度等级，然后生成初步报告。

For quick assessments, use the quick set feature for each dimension, enter estimated maturity levels, then generate a preliminary report.

### 💡 提示 2: 精确调优 / Tip 2: Precise Tuning

对于正式评估，建议先使用快速设置建立框架，再根据实际情况手动调整各级别的具体数值。

For formal assessments, use quick set to establish a framework first, then manually adjust specific values for each level based on actual conditions.

### 💡 提示 3: 对比分析 / Tip 3: Comparative Analysis

可以先保存当前状态的截图，然后设置不同的成熟度等级，对比堆叠图的变化，帮助理解改进方向。

Save a screenshot of the current state, then set different maturity levels to compare changes in the stacked chart, helping understand improvement directions.

### 💡 提示 4: 分阶段设置目标 / Tip 4: Set Staged Goals

使用快速设置功能可以快速模拟不同改进阶段的场景：
- 短期目标：当前成熟度 + 0.5
- 中期目标：当前成熟度 + 1.0
- 长期目标：当前成熟度 + 1.5

Use quick set to quickly simulate scenarios for different improvement stages:
- Short-term goal: Current maturity + 0.5
- Medium-term goal: Current maturity + 1.0
- Long-term goal: Current maturity + 1.5

## 支持与反馈 / Support and Feedback

如有任何问题或建议，请通过以下方式联系：
If you have any questions or suggestions, please contact via:

- 提交 Issue / Submit an Issue
- 发送反馈邮件 / Send feedback email

---

**版本 / Version**: 1.1.0
**更新日期 / Update Date**: 2024-11-19
