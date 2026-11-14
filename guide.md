# Nifty 500 Night Screener – guide

Guide for the page at https://nightscreener.github.io/ – data for **2026-11-13**, built 2026-11-14T17:10+05:30. Rules v1.0 (frozen 2026-11-06) and v1.1 (second paper portfolio). This file: https://nightscreener.github.io/guide.md

## Instructions for Claude

You are helping someone use the Nifty 500 Night Screener, a personal research page made by Karma. Answer from this guide only; say so if the guide doesn't cover it. Never give personal investment advice; explain what the page shows and how its rules work. The page is end-of-day data, not live.

Keep answers short and in plain words, with a rupee example where it helps. If someone asks whether to buy or sell a stock, explain what the page's rules say about it and that the page is a personal learning tool, not advice.

## What the app is

A personal research page made by Karma for learning. Every weekday evening (around 7–11 PM IST) a program downloads end-of-day prices and company data for the 500 stocks of the Nifty 500 index from free public sources (NSE official files; Yahoo Finance for financial statements, marked unofficial), works out ratios, scores and simple verdicts, and publishes one page. It is not live, not a broker, and not investment advice. It opens in Safari or any browser and can be added to the iPad/iPhone Home Screen like an app.

## Which stocks: Nifty 500 and the wider list (Universe W1)

The page shows **1,548 stocks** tonight: all of the Nifty 500 plus NSE mainboard shares (series EQ or BE – no SME, ETFs, REITs or InvITs) listed at least 6 months, not suspended, with a median daily traded value over the last 3 months of at least ₹1 crore and a market cap of at least ₹500 crore. To stay between 1,500 and 2,000 stocks the market-cap floor moves in ₹100–250 crore steps (not below ₹200 crore) and the traded-value floor can drop to ₹0.5 crore; a stock that stops qualifying stays 30 days. Tonight's floors: market cap ₹200 crore, traded value ₹0.5 crore a day.

- A switch at the top of Search, Verdicts and Sectors shows **Nifty 500** or **All**. Stocks outside the Nifty 500 carry an "outside Nifty 500" tag, plus "⚠️ low liquidity" when under ₹5 crore trades a day.
- **Core score and the model portfolios stay on the Nifty 500 only** – a wider list for them would be a new rules version and needs its own backtest first. Stocks outside the Nifty 500 get prices, technicals, business health (compared with all stocks on the list), investor lenses, valuation and the experimental verdict, but no Core score.
- Not collected yet for stocks outside the Nifty 500: NSE shareholding/pledges, insider trades, deals, announcements, the decisions timeline and the Company Reader. Their financial statements refresh in a weekly rotation. The exit check on such a holding shows the verdict, red flags and liquidity only.
- The downloadable offline copy covers the Nifty 500; open the link for all stocks.

## Screens and buttons

The bottom tab bar has five tabs: 🏠 Home · 🔍 Search · ⭐ Watchlist · 💼 Portfolio · ☰ More. Safari's back button and swipe-back work; each screen has its own address (for example `#/stock/TCS`).

### 🏠 Home
- The date of the data and when it was updated; a 🟡 banner if a data check needs a look or the latest update did not run.
- **Model portfolios (paper)** card: two make-believe ₹10 lakh portfolios that follow the rules (v1.0 and v1.1) compared with the Nifty 500 TRI (see below).
- The market mood line: how many stocks are above their 200-day average.
- Big buttons: 🔍 Search stocks, 🟢 Today's verdicts, 🏦 Browse sectors. A 🔴 line appears only when one of your own holdings has an exit signal.

### 🔍 Search and the ready-made screens
Type a stock name or a rule in the box; results appear right under it (30 at a time, "Show more" for the rest), with a sort menu and ✕ Clear. The ready-made screens are buttons under the box:

