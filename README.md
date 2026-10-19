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

This repository contains the formal protocol specification and the manifesto ([`MANIFESTO.md`](./MANIFESTO.md)) detailing how OnionTalk achieves metadata-free, end-to-end encrypted communication over Tor v3 Hidden Services.

---

## 🔐 The 4-Layer Protocol Stack (`v2`)

### 1. Transport & Anonymity Layer (`Tor v3 SOCKS5h`)
- Every client and relay operates over **Tor v3 Hidden Services** (`56-character Ed25519 .onion` addresses).
- All outbound traffic is routed through `SOCKS5h` (`127.0.0.1:9050`), resolving `.onion` descriptors inside the Tor circuit with zero clearnet DNS leakage.
- Relays bind their local HTTP port strictly to `127.0.0.1` and expose virtual port `80` only inside the 6-hop Tor rendezvous circuit, hiding IP addresses from both peers and relays.

### 2. Authenticated Service Discovery (`Bootstrap Seeds + Ed25519 Gossip PEX`)
- **Layer 1 (Bootstrap Seeds)**: New nodes contact a resilient set of multi-cloud `.onion` seed addresses on first boot.
- **Layer 2 (Ed25519-Authenticated Peer Exchange / PEX)**: Relays sign all peer-to-peer requests (`/api/v1/peers/announce`, `/api/v1/messages/sync`, `/api/v1/messages/ack_sync`, `/api/v1/messages/ack_batch_sync`) with their node `Ed25519` private key (`X-Peer-Signature`). Before admitting any candidate node into `known_peers`, relays perform a reverse Tor handshake (`GET http://<candidate>.onion/health`) and verify that the remote node's `node_pubkey` matches the announcement signature.
- **Layer 3 (Client Dynamic Mesh Sync)**: Clients fetch `/api/v1/peers/list` from any reachable relay and persist discovered `.onion` nodes locally inside their encrypted vault.

### 3. Epidemic RAM-Only Gossip & Cryptographic ACK Preimage Lock
- **RAM-Only Volatile Queue (`ram-volatile-ephemeral-ttl24h`)**: Relays never write messages to disk or SQLite. Envelopes reside strictly in volatile RAM with a 24-hour TTL and strict non-evicting per-user quotas.
- **Ed25519 Inbox & ACK Challenge Authentication**: Clients must sign `ONIONTALK_AUTH_V2|<SCOPE>|<user_id>|<timestamp_ms>` with their 256-bit `Ed25519` identity key (`X-OnionTalk-Signature`) to poll `/api/v1/messages/inbox` or submit `/api/v1/messages/ack`.
- **Cryptographic ACK Preimage Lock**:
  - For every message, the sender generates a fresh 256-bit random `ack_token` via `SecureRandom` (sealed inside the `ChaCha20-Poly1305` ciphertext) and publishes only `ack_lock = SHA-256(ack_token)` in the outer envelope.
  - Only the recipient possessing the private key can decrypt the envelope, extract `ack_token`, and submit `POST /api/v1/messages/ack`.
  - Relays verify `SHA-256(ack_token) == ack_lock` in constant time (`hmac.compare_digest`) before purging the message from RAM across the mesh.

### 4. End-to-End Authenticated Encryption (`__ENC_X25519_CHACHA20_V2__`)
- **256-Bit Public-Key Identity**: Each user's Crypto ID (`@<64-hex-ed25519-pubkey>:<domain>.onion`) embeds their full 32-byte **Ed25519** public key, birationally mapped to **X25519** ($u = (1+y)/(1-y) \bmod 2^{255}-19$) per RFC 7748 / RFC 8032.
- **Dual X25519 ECDH + HKDF-SHA256**: Every message generates a fresh ephemeral **X25519** keypair and combines `ECDH(ephemeral_priv, recipient_x25519_pub) || ECDH(sender_x25519_priv, recipient_x25519_pub)` through **HKDF-SHA256** (`info = "ONIONTALK_WIRE_V2_CHACHA20_POLY1305|<msgId>|<sender>|<recipient>"`).
- **ChaCha20-Poly1305 AEAD + Ed25519 Sender Signature**: The payload (`ackToken | plaintext`) is sealed with **ChaCha20-Poly1305** (96-bit random nonce + 128-bit Poly1305 tag with AAD binding) and signed with the sender's **Ed25519** private key to guarantee both forward secrecy and sender authenticity.
- **Local Vault at Rest**: On-device messages and identity seeds are stored inside **SQLCipher 4.5.4 (AES-256-CBC)** keyed via **Argon2id** (`64 MB RAM, 4 iterations, 4 lanes`).

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
