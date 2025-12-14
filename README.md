# 机器学习基础学习

> 🎯 通过交互式可视化，深入理解机器学习核心概念

## 📖 项目简介

本项目是一个专注于机器学习基础概念的可视化教学项目，通过交互式演示帮助学习者直观理解抽象的机器学习概念。项目采用纯前端技术，无需后端配置，即开即用。

## ✨ 核心特性

- **交互式可视化**：每个概念都配有动态可调的演示
- **中文界面**：完全中文化的用户界面和文档
- **无需安装**：直接在浏览器中打开即可使用
- **数学公式支持**：集成MathJax，清晰展示数学原理
- **响应式设计**：支持桌面和移动设备

## 🚀 快速开始

### 在线体验
直接克隆项目后，在浏览器中打开：

```bash
# 克隆项目
git clone https://github.com/your-username/ml-basics-visualization.git

# 打开演示
open index.html
```

### 本地运行
```bash
# 使用Python启动本地服务器
python -m http.server 8000

# 然后访问
http://localhost:8000/index.html
```

## 📚 可视化模块

### 🔍 混淆矩阵与分类指标演示
**路径**: `index.html`

通过拖动阈值滑块，实时观察：
- ✅ 真阳性 (TP) - 正确预测的正样本
- ❌ 假阴性 (FN) - 遗漏的正样本
- ⚠️ 假阳性 (FP) - 误报的负样本
- ✅ 真阴性 (TN) - 正确拒绝的负样本

**核心指标**：
- **Precision (查准率)** = TP / (TP + FP)
- **Recall (查全率)** = TP / (TP + FN)
- **F1 Score** = 2 × (Precision × Recall) / (Precision + Recall)

**可视化组件**：
1. **四色概率分布图** - 直观展示样本分类情况
2. **动态混淆矩阵** - 矩形面积与样本数量成正比
3. **Precision-Recall曲线** - 观察不同阈值下的权衡
4. **F1 Score曲线** - 找到最优阈值点

## 🛠 技术栈

- **前端框架**: 原生 HTML5 + CSS3 + JavaScript
- **可视化库**: [Plotly.js](https://plotly.com/javascript/) v2.24.1
- **数学渲染**: [MathJax](https://www.mathjax.org/) v3.2.2
- **样式框架**: CSS Variables + Flexbox + Grid
- **CDN服务**: BootCDN


## 🎯 学习目标

通过本项目的可视化演示，您将能够：

1. **理解混淆矩阵** - 掌握TP/FN/FP/TN的实际含义
2. **掌握分类指标** - 理解Precision、Recall、F1 Score的计算和应用
3. **阈值选择策略** - 学会根据业务需求选择合适的分类阈值
4. **权衡理解** - 认识到Precision和Recall之间的权衡关系
5. **直观感受概率分布** - 理解模型预测概率与分类决策的关系

## 🤝 贡献指南

欢迎为项目贡献新的可视化模块！

### 添加新模块的要求：
1. **中文界面**：所有界面和说明使用中文
2. **交互式设计**：提供动态调整和实时反馈
3. **响应式布局**：适配不同屏幕尺寸
4. **文档完整**：提供详细的模块文档
5. **CDN优先**：优先使用CDN加载依赖

## 📄 许可证

本项目采用 [MIT 许可证](LICENSE) - 欢迎自由使用和修改。

## 🙏 致谢

- [Plotly.js](https://plotly.com/javascript/) - 强大的JavaScript可视化库
- [MathJax](https://www.mathjax.org/) - 优美的数学公式渲染
- [BootCDN](https://www.bootcdn.net/) - 稳定的国内CDN服务

---

⭐ 如果这个项目对您的学习有帮助，请给一个Star支持！