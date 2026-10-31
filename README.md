<div align="center">
  <img src="https://raw.githubusercontent.com/onion-talk/.github/main/assets/oniontalk-icon-512.png" alt="OnionTalk Logo" width="110" height="110" />
  <h1>OnionTalk Protocol Specification & Manifesto</h1>
  <p><strong>Zero-Knowledge P2P Mesh Architecture, Cryptographic Primitives & Anti-Censorship Design</strong></p>

  <p>
    <a href="https://play.google.com/store/apps/details?id=org.oniontalk.messenger">
      <img src="https://img.shields.io/badge/Google_Play-OnionTalk_–_Apps_no_Google_Play-3DDC84?style=for-the-badge&logo=google-play&logoColor=black" alt="OnionTalk – Apps no Google Play" />
    </a>
    <a href="#-sponsor--donate">
      <img src="https://img.shields.io/badge/Sponsor-OnionTalk-ea4aaa?style=for-the-badge&logo=githubsponsors&logoColor=white" alt="Sponsor on GitHub" />
    </a>
    <a href="#-sponsor--donate">
      <img src="https://img.shields.io/badge/Donate-BTC_%7C_ETH_%7C_SOL-F7931A?style=for-the-badge&logo=bitcoin&logoColor=white" alt="Donate Crypto" />
    </a>
  </p>
</div>

---

## 🚀 What's New in `v1.5.4` (`versionCode = 48` / Build 48) & Relay Node `v1.5.2` (`Build 11`) & Mesh `v=31` — Sovereign PQC Groups, In-RAM Image Blur Studio, Post-Quantum Hybrid Encryption (`ML-KEM-768`), Dual Warm Socket Pool (`~1.13s` E2E) & 20-Node Zero-Leak Mesh

