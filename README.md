# Stock Analyzer Skill

自动化股票五维投资价值分析工具。

## 安装

```bash
# 确保 yahooquery 已安装
pip install yahooquery

# 添加到 PATH
export PATH="$HOME/.openclaw/workspace/skills/stock-analyzer:$PATH"
```

## 使用方法

### 快速分析
```bash
analyze-stock AAPL
analyze-stock AMZN
analyze-stock 1810.HK  # 港股
```

### 保存报告
```bash
analyze-stock TSLA --save
# 生成 TSLA-analysis-2024-02-11.md
```

### 不同格式
```bash
analyze-stock NVDA --format json    # JSON格式
analyze-stock META --format md      # Markdown格式
```

## 分析维度

### 1. 投资点位
- 52周区间位置
- 分析师目标价对比
- 入场策略建议

### 2. 基本面
- Forward P/E、PEG
- ROE、毛利率、净利率
- 护城河评估

### 3. 自由现金流 (FCF)
- FCF计算
- P/FCF估值
- FCF增长率

### 4. PEG估值
- PEG计算
- 增长预期分析

### 5. DCF估值
- 简化DCF模型
- 内在价值估算

## 示例输出

```
📊 Apple Inc. (AAPL) 投资分析报告
======================================================================

【核心数据】
• 股价: $185.92
• 市值: $2865.4B
• 52周位置: 78.5% (距高点 -12.3%)
• Forward P/E: 28.5x
• PEG: 1.85
• 分析师目标价: $200.0 (+7.6%)

【五维评分】
1. 投资点位: ⭐⭐⭐
2. 基本面/护城河: ⭐⭐⭐⭐⭐
3. FCF: ⭐⭐⭐⭐
4. PEG: ⭐⭐⭐
5. DCF: ⭐⭐⭐

【投资评级】
🎯 HOLD ⭐⭐⭐⭐ (4星)
📈 DCF内在价值: $195.5 (Upside: +5.1%)

【左侧交易建议】
⏸️ 当前处于合理区间，可分批建仓
• 第一批: $182-$190 (试仓20%)
• 第二批: $167-$182 (加仓30%)
• 重仓区: $161-$177 (重仓35%)
```

## 特点

- ✅ 自动化数据获取 (Yahoo Finance)
- ✅ 五维评分系统
- ✅ DCF内在价值估算
- ✅ 分析师目标价对比
- ✅ 支持美股、港股、A股
- ✅ 可导出 Markdown/JSON

## 免责声明

本工具仅供参考，不构成投资建议。投资有风险，入市需谨慎。
