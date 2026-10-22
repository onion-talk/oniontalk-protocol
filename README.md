<div align="center">
  <img src="https://raw.githubusercontent.com/onion-talk/.github/main/assets/oniontalk-icon-512.png" alt="OnionTalk Logo" width="110" height="110" />
  <h1>OnionTalk Protocol Specification & Manifesto</h1>
  <p><strong>Zero-Knowledge P2P Mesh Architecture, Cryptographic Primitives & Anti-Censorship Design</strong></p>

  <p>
    <a href="https://play.google.com/store/apps/details?id=org.oniontalk.messenger">
      <img src="https://img.shields.io/badge/Google_Play-OnionTalk_–_Apps_no_Google_Play-3DDC84?style=for-the-badge&logo=google-play&logoColor=black" alt="OnionTalk – Apps no Google Play" />
    </a>
    <a href="https://github.com/sponsors/eriktonon">
      <img src="https://img.shields.io/badge/Sponsor-OnionTalk-ea4aaa?style=for-the-badge&logo=githubsponsors&logoColor=white" alt="Sponsor on GitHub" />
    </a>
    <a href="#-sponsor--donate">
      <img src="https://img.shields.io/badge/Donate-BTC_%7C_ETH_%7C_SOL-F7931A?style=for-the-badge&logo=bitcoin&logoColor=white" alt="Donate Crypto" />
    </a>
  </p>
</div>

---

## 🚀 What's New in `v1.4.2` (`versionCode = 22` / Build 22) — Anti-Exploit Media Firewall, Hardware-Backed KeyStore Vault, Deflate Super-Compression & Warm Tor Pool — Password-Locked Messages & Chats, Unified Long-Press Menu, Profile Photo Privacy, 15s Auto-Lock & Official Video Suite

