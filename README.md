# KALE Pool Mining System

A complete mining pool infrastructure for KALE token on the Stellar blockchain, providing block discovery and coordination services for distributed mining operations.

## System Overview

The KALE Pool Mining System consists of a specialized Pooler service that coordinates mining activities, discovers blocks, and manages pool operations on the Stellar network.

## Quick Start

### Prerequisites

- Bun runtime (>=1.0.0) or Node.js (>=18.0.0)
- Access to Stellar mainnet RPC

### Environment Configuration

Configure the following critical environment variables in `Pooler/.env.mainnet`:

```bash
# Stellar Network
RPC_URL=https://mainnet.sorobanrpc.com
CONTRACT_ID=CDL74RF5BLYR2YBLCCI7F5FB6TPSCLKEJUBSD2RSVWZ4YHF3VMFAIGWA
NETWORK_PASSPHRASE="Public Global Stellar Network ; September 2015"

# Pooler Service
POOLER_PORT=3001
BACKEND_API_URL=https://575ea5d959e3.ngrok-free.app

# Block Monitoring
BLOCK_CHECK_INTERVAL=5000
MAX_FARMERS=100
```

### Start Command

```bash
bun run start:pooler
```

## Architecture

- **Pooler Service**: Block discovery engine and pool coordination service
- **Stellar Integration**: Direct RPC communication with Stellar mainnet
- **Mining Coordination**: Manages up to 100 concurrent miners per pool instance

## Service Endpoints

- Health Check: `http://localhost:3001/health`
- Pool Status: `http://localhost:3001/status`

## Technical Stack

- Runtime: Bun/Node.js with TypeScript
- Blockchain: Stellar Soroban smart contracts
- Network: Stellar mainnet RPC integration
