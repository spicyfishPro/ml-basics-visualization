[根目录](../../../CLAUDE.md) > [visualization](../../) > **confusion-matrix-demo**

# 混淆矩阵演示模块

## 模块职责
提供机器学习分类任务核心概念的交互式可视化演示，包括：
- 混淆矩阵的动态可视化
- Precision、Recall、F1 Score指标计算与展示
- 阈值变化对分类结果的影响演示
- 预测概率分布的四分类切割

## 入口与启动
- **主入口**: `index.html`
- **启动方式**: 直接在浏览器中打开文件
- **依赖加载**: 通过CDN自动加载Plotly.js和MathJax

## 对外接口
### 用户交互接口
- **阈值滑块**: `#thresholdSlider` (0-1000范围，对应0-1阈值)
- **实时指标显示**:
  - `#precVal` - Precision值
  - `#recVal` - Recall值
  - `#f1Val` - F1 Score值

### 可视化组件
1. **概率分布图** (`#distPlot`)
   - 四色堆叠直方图
   - 实时阈值线显示
2. **混淆矩阵** (`#cm-box-container`)
   - 动态比例矩形展示
   - TP/FN/FP/TN计数显示
3. **PR曲线** (`#prCurve`)
   - 完整PR曲线轨迹
   - 当前阈值点标记
4. **F1曲线** (`#f1Curve`)
   - 阈值-F1 Score关系图
   - 最优点可视化

## 关键依赖与配置
### 外部依赖
```html
<!-- Plotly.js v2.24.1 -->
<script src="https://cdn.bootcdn.net/ajax/libs/plotly.js/2.24.1/plotly.min.js"></script>

<!-- MathJax v3.2.2 -->
<script async src="https://cdn.bootcdn.net/ajax/libs/mathjax/3.2.2/es5/tex-mml-chtml.js"></script>
```

### 配置参数
```javascript
const N_POS = 400;    // 正样本数量
const N_NEG = 400;    // 负样本数量
const COLORS = {      // 统一颜色配置
    TP: '#22c55e',    // 绿色
    TN: '#3b82f6',    // 蓝色
    FP: '#ef4444',    // 红色
    FN: '#f97316'     // 橙色
};
```

## 数据模型
### 核心数据结构
```javascript
// 样本数据格式
{ true_label: 0|1, prob: 0-1之间的小数 }

// 预计算数据数组
thresholds: number[]    // 阈值序列
precisions: number[]    // 对应的Precision值
recalls: number[]       // 对应的Recall值
f1s: number[]          // 对应的F1 Score值
```

### 计算逻辑
1. **数据生成**: Box-Muller变换生成正态分布概率
2. **四分类计算**: 基于阈值将样本分为TP/FN/FP/TN
3. **指标计算**: 标准分类指标公式
4. **可视化更新**: 实时响应阈值变化

## 测试与质量
### 手动测试清单
- [ ] 滑块拖动响应性
- [ ] 数值计算准确性
- [ ] 可视化同步更新
- [ ] 浏览器兼容性
- [ ] 响应式布局
- [ ] 数学公式渲染

### 已知限制
- 依赖外部CDN，离线环境不可用
- 样本数量固定，无法动态调整
- 仅支持二分类问题演示

## 常见问题 (FAQ)

**Q: 如何修改样本数量？**
A: 修改JavaScript开头的`N_POS`和`N_NEG`常量。

**Q: 如何调整颜色方案？**
A: 修改CSS变量`--color-tp`等，同时更新JavaScript中的`COLORS`对象。

**Q: 阈值精度不够怎么办？**
A: 将滑块的`step`属性改为1，并在计算时除以更精细的分母。

**Q: 如何添加新的指标？**
A: 在`updateDashboard()`函数中添加计算逻辑和DOM元素更新。

## 相关文件清单
- `index.html` - 主要的演示页面
- `CLAUDE.md` - 本模块文档

## 变更记录 (Changelog)

### 2025-11-21 19:22:05
- 初始化模块文档
- 从根目录移动到标准目录结构
- 添加详细的API说明和配置文档