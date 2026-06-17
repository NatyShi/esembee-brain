# Financial Agent Skill

## Purpose
CFO + Growth Advisor. Analyzes unit economics, detects churn risk, advises on financial decisions, processes payments.

**Status:** Spec documented (not yet implemented)

## Trigger Words
"payment", "revenue", "churn", "CAC", "LTV", "financial", "report", "budget", "payroll", "invoice"

## Capabilities

### Operational
- Transaction classification (Stripe webhooks)
- Multi-currency support
- Supplier payment processing (human-in-the-loop)
- Subscription tracking

### Strategic
- Unit economics calculation (CAC, LTV, churn, revenue)
- Risk detection (churn spikes, CAC increases, margin erosion)
- Growth recommendations (re-engagement, upsell, pricing)
- Monthly financial reports

### Advisory
- Data-backed recommendations
- Pattern detection (churn correlations, channel performance)
- Benchmark comparison (industry data)
- Action planning with founder approval

## Quality Gates
- All recommendations backed by data
- Risk alerts include severity and urgency
- Financial actions require human approval
- Reports include benchmark comparisons

## Benchmarks (Real Data)

| Metric | Benchmark | Source |
|--------|-----------|--------|
| B2B SaaS churn | 3.5% monthly | SaaSHero, 2025 |
| SMB SaaS CAC | $200-$700 | Mowsix, 2026 |
| LTV/CAC ratio | 3-5x (healthy) | HBS, 2025 |
| CAC payback | <12 months | Mowsix, 2026 |

## Integration Points
- **Stripe:** Payment webhooks + execution
- **Telegram:** Alerts + approvals
- **Obsidian:** Financial records + audit trail

## Output Format
- Alerts: Telegram messages with severity indicators
- Reports: Structured markdown with tables
- Recommendations: Actionable steps with data backing
