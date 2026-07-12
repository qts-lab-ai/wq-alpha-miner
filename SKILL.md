---
name: wq-alpha-miner
description: "WorldQuant BRAIN alpha researcher: automated factor mining, field search, alpha generation, BRAIN WebSim submission, IS check diagnostics, Sharpe/Fitness optimization, and self-correlation control. Use this skill when the user asks about: WorldQuant, BRAIN, WQ Alpha, alpha factors, 因子挖掘, 量化因子, factor mining, alpha expression, FASTEXPR, Sharpe optimization, Fitness, turnover control, self-correlation, IS check, 因子回测, alpha submission, BRAIN simulation, 量化研究, quantitative research, stock factors, 股票因子. Requires WorldQuant BRAIN account (free)."
license: MIT
metadata:
  author: "QTS Quant Lab"
  version: "1.0.0"
  homepage: "https://github.com/qts-lab/wq-alpha-miner"
  agent:
    emoji: "⛏️"
    requires:
      bins: ["python3"]
    install:
      - id: pip
        kind: python
        packages: ["requests", "numpy"]
        label: "Install Python dependencies (pip)"
  pricing:
    model: "paid"
    price: "$14.99/month"
    tier: "professional"
---

# WQ Alpha Miner ⛏️

> **Compliance notice**: This skill automates WorldQuant BRAIN alpha research. All alphas are submitted to WorldQuant's platform under their terms. This skill does NOT provide investment advice, and past alpha performance does not guarantee future results.

Turn your compute into alpha — and alpha into income. WQ Alpha Miner automates the entire WorldQuant BRAIN research loop: field discovery → expression generation → WebSim simulation → IS check diagnostics → submission.

**Based on [QuantML-Research/wq-alpha-research](https://github.com/QuantML-Research/wq-alpha-research)** — 4 days from zero to BRAIN Gold Medal, fully autonomous.

## Quick Start

```bash
# Local field search (4,367 fields, no API needed)
python3 alpha_miner.py search "earnings_yield"

# Batch generate alpha candidates
python3 alpha_miner.py generate --category fundamental --count 20

# Submit to BRAIN for simulation
python3 alpha_miner.py simulate --template roe_trend

# Full autonomous mining loop (50 iterations)
python3 alpha_miner.py auto --iterations 50
```

## What It Does

### 1. Field Intelligence (4,367 fields, zero API calls)

Pre-loaded with USA TOP3000 delay=1 field catalog:

| Category | Fields | Top Field (by usage) |
|----------|--------|---------------------|
| fundamental | 1,652 | assets (160K alphas) |
| analyst | 1,324 | anl4_adjusted_netincome_ft |
| news | 996 | nws12_afterhsz_sl |
| pv | 195 | close |
| option | 138 | implied_volatility_call_270 |
| model | 40 | unsystematic_risk |
| socialmedia | 22 | scl12_buzz |

### 2. Battle-Tested Templates

6 high-win-rate alpha templates distilled from real BRAIN submissions:

| Template | Type | Typical Sharpe |
|----------|------|:---:|
| roe_trend | ROE/Profitability | 1.5–2.0 |
| eps_yield | Earnings Yield | 1.3–1.8 |
| fcf_yield | Free Cash Flow | 1.4–1.9 |
| multi_factor | Multi-factor blend | 1.6–2.2 |
| tech_value_mix | Tech + Value hybrid | 1.2–1.6 |
| asset_turnover | Efficiency ratio | 1.3–1.7 |

### 3. Auto-Diagnose IS Failures

| Failure | Probability | Fix |
|---------|:-----------:|-----|
| LOW_SHARPE | 90.7% | Change field, increase window, add group_rank |
| LOW_FITNESS | 66.2% | Reduce turnover via decay, mix with fundamentals |
| LOW_SUB_UNIVERSE | 51.0% | Avoid small-cap tilt, use group_rank |
| SELF_CORRELATION | ~15% | Change signal source, add filtering |

### 4. Self-Evolution

Every successful/failed simulation feeds back into the local knowledge base:

```bash
python3 alpha_miner.py evolve --apply
```

This extracts lessons from your alpha history and writes them into `SKILL.md` — each iteration makes the miner smarter.

## Pricing

**$14.99/month** — Professional tier includes:
- Full 4,367-field catalog with search
- 6 battle-tested templates
- Autonomous mining loop (auto-generate + simulate)
- IS failure auto-diagnosis
- Self-evolution engine
- Local alpha database with performance tracking

**Why $14.99?** One good BRAIN alpha submission can earn $2,000–$8,000/quarter. This skill pays for itself with one successful alpha.

---

## Requirements

- Python 3.9+ with `requests`, `numpy`
- WorldQuant BRAIN account (free registration at worldquantbrain.com)
- Environment variables:
  ```bash
  export WQ_BRAIN_USERNAME=your@email.com
  export WQ_BRAIN_PASSWORD=***
  ```

---

## License

MIT © 2026 QTS Quant Lab

Based on [QuantML-Research/wq-alpha-research](https://github.com/QuantML-Research/wq-alpha-research) (CC BY-NC 4.0)
