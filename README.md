# Prediction Market Directional Accuracy Study

An exploratory data analysis of when and why prediction markets get the direction wrong — studying ~100,000 resolved markets across Kalshi, Manifold, and Polymarket.

## What this is

Prediction markets aggregate crowd beliefs into a probability. When the crowd says p > 0.5, they're calling YES. This study asks: **what separates markets where the crowd called the right direction from those where it didn't?**

We define *wrong-direction* as: crowd said YES and outcome was NO, or crowd said NO and outcome was YES. Markets at exactly 50% are excluded.

## Key findings

1. **Confidence is the strongest predictor of directional accuracy.** The further the final probability from 50%, the more often the crowd is right. At >90% confidence, wrong-direction rate drops below 5%. Near 50%, it approaches a coin flip.

2. **YES bias.** The crowd systematically leans YES — both when correct and when wrong.

3. **Market type matters more than market size.** Higher volume and more traders are associated with correct-direction markets, but the effect is modest (r ≈ −0.06 to −0.26). Longer-duration markets also tend to be more accurate.

4. **Some keywords predict direction.** Markets with "coinflip," "anytime," or "daily" in the title are overrepresented in wrong-direction outcomes (OR ≈ 6–9×). Markets with "win," "champion," or "season" skew correct (OR ≈ 0.1–0.5×). These are exploratory associations — the keyword proxies for market type, not cause.

## Notebooks

| File | Language |
|---|---|
| `notebooks/directional_reliability_en.ipynb` | English |
| `notebooks/directional_reliability_id.ipynb` | Indonesian (Bahasa Indonesia) |

Both notebooks are fully executed with embedded outputs. No data download needed to read results.

## Data

~100,000 resolved prediction markets (yes/no outcomes) from three platforms, collected 2024–2025. Raw data not included in this repository due to size.

## Setup

```bash
pip install -r requirements.txt
```

Key dependencies: `pandas`, `numpy`, `scipy`, `statsmodels`, `matplotlib`, `seaborn`, `lifelines`.
