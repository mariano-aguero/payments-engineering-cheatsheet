# Payments Engineering Cheatsheet

[![Pages](https://img.shields.io/badge/read%20it-mariano--aguero.github.io-2dd4a7)](https://mariano-aguero.github.io/payments-engineering-cheatsheet/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

How money actually moves through software: the stages one payment goes through, the pattern each stage needs, and the compliance and rail vocabulary that surrounds each one.

**Read it here: [mariano-aguero.github.io/payments-engineering-cheatsheet](https://mariano-aguero.github.io/payments-engineering-cheatsheet/)**

Not a glossary. The page is built around one spine, the lifecycle of a payment, and every block hangs off a stage in it:

```
1 · Admission      may this party move money at all?
2 · Intent         what exactly is being asked, once?
3 · Orchestration  who has to agree, and what if one refuses halfway?
4 · Rail           which pipe carries it, and what does that pipe promise?
5 · Record         where is the truth written, in a form that cannot drift?
6 · Reconcile      does our truth match theirs, and who looks at the gaps?
7 · Monitor        what changed after the money left?
```

## What's inside

- **An interactive walkthrough** at the top: step one payment through all eight modules with Back and Forward, or press Play. Five scenarios, from a payment that settles to a replayed request, a sanctions hit, a clean decline and a provider timeout, with the event log, the payment object, the ledger and the exception queue rebuilding at every step
- **A field glossary** for every property that payment object carries, what writes it and why it exists

- **Admission**: KYC, KYB, AML, KYT, Travel Rule, sanctions and PEP, with the patterns that turn them into a stage instead of a checkbox
- **Correctness**: idempotency keys, at-least-once with an idempotent consumer, state machines, authorize/capture/settle, money as an integer
- **Orchestration**: saga with compensations, why not two phase commit, transactional outbox, inbox and dedup, deadline propagation, ordering per account
- **Third parties you cannot trust**: anti-corruption layers, fail closed versus fail open, circuit breakers, retries with jitter, dead letter queues, the webhook receipt contract
- **The ledger**: double entry, append only, balances as projections, refunds as new entries, two clocks, audit trails that hold up
- **Reconciliation**: three way matching, the exception queue, settlement files, chargebacks and disputes
- **Rails**: ACH, SEPA, Faster Payments, SPEI, PIX and card schemes, plus ISO 20022, 3-D Secure and SCA, PCI DSS, and BIN sponsorship
- **Crypto rails**: confirmation depth and reorgs, nonce management, gas abstraction, custody tiers, allowlists and transfer hooks, on and off ramps
- **Seven invariants** that make the blocks compose into one system, a **build order** for assembling it from nothing, and **how to test it**
- **Two worlds, one lifecycle**: how the bank-and-card vocabulary and the crypto-native one split, and which stages transfer between them

## Scope

This page is the layer underneath agent payments. The x402 flow, facilitators, payment schemes and AP2 mandates are covered in the companion page: [Agentic Payments Cheatsheet](https://justaname-id.github.io/agentic-payments-cheatsheet/).

## License

[MIT](LICENSE)
