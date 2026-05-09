# CloudStack TCG — Educational "Study" System

## Overview

Each card has a **back side** with educational content. Players can "Study" (flip) a card **once per match** to:
1. Learn real-world concepts
2. Discover synergies with other cards
3. Optionally gain a small in-game bonus for learning

## Card Back Content

### 1. Real-World Reference
```yaml
back:
  service_name: "AWS Lambda"
  category: "Compute > Serverless"
  launched: 2014
  documentation: "https://docs.aws.amazon.com/lambda/"
  certification: "AWS Solutions Architect Associate"
```

### 2. Learning Notes
```yaml
  learn:
    what: "Run code without provisioning servers"
    when_to_use:
      - "Event-driven workloads"
      - "APIs with variable traffic"
      - "Data processing pipelines"
    when_not_to_use:
      - "Long-running processes (>15 min)"
      - "Consistent high-traffic (consider containers)"
    pricing_model: "Pay per invocation + duration"
```

### 3. Synergy Cards ("Connects To")
```yaml
  synergies:
    - card_id: "api-gateway"
      relationship: "triggers"
      bonus: "Serverless API Stack"
      bonus_effect: "+1 attack when both in play"
      real_world: "API Gateway invokes Lambda for request handling"
      
    - card_id: "dynamodb"
      relationship: "reads/writes"
      bonus: "Serverless Data Layer"
      bonus_effect: "Draw a card when Lambda attacks"
      real_world: "Lambda commonly uses DynamoDB for state"
      
    - card_id: "s3-bucket"
      relationship: "triggered_by"
      bonus: "Event Processing"
      bonus_effect: "Lambda gains +1 health"
      real_world: "S3 events can trigger Lambda functions"
```

### 4. Architecture Patterns
```yaml
  patterns:
    - name: "Serverless Web App"
      cards: ["cloudfront", "api-gateway", "lambda", "dynamodb"]
      description: "Classic serverless architecture"
      
    - name: "Event-Driven Processing"
      cards: ["s3-bucket", "lambda", "sqs", "lambda"]
      description: "Async event processing pipeline"
```

## "Study" Mechanic

