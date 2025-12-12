# Binance to SafePal Top-up Calculator
# 币安 -> SafePal 银行账户精准充值计算器

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
![Privacy: Client Side Only](https://img.shields.io/badge/Privacy-Client%20Side%20Only-green)

[English](#english) | [中文说明](#中文说明)

---

<a name="english"></a>
## 🇬🇧 English

### Overview
A simple calculator to determine the exact amount of USDT needed on Binance C2C to top up a specific USD amount in a SafePal Banking (Fiat24) account via Arbitrum.

**Live Demo**: [https://cosmosdiv.github.io/Binance-SafePal-Topup-Calc/](https://cosmosdiv.github.io/Binance-SafePal-Topup-Calc/)

> **Compatibility**: This tool is hardcoded for **Binance (USDT) -> Arbitrum (USDC) -> SafePal Bank**. Do not use it for other exchanges or chains (like ETH mainnet), as the fee logic will be incorrect.

### The Problem
When using crypto cards (like SafePal Visa) for subscriptions (e.g., ChatGPT Plus at $20/month), users face three main issues:

1.  **Platform Risk (Rug Pull Anxiety)**: Crypto card providers can be unstable or face sudden regulatory shutdowns. Storing a large balance on these cards is risky. **I prefer a "just-in-time" funding model**—topping up exactly what I need right before the bill hits—so if the service disappears, my loss is zero.
2.  **The "10 USDC" Trap**: SafePal has a **minimum deposit of 10 USDC**. If you calculate poorly and only $19.99 lands in your account, you can't just top up $0.01. You are forced to transfer another $10, which locks up capital that I'd rather keep in my own wallet.
3.  **Complex Fees**: Calculating C2C rates, Binance Convert slippage, Arbitrum gas fees, and SafePal's 1% deposit fee manually is error-prone.

I built this tool to reverse-calculate the exact USDT amount needed to hit the target (e.g., $20.01) in one go.

### Features
* **Reverse Calculation**: Starts from your target USD amount and works backward through all fee layers.
* **Safety Buffer**: Includes a built-in alert if the calculated top-up amount is below the 10 USDC threshold.
* **Stateless & Private**: It's a single static HTML file. No database, no cookies, no local storage. Data is lost immediately upon page refresh.

### Usage
1.  Open the [Demo Link](https://cosmosdiv.github.io/Binance-SafePal-Topup-Calc/).
2.  Enter your current banking balance and target amount.
3.  Input the current withdrawal fee (from Binance -> Arbitrum) and the real-time conversion rate (from Binance Convert).
4.  The tool outputs the exact USDT amount to buy via C2C.

---

<a name="中文说明"></a>
## 🇨🇳 中文说明

### 简介
一个简单的倒推计算器，用于计算“从币安 C2C 买多少 USDT，才能在 SafePal 银行账户里精准到账目标金额”。

**在线使用**: [https://cosmosdiv.github.io/Binance-SafePal-Topup-Calc/](https://cosmosdiv.github.io/Binance-SafePal-Topup-Calc/)

> **适用范围**：仅适用于 **Binance (USDT) -> Arbitrum (USDC) -> SafePal Bank** 这一特定链路。其他交易所或公链的费率逻辑不同，请勿混用。

### 为什么要写这个？
用 SafePal 银行卡付固定账单（比如 $20 的 ChatGPT 或 $10 的 Midjourney）时，经常遇到三个麻烦：

1.  **信任危机（怕跑路）**：现在的 U 卡服务商（包括 SafePal 银行服务）虽然方便，但毕竟不是传统银行，随时有合规或关停的风险。为了避险，我坚持**“用多少充多少”**的原则，**绝不在卡里多留一分钱**。哪怕平台明天没了，我也没损失。
2.  **门槛坑人**：SafePal 银行账户限制 **最低充值 10 USDC**。如果你因为怕跑路而算得太紧，导致最终到账只有 $19.99，你没法只补 $0.01，只能被迫再充 $10，这就违背了“不留存资金”的初衷。
3.  **损耗难算**：中间要经过“C2C汇率 -> 闪兑点差 -> 链上Gas -> 银行入金损耗”四层磨损，很难心算精准。

这个小工具就是为了解决这些问题，直接倒推算出需要买多少 USDT，确保资金**刚刚好**够付账单，既不因为少一分钱被卡住，也不多留一分钱在平台里。

### 功能特点
* **精准倒推**：自动计算包含所有手续费和 SafePal 1% 磨损后的实际成本。
* **门槛预警**：如果算出来的补款额低于 10 USDC，会提示风险，防止被卡。
* **纯净隐私**：就是一个静态 HTML 文件。移除了所有缓存功能，不保存任何输入数据，刷新页面即焚。

### 使用方法
1.  打开 [在线链接](https://cosmosdiv.github.io/Binance-SafePal-Topup-Calc/)。
2.  填入你银行卡里现在的余额（比如 $0.32）和目标金额（比如 $20.01）。
3.  看一眼币安现在的提现费（通常 0.2 USDC 左右）和闪兑汇率，填进去。
4.  照着计算结果去 C2C 买币即可。

---

*Disclaimer: Created for personal utility. Always verify fees before transactions.*
