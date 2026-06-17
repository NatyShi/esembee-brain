# Financial Agent — CFO + Growth Advisor

## Overview

The Financial Agent is a hybrid CFO + Growth Advisor that operates within the gBrain multi-agent system. It combines operational financial tasks (transaction classification, payment processing) with strategic analysis (unit economics, churn detection, growth recommendations).

**Status:** Documented spec (not yet implemented)
**Role:** Specialist agent routed by gBrain Orchestrator
**Trigger words:** "payment", "revenue", "churn", "CAC", "LTV", "financial", "report", "budget", "payroll"

## Capabilities

### 1. Transaction Classification
- Receives Stripe webhook events
- Classifies: Revenue, Refund, Subscription, One-time
- Categorizes by client, product, region
- Updates financial records in knowledge base

### 2. Unit Economics Analysis

Calculates and tracks:

| Metric | Formula | Threshold |
|--------|---------|-----------|
| CAC | (Marketing + Sales Spend) / New Customers | $200-$700 (SMB SaaS) |
| LTV | ARPU × Gross Margin × Customer Lifetime | — |
| LTV/CAC | LTV / CAC | 3-5x (healthy) |
| Payback Period | CAC / (ARPU × Margin) | <12 months |
| Churn Rate | Lost Customers / Total Customers | <3.5% monthly |
| Net Margin | (Revenue - Costs) / Revenue | >50% |

### 3. Risk Detection

**Automatic alerts when:**
- Churn rate exceeds 3.5% monthly average
- CAC increases >10% month-over-month
- LTV/CAC drops below 3x
- Revenue at risk exceeds $1,000/month
- Payment to supplier is overdue

**Pattern detection:**
- Correlates churn with product usage data
- Identifies at-risk clients before they churn
- Detects CAC spikes by channel

### 4. Strategic Recommendations

**For churn risk:**
- Personalized re-engagement campaigns
- Feature adoption nudges
- Pricing adjustments

**For CAC optimization:**
- Channel performance analysis
- Budget reallocation suggestions
- Alternative acquisition strategies

**For revenue growth:**
- Upsell opportunities
- Expansion revenue tracking
- Pricing strategy recommendations

### 5. Human-in-the-Loop

All financial decisions require founder approval via Telegram:
- Supplier payments > $500
- New recurring commitments
- Budget reallocations
- Client outreach campaigns

### 6. Monthly Report

Auto-generated on the last day of each month:
- Revenue summary (MRR, growth rate)
- Churn analysis (rate, reasons, recovery)
- CAC breakdown (by channel, trend)
- LTV/CAC health check
- Upcoming payments (suppliers, payroll)
- Action items with priorities

## Integration Points

### Stripe
- Webhook receiver for payment events
- Payment execution for supplier payments
- Subscription management
- Multi-currency support

### Telegram
- Alert delivery
- Approval workflows
- Report distribution
- Quick financial queries

### Knowledge Base (Obsidian)
- Financial records storage
- Historical metric tracking
- Client financial profiles
- Audit trail

## Data Model

```yaml
# Client financial profile
client:
  name: "TechCorp México"
  mrr: 350
  cac: 340
  ltv: 12600
  ltv_cac_ratio: 37
  payback_months: 1.2
  status: "active"  # active | at-risk | churned
  last_payment: "2026-06-17"
  churn_risk: "low"  # low | medium | high

# Monthly business metrics
monthly_metrics:
  revenue: 18750
  churn_rate: 0.042
  cac: 450
  ltv_cac_ratio: 2.1
  net_margin: 0.62
  active_clients: 45
  mrr: 18750
```

## Benchmarks (Real Data)

| Metric | Benchmark | Source |
|--------|-----------|--------|
| B2B SaaS monthly churn | 3.5% | SaaSHero, 2025 |
| SMB SaaS CAC | $200-$700 | Mowsix, 2026 |
| Mid-market CAC | $1,200-$2,000 | Mowsix, 2026 |
| Healthy LTV/CAC | 3-5x | HBS, 2025 |
| CAC payback (healthy) | <12 months | Mowsix, 2026 |
| CAC increase (8 years) | +222% | Shno.co, 2026 |

## Future Enhancements

- **Payroll automation** — Calculate and process payroll based on team data
- **Tax compliance** — LATAM-specific tax calculations (IVA, IIBB, retenciones)
- **Multi-entity support** — Manage finances for multiple businesses
- **Investor reporting** — Auto-generate board-ready financial reports
- **Cash flow forecasting** — Predict future cash positions based on trends

---

*Financial Agent spec documented: 2026-06-17*
