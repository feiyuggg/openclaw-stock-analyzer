---
name: stock-analyzer
description: 自动化股票五维投资价值分析，基于yahooquery数据生成完整的投资报告
---

# Stock Analyzer Skill

自动化股票五维投资价值分析工具。输入股票代码，自动生成包含PE、PEG、FCF、DCF、护城河分析的完整投资报告。

## 使用方法

### 基础分析
```bash
# 分析单只股票
analyze-stock AAPL

# 分析并保存报告
analyze-stock TSLA --save

# 分析港股
analyze-stock 1810.HK

# 分析多只股票对比
analyze-stock AAPL MSFT GOOGL --compare
```

### 输出选项
```bash
analyze-stock AMZN --format json    # JSON格式输出
analyze-stock NVDA --format md      # Markdown格式
analyze-stock META --quiet          # 仅显示结论
```

## 分析维度

### 1. 投资点位与期权策略
- 当前估值位置（52周区间）
- 分析师目标价
- 左侧交易入场策略
- 期权策略建议

### 2. 前瞻PE + 基本面 + 护城河
- Forward P/E 分析
- 同行对比
- 盈利能力（ROE、毛利率、净利率）
- 护城河五维评估

### 3. 每股自由现金流 (FCF)
- FCF计算
- P/FCF估值
- FCF增长率

### 4. PEG估值
- PEG计算
- 增长预期分析
- 同行对比

### 5. DCF估值
- 三阶段DCF模型
- 敏感性分析
- 内在价值计算

## 示例输出

```bash
$ analyze-stock AMZN

╔════════════════════════════════════════════════════════════╗
║              亚马逊 (AMZN) 投资分析报告                      ║
╚════════════════════════════════════════════════════════════╝

【核心数据】
• 股价: $205.58
• 市值: $2.21T
• Forward P/E: 22.1x
• ROE: 22.3%

【五维评分】
1. 投资点位: ⭐⭐⭐⭐ (回调20%，合理区间)
2. 基本面/护城河: ⭐⭐⭐⭐⭐ (极宽护城河)
3. FCF: ⭐⭐⭐⭐ ($32.2B，快速增长)
4. PEG: ⭐⭐⭐⭐ (2026年PEG仅1.05)
5. DCF: ⭐⭐⭐⭐ (内在价值$240-280)

【投资评级】: BUY ⭐⭐⭐⭐ (4星)
【目标仓位】: 8-12%
【3年目标价】: $300-350 (+45-70%)

详细报告: ./reports/AMZN-analysis-2024-02-11.md
```

## 依赖

- Python 3.8+
- yahooquery
- 自动安装依赖

## 数据来源

- Yahoo Finance (通过 yahooquery)
- 实时股价、财务数据、分析师预测
