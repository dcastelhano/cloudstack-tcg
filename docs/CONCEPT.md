# CloudStack: The Cloud Technology Trading Card Game

## 🎯 Vision

**CloudStack** is an educational trading card game that teaches cloud computing, programming, AI/ML, databases, and modern software architecture through engaging gameplay. Players build "architectures" by deploying services, writing code, and defending against incidents — learning real tech concepts while competing.

Think: **Hearthstone meets AWS certification prep.**

---

## 🎮 Core Mechanics

### Resource System: "Compute Credits"

Instead of mana, players generate **Compute Credits** each turn. Credits come in **5 domains** (like Magic's colors):

| Domain | Icon | Theme | Playstyle |
|--------|------|-------|-----------|
| **Compute** | 🖥️ | Servers, VMs, containers, serverless | Aggressive, scaling |
| **Data** | 💾 | Databases, storage, analytics, ETL | Control, card advantage |
| **Network** | 🌐 | Load balancers, CDN, API gateways | Defensive, routing |
| **Intelligence** | 🧠 | AI/ML, LLMs, analytics | Combo, late-game power |
| **Security** | 🛡️ | IAM, encryption, compliance, WAF | Disruption, protection |

**Credit Generation:**
- Start with 1 credit, gain +1 max per turn (like Hearthstone)
- Play "Infrastructure" cards to generate specific domain credits
- Some services require mixed domains (e.g., "ML Pipeline" needs 🧠🧠💾)

### Card Types

#### 1. **Services** (Creatures)
Deployable cloud services with Attack/Health stats.

```
┌─────────────────────────────┐
│ [🖥️🖥️] EC2 Instance         │
│                             │
│    ┌─────────────────┐      │
│    │   [artwork]     │      │
│    └─────────────────┘      │
│                             │
│ On Deploy: Choose instance  │
│ type (t3.micro → m5.xlarge) │
│                             │
│ Scaling: Pay 🖥️ to add      │
│ +1/+1 (max 3 times)         │
│                             │
│ ⚔️ 2    ❤️ 3                │
│                             │
│ "The backbone of cloud      │
│  computing since 2006"      │
└─────────────────────────────┘
```

**Service subtypes:**
- **Managed Services** (AWS/Azure/GCP branded)
- **Open Source** (Kubernetes, PostgreSQL, Redis)
- **Legacy Systems** (on-prem mainframes, COBOL)

#### 2. **Architectures** (Enchantments)
Persistent patterns that buff your deployment.

```
┌─────────────────────────────┐
│ [🖥️💾🌐] Microservices      │
│          Architecture       │
│                             │
│ All your Services gain:     │
│ "Resilient: If destroyed,   │
│  return to hand instead"    │
│                             │
│ Your Services cost 1 less   │
│ but max 3 Services in play  │
│                             │
│ "Loosely coupled, highly    │
│  cohesive"                  │
└─────────────────────────────┘
```

#### 3. **Incidents** (Instants/Spells)
One-time effects — attacks, defenses, fixes.

```
┌─────────────────────────────┐
│ [🛡️🛡️] DDoS Attack          │
│                             │
│ Deal 3 damage to target     │
│ Service.                    │
│                             │
│ If target has no "WAF" or   │
│ "Shield" buff, deal 6       │
│ damage instead.             │
│                             │
│ "Layer 7 floods incoming"   │
└─────────────────────────────┘
```

#### 4. **Engineers** (Hero Cards)
Powerful characters with loyalty abilities.

```
┌─────────────────────────────┐
│ [🧠🧠🧠🧠] Werner Vogels      │
│           AWS CTO           │
│                             │
│ Starting Loyalty: 4         │
│                             │
│ +1: Deploy a 1/1 Lambda     │
│ -2: Draw 2 "Serverless"     │
│ -6: All Services gain       │
│     "Auto-Scaling"          │
│                             │
│ "Everything fails, all the  │
│  time"                      │
└─────────────────────────────┘
```

#### 5. **Infrastructure** (Lands/Energy)
Generate domain-specific credits.

```
┌─────────────────────────────┐
│ AWS Region: us-east-1       │
│                             │
│ Tap: Add 🖥️ or 💾           │
│                             │
│ Activate (🖥️🖥️): Deploy     │
│ services here 1 turn faster │
│                             │
│ "N. Virginia - where half   │
│  the internet lives"        │
└─────────────────────────────┘
```

---

## 🏆 Win Conditions

**Primary:** Reduce opponent's **Uptime** from 100 to 0.

**Alternative wins:**
- **Total Outage**: Opponent has no Services and can't deploy for 2 turns
- **Compliance Victory**: Control 5+ Security services (regulatory domination)
- **Singularity**: Control 10+ Intelligence services (AI takeover)

---

## 📚 Educational Integration

### Learning Through Play

Every card includes:
1. **Real-world reference** (actual AWS/Azure/GCP service)
2. **Flavor text** with actual tech wisdom
3. **QR code** linking to documentation/tutorials

### Card Rarity = Complexity

| Rarity | Tech Level | Examples |
|--------|------------|----------|
| Common | Fundamentals | EC2, S3, basic SQL |
| Uncommon | Intermediate | Lambda, Kubernetes, Redis |
| Rare | Advanced | Step Functions, Kafka, Terraform |
| Legendary | Expert | Multi-region DR, ML pipelines, chaos engineering |

### Deck Archetypes = Career Paths

- **DevOps Deck**: Heavy on Compute + automation
- **Data Engineer Deck**: Data + Intelligence focus
- **Security Architect Deck**: Security + Network control
- **Full-Stack Deck**: Balanced, versatile
- **ML Engineer Deck**: Intelligence-heavy, combo-oriented

---

## 🎲 Gameplay Flow

### Setup
1. Each player starts with 100 Uptime
2. Draw 5 cards from 40-card deck
3. Mulligan once if desired

### Turn Structure
1. **Standup** - Untap infrastructure, gain +1 max credit, draw 1
2. **Deploy** - Play Services, Architectures, Infrastructure
3. **Sprint** - Services can attack opponent's Uptime or Services
4. **Retrospective** - End-of-turn effects resolve

### Combat
- Services attack opponent's Uptime directly OR target enemy Services
- Defender chooses blockers (like Magic)
- "Serverless" services can attack immediately
- "Stateful" services have summoning sickness

---

## 🃏 Sample Cards

### Starter Deck: "AWS Fundamentals"

| Card | Type | Cost | Effect |
|------|------|------|--------|
| EC2 Instance | Service | 🖥️🖥️ | 2/3, Scaling |
| S3 Bucket | Service | 💾 | 0/4, "Store" 2 cards |
| Lambda Function | Service | 🖥️ | 1/1, Serverless, On Attack: +2 damage |
| RDS PostgreSQL | Service | 💾💾 | 1/5, Your Data services +1 attack |
| CloudWatch Alarm | Incident | 🌐 | Draw 2 if you control 3+ Services |
| IAM Role | Architecture | 🛡️ | Your Services can't be targeted by opponent's Incidents |
| Auto Scaling Group | Architecture | 🖥️🖥️🌐 | When a Service dies, deploy a copy |
| us-east-1 | Infrastructure | - | Tap: 🖥️ or 💾 |

### Legendary Cards

| Card | Type | Cost | Effect |
|------|------|------|--------|
| **Kubernetes Cluster** | Service | 🖥️🖥️🖥️🌐🌐 | 5/5, Deploy: Create 3 1/1 Pod tokens |
| **ChatGPT API** | Service | 🧠🧠🧠🧠 | 3/3, Tap: Copy target Incident in opponent's discard |
| **Chaos Monkey** | Incident | 🖥️🛡️ | Destroy random Service (yours or opponent's) |
| **Multi-Region Failover** | Architecture | 🌐🌐🌐💾 | If your Uptime would drop to 0, restore to 20 instead (once) |
| **Jeff Bezos** | Engineer | 🖥️🖥️🖥️🖥️🖥️ | Loyalty 5, +1: Gain 2 credits, -3: Deploy any Service free, -8: Opponent discards hand |

---

## 🎨 Visual Design

### Card Frame Colors (by Domain)
- **Compute**: Orange/Amber (#FF9900 - AWS orange)
- **Data**: Blue (#0078D4 - Azure blue)
- **Network**: Green (#34A853 - GCP green)
- **Intelligence**: Purple (#7B68EE - AI/ML purple)
- **Security**: Red (#DC3545 - Alert red)

### Art Style
- Clean, modern vector illustrations
- Anthropomorphized cloud services
- Circuit board / data flow backgrounds
- Tech company logos where licensed

---

## 💰 Monetization (if commercial)

### Physical
- Starter decks ($15)
- Booster packs ($4 for 10 cards)
- Premium "Certification" sets (AWS, Azure, GCP themed)

### Digital
- Free-to-play with card unlocks
- Battle pass for cosmetics
- No pay-to-win (all cards earnable)

### Educational Licensing
- Classroom packs for bootcamps
- Corporate training editions
- Certification study bundles

---

## 🛠️ Development Phases

### Phase 1: Core Design (Week 1-2)
- [ ] Finalize 5 domain system
- [ ] Design 100 base cards
- [ ] Balance initial card costs/stats
- [ ] Write rules document

### Phase 2: Prototype (Week 3-4)
- [ ] Paper prototype for playtesting
- [ ] Digital prototype (Tabletop Simulator or custom)
- [ ] First playtest sessions

### Phase 3: Art & Polish (Week 5-8)
- [ ] Commission card art
- [ ] Design card frames
- [ ] Create rulebook PDF
- [ ] Build print-ready files

### Phase 4: Digital Version (Week 9-12)
- [ ] Game client (Unity or web-based)
- [ ] Backend (matchmaking, card collection)
- [ ] Tutorial system
- [ ] Beta release

---

## 🔗 References

- [Hearthstone Wiki](https://hearthstone.fandom.com/) - Mana crystal system
- [MTG Comprehensive Rules](https://magic.wizards.com/en/rules) - Stack, priority
- [Pokémon TCG Rules](https://www.pokemon.com/us/pokemon-tcg/rules) - Energy, evolution
- [AWS Services](https://aws.amazon.com/products/) - Service inspiration
- [Azure Services](https://azure.microsoft.com/en-us/products/) - Service inspiration
- [GCP Products](https://cloud.google.com/products) - Service inspiration

---

## 📝 Open Questions

1. **Single platform or multi-cloud?** Should decks be platform-specific (AWS deck vs Azure deck) or mixed?
2. **Competitive or cooperative?** Add co-op modes (defend against "Outage Boss")?
3. **Physical first or digital first?** Which format to prioritize?
4. **Licensing**: Can we use AWS/Azure/GCP logos, or create parody versions?
5. **Name**: CloudStack? TerraCards? InfraWars? CloudBattle?

---

*Document created: 2026-05-09*
*Author: Lucy-Code + David Castelhano*
*Status: Initial Concept*
