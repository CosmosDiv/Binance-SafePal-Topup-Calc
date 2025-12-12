# Binance to SafePal Top-up Calculator
# 币安 -> SafePal 银行账户精准充值计算器

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
![Privacy: Zero Trace](https://img.shields.io/badge/Privacy-Zero%20Trace-green)
![Status: Stable](https://img.shields.io/badge/Status-Stable-blue)

[English](#english) | [中文说明](#中文说明)

---

<a name="english"></a>
## 🇬🇧 English

### Overview
This is a highly specialized, privacy-first calculator designed **exclusively** for the **Binance (USDT) -> Arbitrum (USDC) -> SafePal Banking (Fiat24)** top-up workflow.

> ⚠️ **Notice**: This tool uses hardcoded fee structures specific to SafePal's banking gateway (1% fee + floor rounding) and Binance's Arbitrum withdrawal fees. It is **NOT** suitable for other exchanges (e.g., OKX, Kraken) or other networks (e.g., Ethereum Mainnet, TRON).

### Why this tool?
In Web3 payment scenarios (e.g., paying for ChatGPT Plus, Midjourney, or other USD subscriptions via SafePal card), users often face a "Precision Problem":

1.  **The "Dust" Issue**: If you buy too much USDT, the excess dust sits idle in your wallet.
2.  **The "Threshold" Trap**: If you buy slightly less than needed (e.g., ending up with $19.99 for a $20 bill), you cannot simply top up $0.01. SafePal/Fiat24 has a **minimum deposit requirement of 10 USDC**. This forces you to transfer another $10, locking up unnecessary capital.

**This tool solves this by reverse-engineering the exact amount of USDT you need to buy via C2C to land exactly the target amount (e.g., $20.01) in your bank account.**

### Key Features
* **Specific Logic**: Accounts for C2C rates, Binance Convert slippage, Arbitrum network fees, and SafePal's banking deposit fees (1% + rounding down).
* **Zero Trace (V6)**: This is a single-file HTML tool. All `localStorage` functions have been removed. Data exists only in your browser's RAM and vanishes instantly upon refresh. No cookies, no history.
* **Smart Safety**: Includes a built-in alert for the "10 USDC Minimum" threshold to prevent stuck transactions.

### Usage
1.  **Input**: Enter your current SafePal USD balance and your target amount (e.g., $20.01).
2.  **Fees**: Confirm the current Binance Arbitrum withdrawal fee (usually 0.17 - 0.24 USDC).
3.  **Rates**: Check the real-time `USDT -> USDC` preview on Binance Convert and input the values.
4.  **Result**: The tool calculates exactly how much USDT to buy, ensuring you cover all fees and land safely above your target.

---

<a name="中文说明"></a>
## 🇨🇳 中文说明

### 项目简介
这是一个专为 **币安 (Binance) -> Arbitrum (USDC) -> SafePal 银行账户 (Fiat24)** 这一特定资金链路设计的精准充值计算器。

> ⚠️ **注意**：本工具针对 SafePal 银行的特定损耗逻辑（1% 手续费 + 向下取整）进行了硬编码。它**不适用**于其他交易所（如 OKX）或其公链（如 ETH 主网）。

### 开发背景与痛点
在使用 SafePal 银行卡支付固定金额账单（如 ChatGPT Plus 的 $20/月）时，用户经常面临两难：

1.  **估算困难**：很难心算出一笔 $20 的入金，到底需要在币安买多少 USDT（中间涉及 C2C 汇率、闪兑点差、链上 Gas、银行入金损耗等四重磨损）。
2.  **门槛陷阱**：这是最致命的痛点。如果你算少了，导致最终到账只有 $19.99，你无法只补 $0.01。因为 SafePal 银行账户有 **“最低充值 10 USDC”** 的限制。这意味着你必须被迫再充 $10，导致资金无意义积压。

**本工具通过“逆向倒推算法”，帮助你精准计算出 C2C 购买金额，确保“一次过”，且不留多余残值。**

### 核心功能
* **场景以此为准**：仅服务于 Binance USDT 转 SafePal USDC (Arb) 场景。
* **V6 无痕模式**：这是一个纯静态 HTML 文件。代码中移除了所有本地存储（LocalStorage）功能。您的输入数据仅存在于当前页面的内存中，**刷新页面即焚**，不在电脑或手机上留下任何痕迹（配合隐私模式使用效果更佳）。
* **风控预警**：自动检测补款金额是否低于 10 USDC，防止因金额过小被交易所或银行卡住。

### 如何使用
1.  **填参数**：输入你 SafePal 银行里现在的余额（比如 $0.32），和目标金额（比如 $20.01）。
2.  **查费率**：看一眼币安现在的提现费是多少（通常是 0.17 ~ 0.24 USDC）。
3.  **看汇率**：去币安“闪兑”页面，看一眼 1000 USDT 能换多少 USDC，填进去。
4.  **得结果**：工具会告诉你：“去 C2C 买 xx.xx USDT”。

---

### Security / 安全声明

* **Source Code**: The logic is transparent in `index.html`. No external scripts, no analytics.
* **Data Privacy**: No data is sent to any server. Everything runs client-side.
* **源代码**: 逻辑完全透明，可见 `index.html`。无外部脚本，无统计代码。
* **数据隐私**: 不会向任何服务器发送数据。所有计算完全在本地完成。

*Disclaimer: This tool is for estimation purposes only. Always verify transaction details before confirming on blockchain.*
*免责声明：本工具仅供估算参考。在区块链上确认交易前，请务必核对实际金额。*