- **📦 Direct Signed APK Downloads (`v1.4.2` — Latest Release Build 22)**:
  - **Main Messenger APK (`org.oniontalk.messenger` `v1.4.2` Build 22)**: [**Download `OnionTalk-v1.4.2.apk`**](https://github.com/onion-talk/oniontalk-demo/releases/download/v1.4.2-demo/OnionTalk-v1.4.2.apk) (`SHA-256: 68f3d5785919acaf0820c238f93f5db0cb02df5986db457ec783d573dbc652a8`)
  - **Standalone Android Relay Node APK (`org.oniontalk.relaynode` `v1.4.2` Build 3)**: [**Download `OnionTalk-RelayNode-v1.4.2.apk`**](https://github.com/onion-talk/oniontalk-demo/releases/download/v1.4.1-demo/OnionTalk-RelayNode-v1.4.2.apk) (`SHA-256: 08b926aaa7e52c14373a8c1038384835e34f82ef6dc0c6c4782e3a795aa95a96`)
- **🎬 Official `v1.4.2` Promotional & Feature Walkthrough Videos**:
  - [**▶ Watch Official Promo v1.4.2 (Português 1080p)**](https://github.com/onion-talk/oniontalk-demo/raw/main/video/OnionTalk-v1.4.1-Promo-Oficial-PT.mp4)
  - [**▶ Watch Official Promo v1.4.2 (English 1080p)**](https://github.com/onion-talk/oniontalk-demo/raw/main/video/OnionTalk-v1.4.1-Promo-Official-EN.mp4)
  - [**▶ Watch Complete Feature & Messaging Walkthrough v1.4.2 (PT-BR 1080p)**](https://github.com/onion-talk/oniontalk-demo/raw/main/video/OnionTalk-v1.4.1-Demo-Funcoes-PT.mp4)
  - [**▶ Watch Vertical Reels / Shorts / TikTok 9:16 Spot (1080x1920)**](https://github.com/onion-talk/oniontalk-demo/raw/main/video/OnionTalk-v1.4.1-Reels-Shorts-PT.mp4)
- **🔐 Key Security & UX Improvements in `v1.4.2` (`Build 22`)**:
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

| **4. Lock Entire Conversation Modal** | **5. Profile Photo Privacy (`Build 22`)** | **6. 15s Auto-Lock & Single Biometrics** |
| :---: | :---: | :---: |
| <img src="https://raw.githubusercontent.com/onion-talk/.github/main/assets/screenshots/14-lock-conversation-modal.png" width="260" alt="Lock Conversation with Password" /> | <img src="https://raw.githubusercontent.com/onion-talk/.github/main/assets/screenshots/15-profile-photo-privacy.png" width="260" alt="Profile Photo Visibility Settings" /> | <img src="https://raw.githubusercontent.com/onion-talk/.github/main/assets/screenshots/16-autolock-15s-security.png" width="260" alt="15s Auto-Lock and Biometric Security" /> |
| *Dedicated conversation password hides Home previews and blocks unauthorized access.* | *4 fixed Settings tabs (`Build 22`) and Public / Contacts / Friends / Private avatar visibility.* | *15s inactivity lock enforced even after app closure + single-flight fingerprint prompt.* |

---

## 🚀 What's New in `v1.4.0` (`versionCode = 14`) — 17-Node Global Mesh (8 Countries), Selective `FLAG_SECURE`, Instant Tor Auto-Heal & GZIP File Transfers

- **📦 Direct Signed APK Downloads (`v1.4.0`)**:
  - **Main Messenger APK (`org.oniontalk.messenger`)**: [**Download `OnionTalk-v1.4.0.apk`**](https://github.com/onion-talk/oniontalk-demo/releases/download/v1.4.2-demo/OnionTalk-v1.4.2.apk) (`SHA-256: d11ee5629b6bffa32658d80e2d22cd5582e37c84d3b69bd85dffc424793688c4`)
  - **Standalone Android Relay Node APK (`org.oniontalk.relaynode`)**: [**Download `OnionTalk-RelayNode-v1.4.2.apk`**](https://github.com/onion-talk/oniontalk-demo/releases/download/v1.4.1-demo/OnionTalk-RelayNode-v1.4.2.apk) (`SHA-256: 08b926aaa7e52c14373a8c1038384835e34f82ef6dc0c6c4782e3a795aa95a96`)
- **🌐 17 Active Tor v3 Relays Across 8 Countries (`BR`, `US`, `FR`, `DE`, `RU`, `SG`, `JP`, `CN`)**:
  - Added **Node 16 (DOM Cloud Nuremberg, Germany)**: `o5zqqfl5znzexdojfnxgub5jnjelxdahbyxasjp57sx6fbxtjeqovpad.onion`
  - Added **Node 17 (ModelScope Cloud Hangzhou, China — GFW Bypass)**: `2amizuhb3p5x2lk3sra7f7thm5tgs7qtnysgowqpmexcqi4cuwyv7vad.onion`
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

| # | Country / Region | Tor v3 Hidden Service Address (`.onion`) | Role |
| :-: | :--- | :--- | :--- |
| 1 | 🇧🇷 Brazil (São Paulo #1) | `onion4zr3bsdeaelksemwokl5qmxd5o7jyblf46vc2mfl6cozgw77tqd.onion` | Master Vanity Seed (PVE2) |
| 2 | 🇧🇷 Brazil (São Paulo #2) | `kn4u2xxl2otoo2ujv3mhehwfwbw7mtppaf56fu3nxogvv7eekf2qdrid.onion` | Homelab Core Seed (PVE4) |
| 3 | 🇺🇸 USA (US-East) | `puqjsmsyyzmxjdtcgr2fl4wrdazqd2phaqrz26alzwyletbvekkxhyyd.onion` | AWS EKS Relay |
| 4 | 🇧🇷 Brazil (Vinhedo) | `zqdx5x7pfybox7m5rz3fe5kiouxhipvh3ekuteq2urrrvwcxjttnmgid.onion` | Oracle Cloud OCI Relay |
| 5 | 🇺🇸 USA (Virginia) | `ch4s5llfqshxbvba2yulgp5kbopq25w3qqrtli67sle6smbujlebn2id.onion` | AWS Virginia Relay |
| 6 | 🇫🇷 France (Paris #1) | `7bntuiegd3stvcylvx7rhnhq7ncasxiokunbf5onvvm34dg5gccvooid.onion` | Alwaysdata EU Relay #1 |
| 7 | 🇺🇸 USA (South Carolina) | `jz6urt6ckkqqvtasm6bll2mryhksjcawcl4tbguif5nqvxgsfsx6ywad.onion` | Google Cloud US-East Relay |
| 8 | 🇺🇸 USA (Ohio) | `4wufywh2k6ayyz6nmh2w25hj5vjsqgkve24o2tthvc7rhyvxnhaghqqd.onion` | Render Cloud Ohio Relay |
| 9 | 🇷🇺 Russia (Moscow) | `nwsoa6ddtbbqbwcceanhhj3j23d5a47zbpbs6zspz5zoeytzqpzvkqqd.onion` | Amvera Cloud Eurasia Relay |
| 10 | 🇺🇸 USA (US-East) | `bk7iegv3v232ycjyf5ylwsdx42iozvy2dhhff5zn3ciwa3g2lkifdlad.onion` | Back4App Container Relay |
| 11 | 🇫🇷 France (Paris #2) | `hdjp7uaj4qemlmwtev7xmj2w3uexnv6ctplfgvbmpqxenbfgwjjwtrid.onion` | Alwaysdata EU Relay #2 |
| 12 | 🇫🇷 France (Paris #3) | `gcvfh67zltoyvithw6luetsrcec6cw42upzrsprxfmx27cvh7vidw4yd.onion` | Alwaysdata EU Relay #3 |
| 13 | 🇺🇸 USA (Iowa, US-Central) | `wfi3nwuzk2tgrsf2scdy4nb6x6rtiocit4n26477zdlvdvshkgip3ayd.onion` | Northflank US-Central Relay |
| 14 | 🇯🇵 Japan (Osaka) | `5s6w6556f2eov2p6wlsuavaxh7si2kaswjwi5reojnovbzemducjzjqd.onion` | DOM Cloud Asia-Pacific East |
| 15 | 🇸🇬 Singapore | `o5yf3eukrwpt2g6jfo4q2y23xtuhoso2qknmnn6ac5eng5t4yt36roqd.onion` | DOM Cloud Southeast Asia Hub |
| 16 | 🇩🇪 Germany (Nuremberg) | `o5zqqfl5znzexdojfnxgub5jnjelxdahbyxasjp57sx6fbxtjeqovpad.onion` | DOM Cloud Central Europe |
| 17 | 🇨🇳 China (Hangzhou) | `2amizuhb3p5x2lk3sra7f7thm5tgs7qtnysgowqpmexcqi4cuwyv7vad.onion` | ModelScope CN / GFW Bypass |

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