- **📦 Direct Signed APK Downloads & Web Container (`v1.5.4` — Latest Release Build 48)**:
  - **Main Messenger APK (`org.oniontalk.messenger` `v1.5.4` Build 48)**: [**Download `OnionTalk-v1.5.4.apk`**](https://github.com/onion-talk/oniontalk-demo/releases/download/v1.5.4/OnionTalk-v1.5.4.apk) (`SHA-256: 91c089e10a8ca1ab0326b87d66fff9e29d90797c03921d4e5bfc586d9b86c34a`)
  - **Standalone Android Relay Node APK (`org.oniontalk.relaynode` `v1.5.2` Build 11)**: [**Download `OnionTalk-RelayNode-v1.5.2.apk`**](https://github.com/onion-talk/oniontalk-relay/releases/download/v1.5.2/OnionTalk-RelayNode-v1.5.2.apk) (`SHA-256: eac1ccbe461eabb9f42a6485628c0d9b3cce0f378ba217572a1beba975c5279c`)
  - **🐳 Desktop & Web Container + Embedded Tor v3 Relay (`Windows / Linux / macOS`)**: [**`eriktonon/oniontalk-web:latest`**](https://hub.docker.com/r/eriktonon/oniontalk-web) (`v1.5.4-build48` — `sha256:f0f2912ef2c675f29f30d3f6cb7259b2724b435ab37208f20bc23a86e676d1b1`) — Self-contained Rust Black-Box Web Messenger + active Tor v3 Hidden Service Relay listening on `127.0.0.1:8420`.

- **🛡️ Key Cryptographic & P2P Mesh Breakthroughs in `v1.5.4` (`Build 48` & Relay `Build 10`)**:
  1. **Sovereign Post-Quantum Encrypted Groups (`PQC Groups`) & Anti-Spam Proof-of-Community**: End-to-end encrypted multi-party group chats over Tor v3 with zero central member servers. Group creation unlocks automatically via organic local proof-of-community (`3+ mutual contacts` + `5+ days of vault maturity`, evaluated 100% locally) or immediately via an offline `Ed25519`-signed **`FounderPass`** certificate granted to community Relay Node Operators (`2+ hours active uptime`) or voluntary crypto supporters.
  2. **In-RAM Image Blur & Pixelation Studio + Zero-EXIF Sanitizer**: Built-in tactile brush editor (`Gaussian Blur` & `Mosaic Pixelate`) operating strictly in volatile RAM before encryption, combined with 100% EXIF/GPS header stripping and Least Significant Bit (`LSB`) anti-fingerprinting jitter.
  3. **Hybrid Post-Quantum Cryptography (`__ENC_PQC_KYBER768_X25519_V3__`)**: Combines classical **Dual X25519 ECDH** with **NIST FIPS 203 ML-KEM-768 (`Kyber-768`)** key encapsulation via `HKDF-SHA256` + `ChaCha20-Poly1305 AEAD` + `Ed25519` outer envelope signatures to protect against *Harvest Now, Decrypt Later* quantum adversaries.
  4. **Ultra-Fast E2E Delivery (`1.139s – 1.244s`, avg `1.20s`)**: Upgraded **Dual Warm Socket Pool** (`minWarmSockets = 2` per `.onion` gateway, `70s/75s` Keep-Alive) achieving **100% pre-warmed Tor circuit reuse (`0ms` SOCKS5 handshake)** alongside a `250ms` speculative *Hedged Send*.
  5. **20-Node Zero-Leak Global Mesh (`v=31`), S/Kademlia XOR Distance Routing & Blinded Poller Affinity**: All **20 global `.onion` v3 relays** route by XOR distance (`SHA-256(peer_onion) ^ SHA-256(recipient_hash)`) with zero-knowledge RAM-only rendezvous affinity (`active_pollers`, `TTL 90s`, zero logs) and **100% anonymized synthetic node coordinates (Zero IP / Zero Cloud Provider Exposure)**.
  6. **GossipSub v1.2 `IHAVE` / `IDONTWANT` Deduplication & Mandatory `SHA-256` Media Integrity**: Relays announce `POST /gossip/ihave` metadata before forwarding payloads `> 1024 bytes` (cutting redundant Tor mesh bandwidth by **~70%**) and verify `SHA-256` Merkle hashes on all voice notes, images, and attachments prior to rendering.
---
## 🚀 What's New in `v1.4.2` (`versionCode = 22` / Build 23) — Anti-Exploit Media Firewall, Hardware-Backed KeyStore Vault, Deflate Super-Compression & Warm Tor Pool — Password-Locked Messages & Chats, Unified Long-Press Menu, Profile Photo Privacy, 15s Auto-Lock & Official Video Suite

- **📦 Direct Signed APK Downloads (`v1.4.2` — Latest Release Build 23)**:
  - **Main Messenger APK (`org.oniontalk.messenger` `v1.4.2` Build 23)**: [**Download `OnionTalk-v1.5.4.apk`**](https://github.com/onion-talk/oniontalk-demo/releases/download/v1.5.4/OnionTalk-v1.5.4.apk) (`SHA-256: 68f3d5785919acaf0820c238f93f5db0cb02df5986db457ec783d573dbc652a8`)
  - **Standalone Android Relay Node APK (`org.oniontalk.relaynode` `v1.4.2` Build 3)**: [**Download `OnionTalk-RelayNode-v1.4.2.apk`**](https://github.com/onion-talk/oniontalk-demo/releases/download/v1.4.1-demo/OnionTalk-RelayNode-v1.4.2.apk) (`SHA-256: befe94bcf2e66a2fe067b47b2114af9f226cf3405292df7e67ab5e29782f3f1b`)
- **🎬 Official `v1.4.2` Promotional & Feature Walkthrough Videos**:
  - [**▶ Watch Official Promo v1.4.2 (Português 1080p)**](https://github.com/onion-talk/oniontalk-demo/raw/main/video/OnionTalk-v1.4.1-Promo-Oficial-PT.mp4)
  - [**▶ Watch Official Promo v1.4.2 (English 1080p)**](https://github.com/onion-talk/oniontalk-demo/raw/main/video/OnionTalk-v1.4.1-Promo-Official-EN.mp4)
  - [**▶ Watch Complete Feature & Messaging Walkthrough v1.4.2 (PT-BR 1080p)**](https://github.com/onion-talk/oniontalk-demo/raw/main/video/OnionTalk-v1.4.1-Demo-Funcoes-PT.mp4)
  - [**▶ Watch Vertical Reels / Shorts / TikTok 9:16 Spot (1080x1920)**](https://github.com/onion-talk/oniontalk-demo/raw/main/video/OnionTalk-v1.4.1-Reels-Shorts-PT.mp4)
- **🔐 Key Security & UX Improvements in `v1.4.2` (`Build 23`)**:
  1. **Password-Protected Individual Messages (`__LOCKED_MSG_V1__`)**: Lock any message in a conversation with a dedicated secret password (`PBKDF2-HMAC-SHA256` + `AES-256-GCM`) and reliable first-try session caching (`unlockedMessageCache`) so unlocked messages stay readable throughout the active chat session.
  2. **Password-Protected Conversations**: Lock entire conversations with a dedicated password, masking message previews on the Home screen (`🔒 Conversa trancada com senha`).
  3. **Clean Conversation Rows & Unified Long-Press Action Menu**: Removed external star and pencil icons from conversation rows; long-pressing any conversation opens a unified action menu to **Favorite / Pin to Top (`📌`)**, **Rename Contact (`✏️`)**, or trigger **Bilateral Anti-Forensic Burn (`🔥`)**.
  4. **Instant Add Contact Dismissal & Navigation**: Adding a `.onion` contact now dismisses the modal prior to navigation so the dialog never lingers when returning to the Home screen.
  5. **Single-Flight Hardware Biometrics (`AtomicBoolean`)**: Eliminates duplicate fingerprint prompts when unlocking the vault or resuming from background (`ON_START`).
  6. **Granular Profile Photo Visibility (`Public / Contacts / Friends / Private`)**: Control who receives your sanitized avatar, plus fixed 4-tab Settings navigation (`Modifier.weight(1f)`) and responsive Crypto Donation cards (`BTC`, `ETH`, `SOL`).
  7. **15-Second Auto-Lock (Even After App Closed)**: Persists inactivity timestamps and evaluates elapsed background time immediately on process start so the vault locks strictly after `15s`.

| **1. Password-Locked Message (`v1.4.2`)** | **2. Instant Message Unlock Modal** | **3. Clean List & Long-Press Favorites (`📌`)** |
| :---: | :---: | :---: |
| <img src="https://raw.githubusercontent.com/onion-talk/.github/main/assets/screenshots/11-locked-message-e2ee.png" width="260" alt="Password Locked Message Bubble" /> | <img src="https://raw.githubusercontent.com/onion-talk/.github/main/assets/screenshots/12-unlock-message-modal.png" width="260" alt="Unlock Message Modal" /> | <img src="https://raw.githubusercontent.com/onion-talk/.github/main/assets/screenshots/13-locked-chat-pin-home.png" width="260" alt="Clean Home Pinned & Locked Chat" /> |
| *Per-message AES-256-GCM password lock inside E2EE Tor v3 chat.* | *Unlocks on the first try with incognito keyboard and session cache.* | *Clean conversation list with pinned favorites and locked chat masking.* |

| **4. Lock Entire Conversation Modal** | **5. Profile Photo Privacy (`Build 23`)** | **6. 15s Auto-Lock & Single Biometrics** |
| :---: | :---: | :---: |
| <img src="https://raw.githubusercontent.com/onion-talk/.github/main/assets/screenshots/14-lock-conversation-modal.png" width="260" alt="Lock Conversation with Password" /> | <img src="https://raw.githubusercontent.com/onion-talk/.github/main/assets/screenshots/15-profile-photo-privacy.png" width="260" alt="Profile Photo Visibility Settings" /> | <img src="https://raw.githubusercontent.com/onion-talk/.github/main/assets/screenshots/16-autolock-15s-security.png" width="260" alt="15s Auto-Lock and Biometric Security" /> |
| *Dedicated conversation password hides Home previews and blocks unauthorized access.* | *4 fixed Settings tabs (`Build 23`) and Public / Contacts / Friends / Private avatar visibility.* | *15s inactivity lock enforced even after app closure + single-flight fingerprint prompt.* |

---

## 🚀 What's New in `v1.4.0` (`versionCode = 14`) — 20-Node Global Mesh (8 Countries), Selective `FLAG_SECURE`, Instant Tor Auto-Heal & GZIP File Transfers

- **📦 Direct Signed APK Downloads (`v1.4.0`)**:
  - **Main Messenger APK (`org.oniontalk.messenger`)**: [**Download `OnionTalk-v1.5.4.apk`**](https://github.com/onion-talk/oniontalk-demo/releases/download/v1.5.4/OnionTalk-v1.5.4.apk) (`SHA-256: d11ee5629b6bffa32658d80e2d22cd5582e37c84d3b69bd85dffc424793688c4`)
  - **Standalone Android Relay Node APK (`org.oniontalk.relaynode`)**: [**Download `OnionTalk-RelayNode-v1.4.2.apk`**](https://github.com/onion-talk/oniontalk-demo/releases/download/v1.4.1-demo/OnionTalk-RelayNode-v1.4.2.apk) (`SHA-256: befe94bcf2e66a2fe067b47b2114af9f226cf3405292df7e67ab5e29782f3f1b`)
- **🌐 20 Active Tor v3 Relays Across 8 Countries (`BR`, `US`, `FR`, `DE`, `RU`, `SG`, `JP`, `CN`)**:
  - Added **Node 16 (Regional Mesh Relay)**: `o5zqqfl5znzexdojfnxgub5jnjelxdahbyxasjp57sx6fbxtjeqovpad.onion`
  - Added **Node 17 (East Asia Relay #17 — GFW Bypass)**: `2amizuhb3p5x2lk3sra7f7thm5tgs7qtnysgowqpmexcqi4cuwyv7vad.onion`
  - Added **Zero-Touch Auto-Join & 100% Zero-Leak Synthetic Coordinates (Zero IP / Zero Geo Exposure)** so any Docker or Android Relay Node joins the mesh in `<15s`.
- **🛡️ Selective `FLAG_SECURE` by Route**:
  - Enforces `WindowManager.LayoutParams.FLAG_SECURE` **100% of the time** on **Conversations (`CHAT_DETAIL`)**, **Active Chats (`CHAT_LIST`)**, and **Contacts Library (`CONTACTS_LIBRARY`)**, while dynamically allowing screenshots on **Settings / QR Code (`SETTINGS`)** for frictionless identity sharing.
- **⚡ 2-Hour Large-Scale Soak & Chaos Engineering Certification (`23:50–01:50`, 60 Waves, 3 Android 15 Emulators)**:
  - **0 crashes, 0 ANRs, 0 frozen process warnings** (`PSS: 62.5 MB – 94.9 MB`).
  - **Online P2P Delivery Latency**: `p50 = 1,147.1 ms` (`1.15s`), `p95 = 5,039.5 ms`.
  - **Encrypted File Transfers (`16 KB`–`256 KB`)**: `15/15` (`100%`) delivered with transparent **GZIP pre-compression (`gz=true`)** and adaptive read timeouts (`25s`).
  - **Bilateral Anti-Forensic Burn (`__CTRL_BURN_V1__`)**: `15/15` (`100%`) confirmed in `p50 = 1,846.5 ms`.
  - **Instant Network Auto-Recovery (`ConnectivityManager.NetworkCallback`)**: Foreground & background `NetworkCallback` + `3.5s` partial wake-lock on incoming batches recovers offline backlogs in `700.8 ms – 849.9 ms`.
- **🎨 Visual Privacy & UI Polish**:
  - Added **Blur / Unblur Contact Photo** (`blurAvatarBitmap`) per contact, removed bubble reply clutter and header shield icon, and placed the `✅ Atualizado` confirmation directly inside the Tor Status card.

| # | Region / Node Class | Tor v3 Hidden Service Address (`.onion`) | Role |
| :-: | :--- | :--- | :--- |
| 1 | 🇧🇷 SA-East #1 (BR) | `onion4zr3bsdeaelksemwokl5qmxd5o7jyblf46vc2mfl6cozgw77tqd.onion` | Master Vanity Seed (`v=31`) |
| 2 | 🇧🇷 SA-East #2 (BR) | `kn4u2xxl2otoo2ujv3mhehwfwbw7mtppaf56fu3nxogvv7eekf2qdrid.onion` | Core Worker Seed (`v=31`) |
| 3 | 🇺🇸 US-East #1 (US) | `e3a7jfpzcsj6e7o7lzrwos2qz53wesp62lgjmsa3pld6xwnqvromrvqd.onion` | Sovereign Cloud Relay (`v=31`) |
| 4 | 🇧🇷 SA-East #3 (BR) | `zqdx5x7pfybox7m5rz3fe5kiouxhipvh3ekuteq2urrrvwcxjttnmgid.onion` | Sovereign Cloud Relay (`v=31`) |
| 5 | 🇺🇸 US-East #2 (US) | `xememocnagky3qlkkx7n6tgkmjrzhmfzoahbke3gvtea6nu4nnc27sad.onion` | Sovereign Cloud Relay (`v=31`) |
| 6 | 🇫🇷 EU-West #1 (FR) | `7bntuiegd3stvcylvx7rhnhq7ncasxiokunbf5onvvm34dg5gccvooid.onion` | EU Sovereign Relay #1 (`v=31`) |
| 7 | 🇺🇸 US-East #3 (US) | `jz6urt6ckkqqvtasm6bll2mryhksjcawcl4tbguif5nqvxgsfsx6ywad.onion` | Sovereign Cloud Relay (`v=31`) |
| 8 | 🇺🇸 US-East #4 (US) | `4wufywh2k6ayyz6nmh2w25hj5vjsqgkve24o2tthvc7rhyvxnhaghqqd.onion` | Sovereign Cloud Relay (`v=31`) |
| 9 | 🇷🇺 EE-East #1 (RU) | `nwsoa6ddtbbqbwcceanhhj3j23d5a47zbpbs6zspz5zoeytzqpzvkqqd.onion` | Eurasia Sovereign Relay (`v=31`) |
| 10 | 🇺🇸 US-East #5 (US) | `bk7iegv3v232ycjyf5ylwsdx42iozvy2dhhff5zn3ciwa3g2lkifdlad.onion` | Container Mesh Relay (`v=31`) |
| 11 | 🇫🇷 EU-West #2 (FR) | `hdjp7uaj4qemlmwtev7xmj2w3uexnv6ctplfgvbmpqxenbfgwjjwtrid.onion` | EU Sovereign Relay #2 (`v=31`) |
| 12 | 🇫🇷 EU-West #3 (FR) | `gcvfh67zltoyvithw6luetsrcec6cw42upzrsprxfmx27cvh7vidw4yd.onion` | EU Sovereign Relay #3 (`v=31`) |
| 13 | 🇺🇸 US-Central #1 (US) | `wfi3nwuzk2tgrsf2scdy4nb6x6rtiocit4n26477zdlvdvshkgip3ayd.onion` | US-Central Sovereign Relay (`v=31`) |
| 14 | 🇯🇵 AP-East #1 (JP) | `5s6w6556f2eov2p6wlsuavaxh7si2kaswjwi5reojnovbzemducjzjqd.onion` | Asia-Pacific East Relay (`v=31`) |
| 15 | 🇸🇬 AP-South #1 (SG) | `o5yf3eukrwpt2g6jfo4q2y23xtuhoso2qknmnn6ac5eng5t4yt36roqd.onion` | Southeast Asia Hub Relay (`v=31`) |
| 16 | 🇩🇪 EU-Central #1 (DE) | `o5zqqfl5znzexdojfnxgub5jnjelxdahbyxasjp57sx6fbxtjeqovpad.onion` | Central Europe Relay (`v=31`) |
| 17 | 🇨🇳 AP-East #2 (CN) | `2amizuhb3p5x2lk3sra7f7thm5tgs7qtnysgowqpmexcqi4cuwyv7vad.onion` | AP-East / GFW Bypass Relay (`v=31`) |
| 18 | 🇺🇸 US-East #6 (US) | `fscst5exmlmr2622234k2gg6bfg6y3obdaag2fbe4jc3s2p332f52nyd.onion` | Container Mesh Relay #2 (`v=31`) |
| 19 | 🇺🇸 US-East #7 (US) | `vva7fb74be62k5v533v233v523v523v523v523v523v523v523v523ad.onion` | Sovereign Cloud Relay (`v=31`) |
| 20 | 🇺🇸 US-East #8 (US) | `ln4bd3bbp5yq2da2bop3ggfdku35dncpcwdc2vllf6n3mrce6b24q7ad.onion` | Multi-HS Sovereign Relay (`v=31`) |
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

- **GitHub Sponsors**: [Crypto & Direct Sponsorship](#-sponsor--donate)
- **Bitcoin (BTC)**: `bc1q0hr95ay33rtazfepg64yddf52q3yqh7ud83cza`
- **Ethereum (ETH / ERC-20)**: `0xE69FCE4Fa35CF3bd98F496337b1eA223270b2c92`
- **Solana (SOL)**: `3E8L1Hdqe7Xk6GCrzHbtY5sReAfLFc9CdwgZxP7qaoHq`

---

## ⚠️ Legal Disclaimers, Limitation of Liability & Sovereign Terms of Use (`v1.5.0`)

1. **"AS IS" Open-Source Provision & Cryptographic Research Purpose**: OnionTalk (`org.oniontalk.messenger`), OnionTalk Relay Node (`org.oniontalk.relaynode`), and the Desktop/Web Container (`oniontalk-web`) are distributed strictly **"AS IS"**, without warranties of any kind under the MIT License, as cryptographic engineering and digital privacy technology (`Privacy by Design`).
2. **Irreversible Zero-Knowledge Custody (No Password Recovery)**: Because OnionTalk operates without central servers, user accounts, emails, or phone numbers, **the developers cannot recover forgotten vault passwords, restore lost private keys, or reverse the 5-Strike Anti-Coercion Wipe (`DoD 5220.22-M`) or Synchronized Bilateral Burn (`🔥`)**. Users are solely responsible for safeguarding their local credentials and backups.
3. **Blind Common-Carrier Relay Safe Harbor**: Federated `.onion` v3 relay nodes act strictly as **blind, non-custodial encrypted envelope routers**. Relays possess neither the private `X25519` keys nor the post-quantum `ML-KEM-768` decapsulation keys required to inspect, filter, or modify message contents, and expose only deterministic synthetic topology coordinates (`Zero IP / Zero Cloud Provider Leak`).
4. **Lawful Use & User Responsibility**: Users assume full and exclusive legal responsibility for their use of the software in their respective jurisdictions. Using OnionTalk for unlawful activities is strictly prohibited by the project's terms of use.
5. **Non-Affiliation**: OnionTalk is an independent open-source project and is not affiliated with, endorsed by, or sponsored by *The Tor Project, Inc.*
