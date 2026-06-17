# Stripe Skills - Financial Operations for Agents

## Overview

Stripe Skills enables esembeegBrain agents to receive and process payments, classify financial transactions, and execute supplier payments - all within the agent framework.

**Status:** Conceptual (not yet implemented)
**Integration:** Stripe API + Hermes Agent

## Capabilities

### 1. Payment Reception
- Listen for Stripe webhooks (`payment_intent.succeeded`)
- Classify incoming payments (subscription, one-time, refund)
- Update client financial records
- Trigger Financial Agent analysis

### 2. Transaction Classification
- Auto-categorize by type, client, region
- Multi-currency support with real-time exchange rates
- Tax-relevant categorization (IVA, retentions)

### 3. Supplier Payments
- Schedule and execute payments to suppliers
- Approval workflow via Telegram (human-in-the-loop)
- Payment tracking and reconciliation

### 4. Subscription Management
- Track active subscriptions
- Detect churn (failed payments, cancellations)
- Revenue forecasting based on subscription data

### 5. Reporting
- Monthly revenue summaries
- Transaction history
- Tax-ready export formats

## Architecture

```
Stripe Webhook → Hermes Agent → Financial Agent
                                   ├── Classify
                                   ├── Analyze
                                   ├── Alert (if risk)
                                   └── Report

Founder (Telegram) → Approve Payment → Stripe API → Execute
```

## Security

- All operations via Stripe API (PCI compliant)
- Human-in-the-loop for payments > $500
- Audit trail in Obsidian knowledge base
- OpenShell sandbox for production use

## Use Cases

1. **SaaS Subscription Business** - Track MRR, detect churn, forecast revenue
2. **E-commerce** - Process orders, manage refunds, track margins
3. **Service Business** - Invoice clients, collect payments, manage cash flow
4. **Multi-currency** - Handle international payments with exchange rate management

---

*Stripe Skills spec documented: 2026-06-17*
