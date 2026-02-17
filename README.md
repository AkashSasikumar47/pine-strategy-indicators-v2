# Pine Strategy Indicators v2

## Overview
A collection of professional-grade Pine Script indicators for TradingView, focused on volatility, momentum, and trend analysis. Each indicator is implemented with clean code and customizable parameters for technical analysis and strategy development.

## Included Indicators

### Average True Range (ATR)
**Purpose:** Measures market volatility to assess price movement potential.
**Core Logic:** Calculates the true range (maximum of high-low, high-previous close, and low-previous close) and applies a simple moving average over the specified period.
**Key Parameters:**
- ATR Length: Period for averaging (default: 14)

![ATR](images/atr.png)

**Typical Use Case:** Setting dynamic stop-loss levels and position sizing based on current volatility conditions. Higher ATR values indicate increased volatility, suggesting wider stops.

---

### Bollinger Bands
**Purpose:** Identifies volatility and potential price extremes using statistical bands.
**Core Logic:** Plots a moving average (basis) with upper and lower bands positioned at a specified number of standard deviations from the basis.
**Key Parameters:**
- Length: Period for SMA calculation (default: 20)
- Source: Price input (default: close)
- StdDev Multiplier: Band width in standard deviations (default: 2.0)
- Offset: Horizontal shift (default: 0)

![Bollinger Bands](images/bollinger_bands.png)

**Typical Use Case:** Identifying squeeze patterns (low volatility) that precede breakouts, and spotting potential reversals when price touches or exceeds the bands.

---

### Commodity Channel Index (CCI)
**Purpose:** Momentum oscillator for identifying cyclical trend deviations.
**Core Logic:** Measures the difference between the typical price (HLC3) and its simple moving average, normalized by the mean deviation multiplied by 0.015.
**Key Parameters:**
- Length: Lookback period (default: 20)
- Source: Price input (default: hlc3)
- Smoothing Method: MA type for smoothing line (SMA/EMA/RMA/WMA/VWMA)
- Smoothing Length: Period for smoothing (default: 5)

![CCI](images/cci.png)

**Typical Use Case:** Identifying overbought conditions above +100 and oversold conditions below -100. Divergences between CCI and price can signal potential reversals.

---

### Moving Average Convergence Divergence (MACD)
**Purpose:** Trend-following momentum indicator for identifying trend changes and momentum shifts.
**Core Logic:** Calculates the difference between fast and slow exponential moving averages, with a signal line (EMA of MACD) and histogram showing the difference between MACD and signal.
**Key Parameters:**
- Fast EMA Length: Short-term period (default: 12)
- Slow EMA Length: Long-term period (default: 26)
- Signal EMA Length: Signal line period (default: 9)
- Source: Price input (default: close)

![MACD](images/macd.png)

**Typical Use Case:** Identifying trend direction and momentum. Bullish signals occur when MACD crosses above the signal line; bearish signals when crossing below. Histogram expansion indicates momentum strength.

---

### Williams %R
**Purpose:** Momentum oscillator for identifying overbought and oversold conditions.
**Core Logic:** Calculates the position of the current close relative to the high-low range over the specified period, expressed as a negative percentage from 0 to -100.
**Key Parameters:**
- Length: Lookback period (default: 14)
- Source: Price input (default: close)

![Williams %R](images/williams_r.png)

**Typical Use Case:** Values above -20 indicate overbought conditions (potential reversal down), while values below -80 indicate oversold conditions (potential reversal up). Often used for confirmation with other indicators.

---

## How to Use

1. Open TradingView and navigate to the Pine Editor (Alt+E or via Chart menu)
2. Copy the desired indicator code from the `/indicators` directory
3. Paste the code into the Pine Editor
4. Click "Add to Chart" to apply the indicator
5. Adjust parameters via the indicator settings (gear icon) to suit your trading timeframe and strategy

## Disclaimer

These indicators are provided for educational and research purposes only. They are technical analysis tools and should not be considered financial advice. Past performance does not guarantee future results. Always conduct thorough analysis and risk management before making trading decisions.
