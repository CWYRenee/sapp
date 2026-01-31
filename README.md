# Sapp - Private P2P Messaging

Sapp is a privacy-first mobile messaging app powered by Solana. Send encrypted messages and transfer crypto directly within conversations using peer-to-peer technology.

## Features

- **End-to-End Encrypted Messaging**: All messages are encrypted by default using P2P technology via BareKit
- **Solana Wallet Integration**: Built-in wallet with Privy authentication for seamless crypto transactions
- **Send Crypto in Chat**: Transfer SOL and tokens directly within conversations
- **Modern Minimal UI**: Clean, type-driven design with serif/sans-serif pairing

## Architecture

| Component | Description |
|-----------|-------------|
| **Core/Messaging** | BareKit P2P integration, chat models, messaging service |
| **Core/Solana** | Solana wallet service, Privy authentication |
| **Core/Theme** | Sapp design system (colors, typography, spacing) |
| **Features/Messaging** | Conversations list, chat view, new chat flow |
| **Features/Wallet** | Wallet view, send/receive SOL |
| **Features/Onboarding** | Multi-step onboarding with Privy auth |

## Tech Stack

- **SwiftUI** - Modern declarative UI framework
- **Solana** - Blockchain for transactions
- **Privy** - Authentication (email, phone, social, embedded wallet)
- **BareKit** - P2P messaging infrastructure via worklets

## Setup

### Requirements

- macOS with Xcode 15+
- iOS 17+ device or simulator

### Installation

1. Clone the repository:
   ```bash
   git clone <repo-url>
   cd sapp/Sapp-ios
   ```

2. Open in Xcode:
   ```bash
   open Sapp.xcodeproj
   ```

3. Configure environment:
   ```bash
   cp .env.example .env
   # Edit .env with your Privy credentials from https://dashboard.privy.io
   # PRIVY_APP_ID=your-app-id
   # PRIVY_APP_CLIENT_ID=your-app-client-id
   ```

4. Build and run on simulator or device

## Project Structure

```
Sapp-ios/
├── Core/
│   ├── Components/       # Reusable UI components
│   ├── Messaging/        # P2P chat infrastructure
│   │   ├── BareKitManager.swift
│   │   ├── ChatModels.swift
│   │   └── MessagingService.swift
│   ├── Services/         # App services
│   ├── Solana/           # Wallet & auth
│   │   ├── PrivyAuthService.swift
│   │   ├── SolanaModels.swift
│   │   └── SolanaWalletService.swift
│   ├── Storage/          # Local persistence
│   └── Theme/            # Design system
│       └── Theme.swift
├── Features/
│   ├── Messaging/        # Chat UI
│   │   ├── ChatView.swift
│   │   ├── ConversationsView.swift
│   │   └── NewChatView.swift
│   ├── Onboarding/       # Auth flow
│   │   └── OnboardingView.swift
│   ├── Settings/         # App settings
│   │   └── SettingsView.swift
│   └── Wallet/           # Wallet UI
│       └── WalletView.swift
├── Navigation/           # App navigation
│   ├── MainTabView.swift
│   └── RootNavigationView.swift
└── sapp.swift            # App entry point
```

## Design System

Sapp uses a minimal, type-driven design with:

- **Colors**: Off-white background (#FAFAF8), black text (#1A1A1A), subtle borders
- **Typography**: Serif fonts for headlines, sans-serif for body
- **Spacing**: Generous whitespace using 8pt grid
- **Buttons**: Solid fills with rounded corners, subtle hover transitions

## Network

Currently configured for **Solana Devnet**.

## License

MIT
