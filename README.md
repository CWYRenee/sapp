# Sapp - Private P2P Messaging & Payments

Sapp is a privacy-first mobile superapp powered by Solana. Send encrypted peer-to-peer messages, transfer crypto privately, earn yield, and spend seamlessly with integrated card payments—all in one place.

## Features

- **End-to-End Encrypted Messaging**: All messages are encrypted using P2P technology via Hypercore
- **Private Crypto Transfers**: Send SOL and tokens with transaction privacy using zero-knowledge proofs
- **Cross-Chain Privacy**: Swap and transfer assets across blockchains without exposing transaction paths
- **Integrated Card Payments**: Order a Mastercard to spend crypto in the real world
- **Earn Yield**: Deposit stablecoins to earn yield through integrated DeFi protocols
- **Modern Minimal UI**: Clean, type-driven design with seamless UX

## Privacy Technologies

### Radr Labs - ShadowWire
Private on-chain transfers on Solana using Bulletproofs (zero-knowledge proofs) to hide transaction amounts while keeping everything verifiable on-chain.

### SilentSwap
Non-custodial, compliant privacy service for cross-chain transfers. Obfuscates transaction paths by leveraging shielded transactions and routing through high-volume markets—no pooled mixers or centralized exchanges.

### Starpay
Privacy-focused payment infrastructure for card issuance and ZK Swap. Enables anonymous crypto-to-crypto execution and real-world spending through integrated Mastercard.

## Architecture

| Component | Description |
|-----------|-------------|
| **Core/Crypto** | ShadowWire, SilentSwap, and Starpay integrations for private transactions |
| **Core/Messaging** | Hypercore P2P infrastructure for encrypted messaging |
| **Core/Solana** | Wallet management, transaction building, price feeds |
| **Core/StarPay** | Card issuance, management, and payment processing |
| **Features/Messaging** | Conversations, chat, send crypto in chat, split bills |
| **Features/Wallet** | Portfolio view, send/receive, swap, earn yield, card management |

## Tech Stack

- **SwiftUI** - Modern declarative UI framework
- **Solana** - Blockchain for transactions and DeFi
- **Hypercore** - P2P messaging infrastructure
- **ShadowWire** - Private transfers with Bulletproofs
- **SilentSwap** - Cross-chain privacy transfers
- **Starpay** - Card issuance and ZK payments

## Setup

### Requirements

- macOS with Xcode 15+
- iOS 17+ device or simulator
- Node.js 18+ (for backend)

### Installation

1. Clone the repository:
   ```bash
   git clone <repo-url>
   cd sapp
   ```

2. **iOS App** - Open in Xcode:
   ```bash
   cd Sapp-ios
   open Sapp.xcodeproj
   ```

3. **Backend** - Install dependencies and run:
   ```bash
   cd sapp/backend-sapp
   npm install
   cp .env.example .env
   # Configure environment variables
   npm run dev
   ```

4. Build and run on simulator or device

## Project Structure

```
Sapp-ios/
├── Core/
│   ├── Auth/                # Authentication protocols & models
│   ├── Components/          # Reusable UI components
│   ├── Config/              # App configuration
│   ├── Crypto/              # Privacy integrations
│   │   ├── ShadowWire*.swift    # Radr Labs private transfers
│   │   ├── SilentSwap*.swift    # Cross-chain privacy
│   │   └── SwapAndPay*.swift    # Swap routing
│   ├── Database/            # Local persistence (SwiftData)
│   ├── Messaging/           # P2P chat infrastructure
│   │   ├── Hypercore/           # Distributed messaging
│   │   └── MessagingService.swift
│   ├── Networking/          # WebSocket & API clients
│   ├── Services/            # Core app services
│   ├── Solana/              # Wallet & blockchain
│   ├── StarPay/             # Card & payment services
│   ├── State/               # ViewModels & state management
│   ├── Storage/             # Secure storage (Keychain)
│   └── Theme/               # Design system
├── Features/
│   ├── Messaging/           # Chat UI
│   │   ├── ChatView.swift
│   │   ├── ConversationsView.swift
│   │   ├── SendCryptoInChatView.swift
│   │   └── SplitBillView.swift
│   ├── Onboarding/          # Auth & setup flow
│   ├── Payment/             # QR scanning
│   ├── Settings/            # App settings & backup
│   └── Wallet/              # Wallet UI
│       ├── WalletView.swift
│       ├── SendCryptoView.swift
│       ├── SwapView.swift
│       ├── EarnView.swift
│       ├── StarpayCardsView.swift
│       └── CardOrderView.swift
├── Navigation/              # App navigation
└── sapp.swift               # App entry point

sapp/backend-sapp/
├── src/
│   ├── config/              # Database & environment
│   ├── constants/           # API, chains, tokens
│   ├── middleware/          # Auth, validation, rate limiting
│   ├── models/              # User, Conversation, Message
│   ├── routes/              # API endpoints
│   │   ├── cryptoRoutes.ts      # Token operations
│   │   ├── silentSwapRoutes.ts  # Cross-chain privacy
│   │   ├── starpayRoutes.ts     # Card & payments
│   │   └── walletRoutes.ts      # Wallet operations
│   ├── services/            # Business logic
│   │   ├── shadowWireService.ts # Private transfers
│   │   ├── silentSwapService.ts # Cross-chain swaps
│   │   ├── starpayService.ts    # Card management
│   │   └── luloService.ts       # Yield aggregation
│   └── types/               # TypeScript definitions
└── server.ts                # Entry point
```

## Roadmap

### Phase 1: Messaging Enhancements
- Strengthen P2P messaging reliability and offline support
- Group chat improvements and media sharing
- Message search and conversation management

### Phase 2: Frictionless Payments
- **AutoSwap**: Automatically swap tokens when users lack the required asset for a transaction
- Streamlined payment flows with fewer confirmation steps

### Phase 3: Unified Financial View
- **Card Transaction History**: Full transaction view for Starpay Mastercard
- Holistic view combining crypto holdings and real-world spending
- Spending analytics and categorization

### Phase 4: Wealth Management
- Comprehensive wealth dashboard across all assets
- Portfolio tracking with performance insights
- Integrated savings goals and budgeting tools

### Vision: Superapp
Sapp aims to be the all-in-one private financial superapp—messaging, payments, savings, and spending unified in a single privacy-preserving experience.

## License

MIT
