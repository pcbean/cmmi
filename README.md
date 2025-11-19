# 信息安全能力成熟度评估系统 / Information Security Capability Maturity Assessment System

## 最新更新 / Latest Updates

### 版本 1.1.0 (2024-11-19)

🎉 **重要修复和新功能** / **Important Fixes and New Features**

1. **✅ 修复：成熟度分布堆叠图显示问题**
   - 问题：全部显示成1级别（全红）
   - 解决：采用加权贡献计算方法，清晰展示各级别对整体成熟度的影响
   
2. **✨ 新功能：快速设置成熟度**
   - 问题：只能逐个调整，操作不便
   - 解决：新增快速输入功能，一键设置目标成熟度等级

详细信息请查看：
- [修复说明文档 / Changes Documentation](CHANGES.md)
- [用户使用指南 / User Guide](USER_GUIDE.md)

---

## 功能特性 / Features

### 🎯 核心功能 / Core Features

- **五维度评估** / **Five-Dimensional Assessment**
  - 安全管理 / Security Management
  - 安全技术 / Security Technology
  - 安全运营 / Security Operations
  - 开发安全 / Development Security
  - 数据安全 / Data Security

- **CMMI五级成熟度模型** / **CMMI Five-Level Maturity Model**
  - 1级：非正式执行级 / Level 1: Initial/Ad-hoc
  - 2级：计划跟踪级 / Level 2: Planned/Tracked
  - 3级：充分定义级 / Level 3: Well-Defined
  - 4级：量化控制级 / Level 4: Quantitatively Managed
  - 5级：持续优化级 / Level 5: Continuously Improving

- **多种计算模式** / **Multiple Calculation Modes**
  - 加权平均模式（推荐） / Weighted Average Mode (Recommended)
  - 木桶原则模式 / Barrel Principle Mode

### 📊 可视化图表 / Visualization Charts

- 整体成熟度仪表盘 / Overall Maturity Dashboard
- 五维能力雷达图 / Five-Dimensional Capability Radar Chart
- 各维度成熟度对比 / Dimension Maturity Comparison
- **成熟度分布堆叠图** (已优化) / **Maturity Distribution Stacked Chart** (Optimized)
- 成熟度热力图 / Maturity Heatmap

### ⚡ 新增功能 / New Features (v1.1.0)

- **💡 快速设置成熟度** / **Quick Set Maturity**
  - 直接输入1-5之间的成熟度等级 / Directly enter maturity level between 1-5
  - 支持小数（如3.5） / Supports decimals (e.g., 3.5)
  - 自动计算各级别完成度 / Automatically calculates completion for all levels
  - 每个维度独立设置 / Independent setting for each dimension

- **📈 改进的堆叠图** / **Improved Stacked Chart**
  - 加权贡献显示 / Weighted contribution display
  - 更准确的成熟度分布展示 / More accurate maturity distribution visualization
  - 鼠标悬停显示详细信息 / Detailed information on mouse hover

### 🎨 其他特性 / Other Features

- 自定义主题色 / Customizable Theme Colors
- 响应式设计 / Responsive Design
- 详细的洞察与建议 / Detailed Insights and Recommendations
- 数据验证 / Data Validation
- 自动计算未完成项 / Auto-calculation of incomplete items

---

## 快速开始 / Quick Start

1. **打开页面** / **Open the Page**
   ```
   在浏览器中打开 cmmi.html
   Open cmmi.html in a browser
   ```

2. **选择输入方式** / **Choose Input Method**
   
   **方式A：传统手动输入** / **Method A: Traditional Manual Input**
   - 逐个填写各级别的"已完成"、"部分完成"、"未完成"数量
   - Fill in "Fully Completed", "Partially Completed", "Not Completed" for each level

   **方式B：快速设置（新）** / **Method B: Quick Set (New)**
   - 在维度表格下方找到"快速设置成熟度"输入框
   - 输入目标成熟度等级（1.0-5.0）
   - 点击"应用"按钮
   
   Find "Quick Set Maturity" input below dimension table
   Enter target maturity level (1.0-5.0)
   Click "Apply" button

3. **选择计算模式** / **Select Calculation Mode**
   - 加权平均模式（推荐）：综合考虑各级别能力
   - 木桶原则模式：以最弱维度为准
   
   Weighted Average Mode (Recommended): Comprehensively considers all level capabilities
   Barrel Principle Mode: Based on weakest dimension

4. **生成报告** / **Generate Report**
   - 点击"生成成熟度诊断报告"按钮
   - 查看详细的可视化分析结果
   
   Click "Generate Maturity Assessment Report" button
   View detailed visualization analysis results

---

## 文档 / Documentation

- [📝 修复说明 / Changes Documentation](CHANGES.md) - 详细的修复说明和技术细节
- [📖 用户指南 / User Guide](USER_GUIDE.md) - 新功能使用指南和常见问题
- [💻 源代码 / Source Code](cmmi.html) - 单文件 HTML 应用

---

## 技术栈 / Technology Stack

- HTML5
- CSS3 (Flexbox, Grid)
- JavaScript (ES6+)
- Chart.js - 图表库 / Chart Library
- Chart.js Plugin Datalabels - 数据标签插件

---

## 浏览器要求 / Browser Requirements

- Chrome / Edge (推荐 / Recommended)
- Firefox
- Safari
- 支持移动端浏览器 / Mobile browsers supported

---

## 更新日志 / Changelog

### v1.1.0 (2024-11-19)
- ✅ 修复成熟度分布堆叠图显示问题
- ✨ 新增快速设置成熟度功能
- 📈 优化堆叠图使用加权贡献计算
- 📝 添加详细文档（CHANGES.md, USER_GUIDE.md）
- 🎨 新增 .gitignore 文件

### v1.0.0 (Initial Release)
- 🎉 基础功能实现
- 📊 五维度CMMI评估
- 📈 多种可视化图表
- 🎨 自定义主题色
- 📱 响应式设计

---

## 许可证 / License

请根据项目实际情况添加许可证信息。
Please add license information according to your project requirements.

---

## 贡献 / Contributing

欢迎提交 Issue 和 Pull Request！
Issues and Pull Requests are welcome!

---

**开发者 / Developer**: [Your Name]
**版本 / Version**: 1.1.0
**最后更新 / Last Updated**: 2024-11-19
