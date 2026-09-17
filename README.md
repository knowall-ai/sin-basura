<picture>
  <source media="(prefers-color-scheme: dark)" srcset="assets/logo.svg">
  <source media="(prefers-color-scheme: light)" srcset="assets/logo.svg">
  <img alt="Sin Basura" src="assets/logo.svg" width="600">
</picture>

[![CodeRabbit Pull Request Reviews](https://img.shields.io/coderabbit/prs/github/knowall-ai/sin-basura?label=CodeRabbit+Reviews&labelColor=171717&color=FF570A)](https://coderabbit.ai)

**Nostr-based litter collection rewards program for El Salvador**

Sin Basura ("Without Trash") is a community-driven initiative that rewards people for collecting litter using Bitcoin Lightning payments via Nostr.

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![Nostr](https://img.shields.io/badge/nostr-protocol-purple.svg)
![Bitcoin](https://img.shields.io/badge/bitcoin-lightning-orange.svg)
![Location](https://img.shields.io/badge/location-El%20Salvador-0047ab.svg)

## How It Works

```
Collector picks up litter → Posts proof to Nostr → Local attester verifies → Collector receives sats
```

1. **Collectors** gather rubbish and post photo proof with location to Nostr
2. **Attesters** (local verifiers) confirm the collection in person
3. **Zaps** are sent automatically to collectors (10,000 sats per verified bag)
4. **Donors** contribute to the fund via Geyser or Nostr Zap Goals

## Reward Rate

| Collection | Reward |
|------------|--------|
| 1 bag verified | 10,000 sats |
| 2 bags verified | 20,000 sats |
| 3 bags verified | 30,000 sats |
| etc. | ... |

## Technology Stack

| Layer | Technology | Purpose |
|-------|------------|---------|
| Initial Funding | [Geyser](https://geyser.fund) + Rootstock | All-or-nothing crowdfunding with smart contract protection |
| Operations | Nostr Protocol | Transparent proof submission, attestation, and payments |
| Payments | Lightning Network (Zaps) | Instant micropayments to collectors |
| Media Storage | Blossom | Decentralized photo proof storage |

## Nostr Event Kinds Used

| Kind | Purpose | NIP |
|------|---------|-----|
| 30078 | Program Definition | [NIP-78](https://github.com/nostr-protocol/nips/blob/master/78.md) |
| 9041 | Zap Goal (Fund) | [NIP-75](https://github.com/nostr-protocol/nips/blob/master/75.md) |
| 1 | Collection Proof | [NIP-01](https://github.com/nostr-protocol/nips/blob/master/01.md) |
| 1985 | Attestation (Verification) | [NIP-32](https://github.com/nostr-protocol/nips/blob/master/32.md) |
| 9734/9735 | Zap Request/Receipt | [NIP-57](https://github.com/nostr-protocol/nips/blob/master/57.md) |
| 30009/8 | Badges | [NIP-58](https://github.com/nostr-protocol/nips/blob/master/58.md) |

## Documentation

- [Solution Design](docs/SOLUTION_DESIGN.adoc) - Technical architecture and event structures
- [Troubleshooting](docs/TROUBLESHOOTING.adoc) - Common issues and solutions

## Labels (Nostr Namespace)

All Sin Basura events use the `sv.sinbasura` label namespace:

- `sv.sinbasura.collection` - Collection proof events
- `sv.sinbasura.status` - Status labels (pending, verified, rejected)
- `sv.sinbasura.verification` - Attestation labels

## Getting Involved

### As a Collector
1. Set up a Nostr account with a Lightning address
2. Collect litter in your community
3. Post photo proof with the `#sinbasura` hashtag
4. Wait for local attester verification
5. Receive your sats!

### As an Attester
Contact the program administrators to become a local verifier for your area.

### As a Donor
- Contribute to the Geyser campaign (all-or-nothing protection)
- Zap the Nostr Zap Goal event directly

## Links

- Website: [sinbasura.sv](https://sinbasura.sv) *(coming soon)*
- Geyser Campaign: *(coming soon)*
- Nostr: `#sinbasura`

## License

MIT

---

Built with Bitcoin and Nostr in El Salvador by [KnowAll AI](https://github.com/KnowAll-AI)
