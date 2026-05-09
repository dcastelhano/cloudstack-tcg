# CloudStack TCG

> A trading card game that teaches cloud computing through gameplay

**Learn AWS, Azure, GCP, programming, AI/ML, and DevOps while battling friends!**

## 🎮 What is CloudStack?

CloudStack is an educational trading card game where players:
- **Deploy Services** (EC2, Lambda, Kubernetes) as creatures
- **Build Architectures** (Microservices, Event-Driven) as enchantments  
- **Respond to Incidents** (DDoS, Outages) with quick plays
- **Hire Engineers** (Werner Vogels, Kelsey Hightower) as hero cards

Win by reducing your opponent's **Uptime** to zero!

## 📚 Learn While You Play

Every card features:
- Real cloud service references
- Educational flavor text
- QR codes to documentation

Card rarity = tech complexity:
- **Common** = Fundamentals (EC2, S3, SQL)
- **Rare** = Advanced (Lambda, K8s, Redis)
- **Legendary** = Expert (Multi-region DR, ML Pipelines)

## 🎯 Resource System

Five domains of **Compute Credits**:

| Domain | Icon | Theme |
|--------|------|-------|
| Compute | 🖥️ | Servers, VMs, containers |
| Data | 💾 | Databases, storage, analytics |
| Network | 🌐 | Load balancers, CDN, APIs |
| Intelligence | 🧠 | AI/ML, LLMs, analytics |
| Security | 🛡️ | IAM, encryption, compliance |

## 📂 Project Structure

```
cloudstack-tcg/
├── docs/
│   ├── CONCEPT.md          # Game design document
│   ├── RULES.md            # Official rulebook
│   ├── CARD_DESIGN.md      # Card template specs
│   └── adr/                # Architecture decisions
├── cards/
│   ├── services/           # Service card definitions
│   ├── architectures/      # Architecture cards
│   ├── incidents/          # Incident cards
│   ├── engineers/          # Hero cards
│   └── infrastructure/     # Infrastructure cards
├── art/
│   ├── templates/          # Card frame templates
│   ├── icons/              # Domain icons
│   └── illustrations/      # Card art
├── digital/
│   ├── client/             # Game client (TBD)
│   └── server/             # Backend (TBD)
├── print/
│   └── sheets/             # Print-ready PDFs
└── playtesting/
    └── notes/              # Playtest feedback
```

## 🚀 Getting Started

See [CONCEPT.md](docs/CONCEPT.md) for the full game design.

## 📜 License

TBD - Educational use encouraged!

---

*A projekt by David Castelhano & Lucy-Code*