- **🟢 Buy list** – The screener's verdict is 🟢 Buy. Typed rule: `verdict buy`
- **Quality on Sale** – Good businesses whose price fell – they pass every Quality on Sale rule we can check. Typed rule: `quality on sale`
- **Quality 70+ with 25% margin of safety** – Quality score 70 or more, and the price at least 25% below fair value. Typed rule: `Quality >= 70 AND Margin of safety >= 25`
- **Long-term uptrend** – Price above its 200-day average – the long-term trend is up. Typed rule: `above 200 DMA`
- **Quality at a fair price** – ROCE above 15%, debt below half of equity, PE below 30. Typed rule: `ROCE > 15 AND Debt to equity < 0.5 AND PE < 30`
- **Cash-rich growers** – Sales growing over 10% a year, and at least 80% of profit arriving as cash. Typed rule: `Sales growth > 10 AND CFO/PAT > 0.8`
- **Strong banks** – Banks earning over 1% a year on their assets, priced under 2.5× book value. Typed rule: `Bank AND ROA > 1 AND P/B < 2.5`
- **Near 1-year high** – Price within 10% of its 1-year high. Typed rule: `near high`
- **Fell fast (RSI < 30)** – RSI below 30 – the price fell fast recently. Typed rule: `RSI < 30`
- **Either strong return** – ROCE or ROE above 25%, and debt below 30% of equity. Typed rule: `(ROCE > 25 OR ROE > 25) AND Debt to equity < 0.3`
- **Piotroski 7+ and no red flags** – Piotroski score 7 or more out of 9, and no ownership or management red flags. Typed rule: `Piotroski >= 7 AND Red flags = 0`
- **Promoters/insiders buying** – Insiders bought more than they sold in 12 months, and promoters did not cut their stake. Typed rule: `Insider net > 0 AND Promoter change >= 0`
- **Buffett-style quality** – Passes 60% or more of the Buffett checks, and no red flags. Typed rule: `Buffett >= 60 AND Red flags = 0`
- **Fits a Lynch fast-grower style** – Fast growers (Peter Lynch's own sorting) that pass 70% or more of the Lynch checks. Typed rule: `fits a Lynch fast-grower style`
- **Fits a Buffett-style moat** – Steady moat businesses that pass 70% or more of the Buffett checks. Typed rule: `fits a Buffett moat style`
- **Look up Trent** – Name search: Trent. Typed rule: `Trent`

### 🟢 Verdicts (experimental)
Every stock is sorted into one of five groups by simple rules (open from Home or More):

- 🟢 **Buy** – Quality 70+, price at least 25% below fair value, most methods say cheap, confidence Medium or High, no red flags, trend OK.
- 🟡 **Accumulate** – Quality 70+ and price close to fair value (or cheap but waiting for the trend). Buy slowly, in parts.
- ⚪ **Hold** – Average business, a good one at a full price, a caution flag, or fewer than 3 valuation methods to agree on a price. Nothing to do.
- 🟠 **Trim** – Price more than 30% above fair value. If you own it, think about taking some profit.
- 🔴 **Avoid / Sell** – Weak business (quality below 50, after caution-flag penalties) or a hard red flag.
- 💎 **Quality on Sale** – Good businesses whose price fell – they pass every rule we can check in 5 groups: on sale, quality, not breaking, the market's fall not the company's, genuinely cheap.
- 🔍 **Nearly on sale** – They fail just one Quality on Sale rule.

A **market gauge** line may tighten the Buy margin when the whole market looks expensive. Tap a group to see its stocks.

### 🏦 Sectors
Fifteen sector pages (banks, IT, pharma …). Each shows only the numbers that matter for that kind of business (a bank's debt-to-equity is hidden, for example), ready-made screens for the sector, the sector's middle values (medians), and a table you can sort by tapping a column heading.

### Stock page
Tap any stock. A bar under the name jumps to each section: **Summary** (Core score, verdict, why the price moved, Quality on Sale) · **Fair value** (valuation methods and the fair-value range; you can edit the DCF inputs) · **Health** (business numbers vs sector rules, close peers and the company's own history) · **Investors** (10 investor-style checklists such as Graham, Buffett, Lynch) · **Owners** (promoter holding, pledges, insider trades, management checks) · **News** (decisions timeline with the market's reaction) · **Documents** (Company Reader: what the annual report and concall say, with page numbers) · **Chart** (one-year price with the 50-day average, and what the price signals say). Buttons: ☆ Save (to the Watchlist) and 💼 Bought (to the Portfolio).

### Experts' View (More and a Home tile – shown once it has been switched on)
Today's world in brief: 6–10 factors that moved or may move Indian markets (global rates, commodities, geopolitics, India policy and data, flows, corporate), each with what happened, the channel to Indian sectors, a direction ▲/▼/– and **source links** – a factor without a source is dropped by code. Road ahead: three scenarios (good / base / bad) with what would signal each – no predictions or price targets. Weekly (Saturday): cards **through a Buffett-, Munger-, Graham-, Lynch-, Marks-, Dalio-, Kedia-, Agrawal- and Jhunjhunwala-style lens** – AI interpretations of principles they have stated publicly, **not their words or views** – with a mood, what the principles would watch and avoid, and up to 3 stocks that fit the app's own checklist for that investor ("fits the checklist", never "they would buy"). Politics: policies and their market channel only. Not investment advice.

### Watchlist buckets, notes, shared lists, alerts (review #58)
⭐ Save opens a picker: tick up to 8 buckets of your own (Long term, From YouTube …), add a note (why you saved it, up to 280 characters) and who suggested it. The Watchlist shows tabs All · your buckets · **Nifty 50** · **Bank Nifty** (filled from NSE's index files) with counts; every row shows the move since you saved it, and "By who suggested it" averages that per source. **Share list** sends a link with the stock names only – never notes, prices or your portfolio; opening it shows the list and adds nothing until you tap "Add to my watchlist". **Price alert** on a saved stock: above/below ₹X or ±X% since saved, checked against each night's close (end-of-day only, no phone notifications) – a banner on Home and a badge on the Watchlist tab.

### Finding and comparing
Recent searches and recently viewed stocks sit under the search box (✕ clears the history). Suggestions appear after 2 letters, short names work (SBI, L&T, M&M, Airtel, HUL, Kotak, ICICI Pru, Bajaj Fin), and a typo gets "Did you mean…?". **Compare** puts 2–3 stocks side by side with the better value per row marked. On a stock page opened from a list, Previous / Next (or swipe, or ← →) walk that list ("3 of 27"). Keyboard: / search, Esc clear or close, g h Home, g w Watchlist, ? the list. Long-press or right-click a number to copy it.

### ★ Best-fit investor styles
Each stock gets 1–2 business types from our own numbers (steady moat business, fast grower, cyclical, asset-cheap, bank / lender / insurer, turnaround, rate or currency sensitive; fast grower, cyclical, turnaround and asset play come from the Peter Lynch lens's own sorting). The investor lenses built for that type get a ★ on the Investors tab and are listed first; the stock page says why. ★ = this style was built for this type of business. It is not a buy signal.

### Check the AI's reading (More)
A queue of 20 stocks (mixed sectors, golden stocks first) with the Company Reader's key claims – numbers, cautions, promises – each linked to its source page. Tap Correct, Wrong or Unsure per claim and add a note; the screen shows "12 of 20 reviewed · 94% correct". Answers stay in this browser and in the Backup file; **Export my answers** saves a file you upload to docs/reader-review on GitHub (Add file → Upload files). Document signals can start counting in the verdict only after at least 20 stocks are reviewed with at least 90% correct – never in the Core score. Management credibility and future scenarios unlock after that.

### ⭐ Watchlist
Stocks you saved. Each row shows when and at what price you saved it and where from, the change since then, tonight's verdict and Core score (a "changed" badge if they changed), the **buy zone** (the highest price that still meets tonight's Buy price rule: the value the verdict used × (1 − its margin of safety)), the trend check, and "Meets the screener's Buy rule today: yes/no – not advice". **Ideas you skipped** compares stocks you removed without buying with the Nifty 500 over the same days. A saved stock that gets a hard red flag shows 🔴 "Would not buy – red flag".

### 💼 Portfolio
Your real holdings, entered with 💼 Bought / ➖ Sold (quantity, price, date, charges) or imported from a Zerodha holdings CSV (Kite or Console). It shows invested, current value, total and today's P&L, realised P&L, what the same money in the Nifty 500 TRI would be worth, and XIRR (after 30 days). Each holding has its own page with lots (oldest sold first), "LTCG in N days", a tax estimate, transactions (edit/delete) and a chart with your buys and sells.

Tax estimate: short-term gains × 20%; long-term gains for the financial year above ₹125,000 × 12.5% – before surcharge and cess, not tax advice. Rates as of 2026-11-09, source: https://www.incometaxindia.gov.in/w/determination-of-tax-in-certain-special-cases%E2%80%8B

### 🚦 Exit check (on each holding)
The same frozen Rules v1.0 exits the paper portfolios follow, shown on your own holdings:

- 🔴 **Exit signal** – a hard red flag or a Company Reader hard document flag: the rules would sell at the next close.
- 🟠 **Review at the next rebalance** (first trading day of Jan, Apr, Jul, Oct) – the Core score rank fell outside the keep zone: the top 30% of eligible stocks, or the top 50% while the holding is younger than 12 months (the tax wait). Before that date it is only a heads-up.
- 🟡 **Price far above fair value** – verdict Trim. Experimental; consider taking some profit. Not an exit by itself.
- 🟢 **Keep** – none of the above.

There is no stop-loss, trailing stop or chart-based sell signal: they were not tested, and a trend exit hurt in the backtest.

### 💾 Backup / Restore
The Watchlist and Portfolio live **only in the browser on your own device** – nothing is sent anywhere. ☰ More → 💾 Back up downloads a file (`screener-backup-YYYY-MM-DD.json`, saved to the Files app on iPad); Restore reads it back (replace or merge). A reminder appears if the last backup is more than 14 days old.

### 📊 Market (tab)
Tonight's whole-market summary, from NSE's own end-of-day files (not live): **Today in 30 seconds** (rule-based lines: Nifty 50's move, the sector that led, how many stocks rose and fell, India VIX, FII/DII money); **major indices** (close, points, day range, 1-week / 1-month / YTD, P/E vs its 5-year median – cheap / fair / expensive); a **sector heat-map** (tap a tile for that sector); **breadth** (rose / fell, new 52-week highs and lows, % above the 200-day average); **top gainers and losers** for Nifty 50, Nifty 500 or All (traded at least ₹5 crore that day), most active, volume shockers (≥ 3× usual volume and a ≥ 3% move), 52-week highs/lows; **money flow** (FII/DII net, provisional); **your stocks today** (only in your browser); **news that moved prices**; **coming up** in the next 7 days (results, dividends, splits, holidays); global closes (unofficial, Yahoo). The ← → picker reads earlier days (the last 400 trading days); Day · Week · Month switches the period.

### 📈 Pro charts
Each stock page has a **Chart** section (on the online page) with a **Full screen** button; index charts open from the Market tab. Five years of daily prices – **end of day, not live** (NSE; older prices from Yahoo, adjusted for splits, bonuses and demergers). Candles, OHLC bars, line, area or Heikin-Ashi; daily / weekly / monthly bars; ranges 1M … Max; log, linear or % scale. Indicators: 20/50/200-day simple averages, 20/50 exponential, Bollinger bands (20, 2), RSI (14), MACD (12, 26, 9), volume with its 20-day average, 52-week high/low lines, an anchored average from a day you tap, gaps of 1% or more (shaded until filled, plus an Unfilled gaps list), corporate actions and result dates, your own buys/sells and your Watchlist price. Compare with the Nifty 50, Nifty 500, the sector index or another stock (% from the first day shown). Drawing tools: trend line, ray, horizontal, vertical, parallel channel, Fibonacci, rectangle, text note and measure – with magnet, undo/redo and delete. A horizontal line can be a **watch level**: the Watchlist then says "crossed your level ₹X". Drawings stay on your device and go into the Backup file.
**For viewing only:** none of the chart tools change the Core score, the verdicts or the ghost portfolios – of everything on a chart, only momentum (12-1 month return) is part of the Core score. Charts by TradingView Lightweight Charts™ (Apache-2.0; More → Licences).

### Colours: green when you're up, red when you're down
Every gain is green with ▲ or +, every loss red with ▼ or −, zero grey. On 💼 Portfolio the totals card, the active tab and the top bar tint green or red by your overall P&L (or today's – the "Colour by" switch); the tint is faint under 2%, stronger above 2% and 10%. **Calm mode** (More → Display) keeps the green/red numbers but turns the tints off.

### ☰ More and ⚙️ Settings
More holds Verdicts, Sectors, Settings, "What the past 4 years say" (an early test), How to read this page, data checks, Backup/Restore and ❓ Help & Ask Claude. **Settings** choose what counts in the verdict (saved in this browser only):

- **Show verdicts** – master switch; OFF hides every Buy/Hold/Sell label and the model portfolios.
- **Business quality** – Stage 2 business-health score (sector percentiles). Weight 50 in the quality score.
- **Investor lenses** – Share of the 10 lenses' non-price checks passed. Weight 25.
- **Red-flag veto** – Hard red flags force Avoid (SEBI order, auditor resigned mid-term, pledge > 25%, negative net worth, weak cash + high accruals, distress + interest cover < 1.5). Caution flags (promoter stake drop, CFO churn, weak cash or distress alone) cost 10 quality points each and cap the verdict at Hold.
- **Valuation** – Consensus fair value from the methods suited to the sector. OFF = no Buy, Accumulate or Trim from price.
- **Momentum** – Buy needs price above the 200-day average, or a 12-1 month return in the top half of its sector.
- **Ownership** – Promoter holding, pledge and promoter buying/selling (weight 10), and ownership red flags.
- **Decisions timeline** – Stage 3 decisions sub-score (weight 15).
- **Management credibility** (not built yet / not counted) – Stage 5 – promises vs delivery. Not built yet, so nothing is counted.
- **Document signals** (not built yet / not counted) – Stage 5a – the Company Reader block on the stock page shows concall/annual-report signals, but they are NOT counted (OFF) until Karma has reviewed 20+ stocks (Stage 5b).
- **Future scenarios** (not built yet / not counted) – Stage 5 – bull/base/bear tracker. Not built yet.
- **Valuation mode** – Auto, Always Strict (cash-flow value) or Always Balanced (relative value).
- **Market gauge** – tightens (or, with enough history, relaxes) the Buy margin with the whole market's valuation.

## Core score vs the experimental verdict

- **Core score** (0–100): Quality 40% · Value 30% · Momentum 30%, each as a percentile within the stock's sector group, minus 10 points per caution flag (at most 30). Its rules are **frozen** (Rules v1.0) and were **backtested** on 2012–2026 history with past index members included.
- **Verdict** (Buy … Avoid): fair-value methods, Strict/Balanced modes, a 25% margin of safety, the market gauge and Quality on Sale. Useful for explanation, but **not yet backtested**, so it is labelled "experimental – not in the Core score".

## Model portfolios v1.0 / v1.1 and the Nifty 500 TRI

- **v1.0**: top 20 stocks by Core score, equal weight, at most 3 per sector group, rebalanced on the first trading day of Jan, Apr, Jul, Oct; a holding stays while in the top 30% (the top 50% while held under 12 months); a hard red flag sells it at the next close; costs included.
- **v1.1** = v1.0 + one rule: at least 10 of the 20 picks come from the 100 biggest companies by market cap (smaller falls in the backtest).
- Both are paper only (notional ₹10 lakh each), recorded every night and never edited. They are compared with the **Nifty 500 TRI** – the index with dividends added back, which is what an index fund investor really earns.
- A real-money decision waits for at least 6 months of these paper records.

## Glossary

- **Debt to equity (D/E)** – Borrowings divided by shareholders' money. Under 0.5 is comfortable for most companies; banks and NBFCs borrow by design. Example: D/E 0.3 = ₹30 borrowed for every ₹100 of shareholders' money.
- **TTM** – Trailing twelve months – the last four quarters added up, so it is always a full year even mid-year. Example: TTM sales in November = the four quarters to September.
- **CAGR** – Compound annual growth rate – the steady yearly growth that turns the first value into the last one. Example: ₹100 → ₹133 in 3 years = 10% CAGR.
- **LTCG / STCG** – Long-term vs short-term capital gains. Listed shares held more than 12 months are long-term (taxed lower, with a yearly tax-free limit); sold within 12 months they are short-term. Example: Bought 1 Jan 2025, sold 2 Feb 2026 = long-term.
- **India VIX** – NSE's 'fear gauge': how much the market expects the Nifty 50 to swing over the next 30 days, from option prices. Higher = more nervous. Example: VIX 12 = calm; VIX 25 = jittery.
- **Breadth** – How many stocks rose vs fell today. A rise led by few stocks is weaker than one where most stocks rose. Example: 1,800 up and 900 down = broad buying.
- **Business health** – How healthy the business is – profitability, debt, cash and growth – as a 0–100 score. Used by the verdict (the Buy rule needs 70+). Not the Core score. Example: 71/100 = healthier than most companies in its sector on those checks.
- **Quality vs sector** – This stock's quality rank inside its sector (0–100) – 40% of the Core score (Rules v1.0). Example: 51.8 = better quality than about half of its sector.
- **FII / DII** – Net buying (+) or selling (−) in the cash market by foreign investors (FII/FPI) and domestic institutions (DII: mutual funds, insurers). NSE's provisional end-of-day figures. Example: FIIs −₹2,000 crore = they sold ₹2,000 crore more than they bought.
- **P/E band** – The index's P/E tonight vs the median of its last 5 years' month-end P/E (NSE's index file): more than 10% below = cheap, more than 10% above = expensive, else fair. A rough gauge, not a forecast. Example: Median 21, tonight 18 → cheap.
- **Volume shocker** – Traded at least 3× its usual 20-day volume and moved at least 3% – something made people trade it today. Example: Usual 1 lakh shares, today 4 lakh, +5%.
- **ROCE** – Return on capital employed: profit before interest and tax for every ₹100 of money (debt + equity) the business uses. Example: ROCE 20% = ₹20 a year on every ₹100 invested in the business.
- **ROE** – Return on equity: yearly profit for every ₹100 of the shareholders' own money. Example: ROE 15% = ₹15 profit a year on ₹100 of equity.
- **PE** – Price ÷ yearly earnings per share: how many years of today's profit you pay for. Example: Share ₹500, profit ₹25 a share → PE 20.
- **P/B** – Price ÷ book value (net worth) per share. Used mainly for banks. Example: Price ₹300, book value ₹150 → P/B 2.
- **RSI** – A 0–100 speed meter of recent price moves (14 days). Below 30 = fell fast, above 70 = rose fast. Example: RSI 25 after a sharp 15% fall in two weeks.
- **50/200-day average (DMA)** – The average closing price of the last 50 or 200 trading days. Price above the 200-day average usually means the long-term trend is up. Example: Price ₹550 vs a 200-day average of ₹500 = 10% above: an uptrend.
- **Piotroski F-score** – 9 yes/no checks on profit, debt and efficiency; 7–9 is strong. Example: 8/9 = the business improved on 8 of 9 checks this year.
- **Margin of safety** – How far the price is below our fair-value estimate. A cushion in case the estimate is wrong. Example: Fair value ₹1,000, price ₹750 → 25% margin of safety.
- **TRI (total return index)** – An index that adds dividends back in, so it shows what an investor really earned. The plain Nifty 500 leaves dividends out. Example: Price index +10% plus about 1.3% dividends → TRI about +11.3%.
- **Biggest fall (drawdown)** – The largest drop from a high point to a later low. Example: ₹10 lakh grows to ₹12 lakh, then falls to ₹9 lakh → biggest fall −25%.
- **XIRR** – Your yearly return, counting when each rupee went in or came out – like a bank's interest rate for your buys and sells. Example: ₹10,000 in on 1 Jan and ₹5,000 on 1 Jul, worth ₹17,000 next 1 Jan → XIRR about 16% a year.
- **PEG** – PE ÷ yearly profit growth (%). Around 1 or below = the price looks fair for the growth (Peter Lynch's rule of thumb). Example: PE 30 with profit growing 30% a year → PEG 1.
- **EV/EBITDA** – Company value (market cap + debt − cash) ÷ yearly operating profit before depreciation. Compares companies with different debt. Example: EV ₹10,000 crore, EBITDA ₹1,000 crore → EV/EBITDA 10.
- **CFO/PAT** – Cash from operations ÷ reported profit. Near 1 or above = profits really arrive as cash. Example: Profit ₹100 crore, operating cash ₹90 crore → CFO/PAT 0.9.
- **Fair value** – Our estimate of what a share is worth: the middle (median) of the valuation methods that suit the sector, e.g. cash-flow (DCF), peer PE, own PE history. Example: Methods say ₹900, ₹1,000 and ₹1,150 → fair value ₹1,000.
- **STCG / LTCG** – Short-term / long-term capital gains tax on listed shares: short-term if held 12 months or less, long-term if held more than 12 months. The Portfolio shows the official rates and their source. Example: Bought 10 Jan 2026, sold 5 Jun 2026 → short-term; sold 15 Jan 2027 → long-term.
- **Core score** – Our 0–100 rank of a stock: Quality 40% · Value 30% · Momentum 30%, compared with stocks in the same sector. Example: Core 80 = better than most of its sector on the three together.
- **Verdict** – Simple rules that sort every stock into 🟢 Buy · 🟡 Accumulate · ⚪ Hold · 🟠 Trim · 🔴 Avoid. Experimental, not advice. Example: 🟢 Buy needs quality 70+, price well below fair value and no red flags.

## Search syntax with examples

- A name, symbol or industry: `Infosys`, `TCS`, `Healthcare`.
- A rule: a field, a sign (`>`, `<`, `>=`, `<=`, `=`) and a number: `ROCE > 15`, `Debt to equity < 0.5`, `PE <= 20`.
- Join rules with AND / OR: `ROCE > 15 AND PE < 30`. When you mix AND with OR, use brackets: `(ROCE > 20 OR ROE > 20) AND PE < 30`.
- Phrases: `above 200 DMA`, `near high`, `oversold`, `50-day above 200-day`, `golden cross` / `death cross` (the 50-day average crossed above / below the 200-day in the last 20 trading days), `volume spike`, `verdict buy`, `quality on sale`.
- Stocks under NSE extra surveillance (ASM/GSM) or trading under ₹5 crore a day are left out of business-number screens.
- Fields you can use: RSI, price, % from 1-year high, volume vs normal, day change, 50-day average, 200-day average, ROCE, average ROCE, ROE, average ROE, ROA, debt to equity, interest coverage, cash conversion (CFO/PAT), operating margin, debtor days, inventory days, payable days, PE, PEG, P/B, EV/EBITDA, earnings yield, sales growth per year, EPS growth per year, market cap (₹ crore), Beneish M-score, Altman Z-score, accruals, daily traded value (₹ crore), promoter pledge %, promoter holding %, business health score, Piotroski F-score, promoter stake change over 4 quarters (points), insider net buying, 12 months (₹ crore), ownership/management red flags, Core score v1 (0–100), quality score (0–100), margin of safety vs fair value (%), fair value (₹), Graham lens: % of checks passed, Buffett lens: % of checks passed, Munger lens: % of checks passed, Lynch lens: % of checks passed, Fisher lens: % of checks passed, Greenblatt lens: % of checks passed, Kedia SMILE lens: % of checks passed, QGLP lens: % of checks passed, Coffee Can lens: % of checks passed.

## Troubleshooting

- **Looks old or broken after an update:** pull down to refresh; if it still looks old, open the link with `?v=2` at the end (any number) to skip the browser's saved copy.
- **🟡 "This is <date>'s data – the latest update didn't run":** the nightly job did not run that evening (GitHub sometimes delays it). If that day was an NSE holiday, ignore it.
- **Install on iPad/iPhone:** open the link in Safari → Share → Add to Home Screen. It then opens full screen like an app.
- **My Watchlist/Portfolio disappeared:** it lives only in this browser on this device. Safari may clear data of sites you have not opened for 7 days unless the page is on the Home Screen – open it from the Home Screen icon, and use ☰ More → 💾 Back up now and then. Private browsing does not keep it at all.
- **Numbers differ from my broker:** prices are end-of-day closes; financial statements come from Yahoo Finance (unofficial) with official NSE filings where matched.

## Limits

- Free public data only: NSE official files for prices and many checks; Yahoo Finance for statements (marked unofficial).
- End-of-day only, updated in the evening on NSE trading days. Not live.
- Rules are simple and partly experimental; a backtest is not a promise.
- Personal research tool for learning – not investment advice, not a recommendation to buy or sell.

## Where to report a problem

In the app: ☰ More → ❓ Help & Ask Claude → **Report a problem** → 📋 Copy, then send the copied text to Karma on WhatsApp. It includes the app date, the screen, the device size and browser, and spaces for what you tapped and what you expected. No email address or phone number is published on the page.
