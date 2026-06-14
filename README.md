# Cryptomus

Cryptomus is a cryptocurrency payment gateway and ecosystem providing REST APIs for merchants and developers to accept crypto payments, create invoices, process payouts, manage recurring subscriptions, and access real-time exchange rate and market data across 100+ cryptocurrencies.

## APIs

| API | Description | Base URL |
|-----|-------------|----------|
| Merchant Payment API | Accept crypto payments, create invoices, manage static wallets | `https://api.cryptomus.com/v1` |
| Payout API | Process withdrawals, mass payouts, wallet transfers | `https://api.cryptomus.com/v1` |
| Recurring Payments API | Subscription billing with weekly/monthly/quarterly periods | `https://api.cryptomus.com/v1` |
| Exchange and Market Data API | Real-time rates, order books, trading, WebSocket streams | `https://api.cryptomus.com/v2` |

## Authentication

All Merchant API requests require two HTTP headers:

- `merchant` — your merchant UUID from account settings
- `sign` — MD5 hash of `base64_encode(request_body) + API_KEY`

Separate API keys are required for payment and payout operations.

## Key Endpoints

- `POST /v1/payment` — Create a payment invoice
- `POST /v1/payout` — Create a payout
- `POST /v1/recurrence/create` — Create a recurring payment plan
- `POST /v1/payment/services` — List available payment services
- `POST /v1/balance` — Get merchant and user wallet balances
- `POST /v1/transfer/to-business` — Transfer funds to business wallet
- `POST /v2/user-api/convert/calculate` — Calculate exchange conversion
- `WSS wss://api-ws.cryptomus.com/ws` — Real-time market data WebSocket

## Fees

- Payment processing: 2% standard, negotiable to 0.4% by volume
- Trading: from 0.04% (maker/taker tiered model)
- Auto-convert: Free
- Internal transfers: Free

## Resources

- Documentation: https://doc.cryptomus.com/
- Fee Schedule: https://cryptomus.com/fees/payment
- Website: https://cryptomus.com/