### How It Works
1. **Once per match**, click "Study" on any card (yours or opponent's)
2. Card flips to show educational back
3. You learn the synergies and real-world context
4. **Optional bonus**: If you control a synergy pair, activate the bonus!

### UI Flow
```
┌─────────────────────────────────────┐
│ 🔄 STUDY MODE                       │
│                                     │
│ ┌─────────┐    ┌─────────────────┐  │
│ │ Lambda  │ => │ 📚 LEARN        │  │
│ │ [front] │    │                 │  │
│ └─────────┘    │ What: Serverless│  │
│                │ compute...      │  │
│                │                 │  │
│                │ 🔗 SYNERGIES    │  │
│                │ + API Gateway   │  │
│                │ + DynamoDB      │  │
│                │ + S3 Bucket     │  │
│                │                 │  │
│                │ 📖 Docs →       │  │
│                └─────────────────┘  │
│                                     │
│ [Close] [Activate Synergy Bonus!]   │
└─────────────────────────────────────┘
```

### Study Bonus Activation
If you study a card AND control its synergy partner:
- "You studied Lambda while controlling API Gateway!"
- "Serverless API Stack activated: +1 attack to both!"

## Synergy Categories

### 1. Service Pairs (Direct Connections)
| Card A | Card B | Synergy Name | Bonus |
|--------|--------|--------------|-------|
| API Gateway | Lambda | Serverless API | +1 attack each |
| Lambda | DynamoDB | Serverless Data | Draw when attacking |
| Lambda | S3 | Event Processing | +1 health |
| RDS | ElastiCache | Cached Database | -1 cost to Data cards |
| EKS | Fargate | Managed K8s | Pods have +1 health |
| CloudFront | S3 | Static Hosting | Can't be targeted |
| ALB | EC2 | Load Balanced | Redirect damage |
| SageMaker | S3 | ML Pipeline | +1 attack per turn |
| Bedrock | Lambda | AI Function | Copy ability once |

### 2. Architecture Stacks (3+ Cards)
| Stack Name | Cards Required | Bonus |
|------------|----------------|-------|
| Serverless Trio | API GW + Lambda + DynamoDB | All gain Serverless keyword |
| Data Lake | S3 + Glue + Redshift | Draw 2 cards |
| ML Platform | S3 + SageMaker + Bedrock | Train gives +2 instead of +1 |
| Security Stack | WAF + GuardDuty + KMS | Opponent's incidents cost +1 |

### 3. Domain Mastery (Infrastructure Synergy)
| Condition | Bonus |
|-----------|-------|
| Control 4+ Compute Infrastructure | Compute services cost -1⚪ |
| Control 4+ Data Infrastructure | Draw extra card per turn |
| Control 4+ Security Infrastructure | Services have Shield |

## Implementation

### Card Data Structure
```typescript
interface CardEducation {
  // Real-world reference
  serviceName: string;
  category: string;
  launched?: number;
  documentation: string;
  certification?: string;
  
  // Learning content
  whatItDoes: string;
  whenToUse: string[];
  whenNotToUse: string[];
  pricingModel?: string;
  
  // Synergies
  synergies: Synergy[];
  patterns: Pattern[];
}

interface Synergy {
  cardId: string;
  relationship: 'triggers' | 'reads' | 'writes' | 'protects' | 'enhances';
  synergyName: string;
  bonusEffect: string;
  realWorldExplanation: string;
}
```

### Game State Additions
```typescript
interface Player {
  // ... existing fields
  hasStudied: boolean;  // Once per match
  activeSynergies: string[];  // Currently active synergy bonuses
}
```

### Synergy Resolution
```typescript
function checkSynergies(player: Player): ActiveSynergy[] {
  const synergies: ActiveSynergy[] = [];
  
  for (const card of player.field) {
    for (const syn of card.education.synergies) {
      if (player.field.some(c => c.id === syn.cardId)) {
        synergies.push({
          name: syn.synergyName,
          cards: [card.id, syn.cardId],
          effect: syn.bonusEffect,
        });
      }
    }
  }
  
  return synergies;
}
```

## Educational Value

### What Players Learn
1. **Service Relationships**: How AWS services connect in real architectures
2. **Use Cases**: When to use each service
3. **Architecture Patterns**: Common cloud design patterns
4. **Certification Prep**: Which services appear on which exams
5. **Pricing Awareness**: How services are billed

### Gamification of Learning
- Synergy bonuses reward knowing how services connect
- "Study" mechanic encourages reading the educational content
- Patterns teach complete architectures, not just individual services
- Competitive advantage from understanding the tech

## Example: Full Lambda Card

### Front
```
┌─────────────────────┐
│ [1] Lambda Function │
│ 🖥️ Service          │
│                     │
│ Serverless. +2 dmg  │
│ when attacking.     │
│ Destroy at end of   │
│ turn.               │
│                     │
│ ⚔️1        ❤️1      │
└─────────────────────┘
```

### Back (Study Mode)
```
┌─────────────────────────────────┐
│ 📚 AWS Lambda                   │
│ Compute > Serverless            │
│ Launched: 2014                  │
├─────────────────────────────────┤
│ Run code without servers.       │
│ Pay only for compute time.      │
│                                 │
│ ✅ Use for:                     │
│ • Event-driven workloads        │
│ • Variable traffic APIs         │
│ • Data processing               │
│                                 │
│ ❌ Avoid for:                   │
│ • Long-running (>15 min)        │
│ • Consistent high traffic       │
├─────────────────────────────────┤
│ 🔗 SYNERGIES                    │
│                                 │
│ + API Gateway → Serverless API  │
│ + DynamoDB → Serverless Data    │
│ + S3 Bucket → Event Processing  │
├─────────────────────────────────┤
│ 📖 docs.aws.amazon.com/lambda   │
│ 🎓 Solutions Architect Assoc.   │
└─────────────────────────────────┘
```
