# Card Schema

All cards follow this YAML structure:

```yaml
id: unique-card-id
name: Card Name
type: service|architecture|incident|engineer|infrastructure
domain: [compute, data, network, intelligence, security]  # list of required domains
cost: 3  # total credits needed
rarity: common|uncommon|rare|legendary

# For Services
stats:
  attack: 2
  health: 3
keywords: [serverless, scaling, stateful]

# For Engineers
loyalty: 4
abilities:
  - cost: "+1"
    effect: "Description"
  - cost: "-3"
    effect: "Description"

# Common fields
effect: |
  Card effect text.
  Can be multiline.
flavor: "Flavor text quote"
reference: "https://aws.amazon.com/ec2/"  # Real-world link
art: "art/illustrations/ec2-instance.png"
```

## Domain Costs

Costs are expressed as domain requirements:

- `🖥️` = 1 Compute credit
- `💾` = 1 Data credit
- `🌐` = 1 Network credit
- `🧠` = 1 Intelligence credit
- `🛡️` = 1 Security credit
- `⚪` = 1 Generic credit (any domain)

Example: `🖥️🖥️💾` = 2 Compute + 1 Data credits

## Keywords

| Keyword | Effect |
|---------|--------|
| **Serverless** | Can attack the turn it's deployed |
| **Scaling** | Pay credits to add +1/+1 |
| **Stateful** | Can't attack the turn it's deployed |
| **Resilient** | Returns to hand instead of being destroyed |
| **Cached** | Costs 1 less if you control a Data service |
| **Encrypted** | Can't be targeted by opponent's Incidents |
| **Auto-Healing** | Restore 1 health at end of turn |
| **Multi-Region** | Create a copy when deployed |
