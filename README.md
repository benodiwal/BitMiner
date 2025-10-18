# BitMiner

**A lightweight Bitcoin block mining simulator and transaction validation engine built from scratch**

BitMiner is an educational implementation of Bitcoin's core mining and transaction validation mechanisms. Built without relying on Bitcoin-specific libraries, this project demonstrates the fundamental cryptographic and algorithmic principles that power Bitcoin's proof-of-work consensus.

## Features

- **Transaction Validation**: Validates Bitcoin transactions from scratch using cryptographic primitives
- **Block Mining Simulation**: Implements proof-of-work mining algorithm with configurable difficulty targets
- **Mempool Processing**: Efficiently processes and prioritizes transactions based on fee rates
- **Block Construction**: Constructs valid Bitcoin blocks including coinbase transactions
- **Zero External Bitcoin Libraries**: Built using only standard cryptographic libraries (secp256k1, SHA-256)

## Quick Start

### Prerequisites

- Rust 1.70+ (or your language runtime)
- Standard cryptographic libraries

### Installation

```bash
git clone https://github.com/benodiwal/BitMiner.git
cd BitMiner
```

### Usage

1. Place transaction JSON files in the `mempool/` directory
2. Run the mining simulation:

```bash
bash run.sh
```

3. The mined block will be output to `output.txt` with the following structure:
   - Line 1: Block header
   - Line 2: Serialized coinbase transaction
   - Line 3+: Transaction IDs included in the block

## How It Works

### Block Construction Pipeline

1. **Transaction Parsing**: Reads and parses transactions from the mempool
2. **Validation**: Validates each transaction using cryptographic signatures and script verification
3. **Fee Optimization**: Selects transactions to maximize fee collection while respecting block size limits
4. **Coinbase Creation**: Generates coinbase transaction with block reward and collected fees
5. **Mining**: Iterates through nonce values to find a block hash below the difficulty target

### Difficulty Target

The default difficulty target is:
```
0000ffff00000000000000000000000000000000000000000000000000000000
```

This can be configured to simulate different mining difficulties.

## Configuration

Customize mining parameters by modifying the configuration:

- Difficulty target
- Block size limits
- Fee calculation methods
- Validation rules

**Note**: This is an educational implementation for learning purposes. It is not intended for production use or actual Bitcoin mining.

## Contact

For questions or feedback, please open an issue on GitHub.
