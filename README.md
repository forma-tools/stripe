# Stripe

[![Forma](https://img.shields.io/badge/forma-stable-brightgreen.svg)](https://github.com/forma-tools/forma)
[![License](https://img.shields.io/badge/license-MIT-green.svg)](LICENSE)

> Stripe payments - customers, invoices, subscriptions, products, webhooks.

**Origin:** Vendor (1st-party) - [stripe.com/docs/stripe-cli](https://docs.stripe.com/stripe-cli)

## Install

```bash
brew install stripe-cli
```

## Quick Start

```bash
stripe login
stripe customers list --limit 5
stripe invoices list --limit 5
stripe payments list --limit 5
```

## Key Commands

```bash
# Customers
stripe customers list
stripe customers create --email "client@acme.com" --name "Acme Corp"
stripe customers retrieve cus_xxx

# Invoices
stripe invoices list --customer cus_xxx
stripe invoices create --customer cus_xxx
stripe invoices send inv_xxx

# Subscriptions
stripe subscriptions list --customer cus_xxx
stripe subscriptions create --customer cus_xxx --price price_xxx

# Payments
stripe payments list
stripe payment_intents create --amount 5000 --currency usd

# Products & Prices
stripe products list
stripe prices list --product prod_xxx

# Webhooks
stripe listen --forward-to localhost:3000/webhooks
stripe trigger payment_intent.succeeded

# All 90+ API resources
stripe resources
```

## Authentication

```bash
stripe login          # Browser OAuth
stripe whoami         # Check status
stripe config --list  # View config
```

## Forma Protocol

This tool follows the [Forma Protocol](https://github.com/forma-tools/forma).
