# TradingView Pine Script Strategies

收集与维护个人编写的 TradingView (Pine Script v6) 量化交易策略与指标脚本。

## 策略目录

### 1. 同周期动能波段策略 (EMA144+MA144 叠加动能止损)

- **脚本文件**：[`momentum_swing_ema144_ma144.pine`](./momentum_swing_ema144_ma144.pine)
- **Pine Script 版本**：v6
- **核心逻辑**：
  1. **趋势/牛熊带（大周期顺势）**：
     - `EMA 144` 与 `SMA 144` 形成通道带。
     - 当 `EMA 144 > SMA 144` 判定为多头波段（绿色动能带）；
     - 当 `EMA 144 < SMA 144` 判定为空头波段（红色动能带）。
  2. **入场信号（小周期触发）**：
     - **做多（Long）**：处于多头波段 且 `MA 19` 上穿 `MA 53`（金叉）。
     - **做空（Short）**：处于空头波段 且 `MA 19` 下穿 `MA 53`（死叉）。
  3. **出场与止损（动能衰竭离场）**：
     - 多单持仓中，出现 `MA 19` 下穿 `MA 53` 即刻平仓离场；
     - 空单持仓中，出现 `MA 19` 上穿 `MA 53` 即刻平仓离场。

## 如何使用

1. 打开 [TradingView](https://www.tradingview.com/) 任意图表。
2. 展开底部的 **Pine Editor (Pine 编辑器)**。
3. 新建脚本并将 `.pine` 文件中的代码完整粘贴到编辑器中。
4. 点击 **保存 (Save)** 并点击 **添加到图表 (Add to chart)** 进行回测与查看信号。

## 免责声明

本策略仅供量化策略研究与技术分析回测参考，不构成任何投资建议。
