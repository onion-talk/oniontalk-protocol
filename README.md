<div align="center">
  <img src="https://raw.githubusercontent.com/onion-talk/.github/main/assets/oniontalk-icon-512.png" alt="OnionTalk Logo" width="110" height="110" />
  <h1>OnionTalk Protocol Specification & Manifesto</h1>
  <p><strong>Zero-Knowledge P2P Mesh Architecture, Cryptographic Primitives & Anti-Censorship Design</strong></p>

  <p>
    <a href="https://github.com/sponsors/eriktonon">
      <img src="https://img.shields.io/badge/Sponsor-OnionTalk-ea4aaa?style=for-the-badge&logo=githubsponsors&logoColor=white" alt="Sponsor on GitHub" />
    </a>
    <a href="#-sponsor--donate">
      <img src="https://img.shields.io/badge/Donate-BTC_%7C_ETH_%7C_SOL-F7931A?style=for-the-badge&logo=bitcoin&logoColor=white" alt="Donate Crypto" />
    </a>
  </p>
</div>

---

## 🎯 Our Mission

Centralized messengers protect the body of your message while surrendering your social graph. They require phone numbers, depend on centralized DNS-resolved servers, and create a single choke point for censorship and subpoena.

**OnionTalk is built to make censorship and mass surveillance mathematically impossible.**

This repository contains the formal protocol specification and the bilingual manifesto ([`MANIFESTO.md`](./MANIFESTO.md)) detailing how OnionTalk achieves metadata-free, end-to-end encrypted communication over Tor v3 Hidden Services.

---

## 🔐 The 4-Layer Protocol Stack

### 1. Transport & Anonymity Layer (`Tor v3 SOCKS5h`)
- Every client and relay operates over **Tor v3 Hidden Services** (`56-character Ed25519 .onion` addresses).
- All outbound traffic is routed through `SOCKS5h` (`127.0.0.1:9050`), resolving `.onion` descriptors inside the Tor circuit with zero clearnet DNS leakage.
- Connections use a 6-hop Tor rendezvous circuit (3 sender hops + 3 hidden service hops), hiding IP addresses from both peers and relays.

### 2. Service Discovery (`Bootstrap Seeds + Auto-Gossip PEX`)
- **Layer 1 (Bootstrap Seeds)**: New nodes contact a resilient set of multi-cloud `.onion` seed addresses on first boot.
- **Layer 2 (Autonomous Peer Exchange / PEX)**: Every 30 seconds, relays exchange their active peer tables via `POST /api/v1/peers/announce` and `GET /api/v1/peers/list`, verifying liveness over Tor (`GET /health`) before admitting a node into the routing table.
- **Layer 3 (Client Dynamic Mesh Sync)**: Clients fetch `/api/v1/peers/list` from any reachable relay and persist discovered `.onion` nodes locally. Even if all original bootstrap seeds are taken offline, clients continue operating through learned community relays.

### 3. Epidemic Gossip Distribution & ACK Preimage Lock
- **Client Multi-Relay Fanout (`3x`)**: When sending a message, the client pushes the encrypted envelope in parallel to 3 distinct `.onion` relays (`POST /api/v1/messages/send`).
- **Relay Gossip Replication**: Receiving relays asynchronously replicate the envelope (`X-Gossip-Sync: 1`) across their active peer table, deduplicating by `msg_id` (`UUIDv4`).
- **Cryptographic ACK Preimage Lock**:
  - The sender generates a random 256-bit `ack_token` (sealed inside the E2EE payload) and places only `ack_hash = SHA-256(ack_token)` in the outer envelope header.
  - Only the legitimate recipient can decrypt the payload, extract `ack_token`, and broadcast `POST /api/v1/messages/ack`.
  - Relays verify `SHA-256(ack_token) == ack_hash` before purging the message from SQLite WAL storage, preventing malicious third parties from deleting undelivered messages.

### 4. Double-Layer Authenticated Encryption (`E2EE + Wire Key`)
- **Inner E2EE Layer (`OfflineCryptoManager`)**: Ephemeral **X25519 ECDH** key agreement + **HKDF-SHA256** (`info = "TonyLoco-Offline-E2EE-v1"`) + **ChaCha20-Poly1305** (96-bit random nonce + 128-bit Poly1305 MAC).
- **Outer Wire Layer (`EncryptionHelper`)**: **AES-256-GCM** envelope encryption prior to JSON serialization.

---

## 📄 Full Protocol & Architecture Manifesto

Read the complete specification and diagrams in [**`MANIFESTO.md`**](./MANIFESTO.md).

---

## 💖 Sponsor & Donate

Support independent privacy infrastructure:

- **GitHub Sponsors**: [github.com/sponsors/eriktonon](https://github.com/sponsors/eriktonon)
- **Bitcoin (BTC)**: `bc1q0hr95ay33rtazfepg64yddf52q3yqh7ud83cza`
- **Ethereum (ETH / ERC-20)**: `0xE69FCE4Fa35CF3bd98F496337b1eA223270b2c92`
- **Solana (SOL)**: `3E8L1Hdqe7Xk6GCrzHbtY5sReAfLFc9CdwgZxP7qaoHq`
