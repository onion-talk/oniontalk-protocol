<div align="center">
  <img src="https://raw.githubusercontent.com/onion-talk/.github/main/assets/oniontalk-icon-512.png" alt="OnionTalk Logo" width="110" height="110" />
  <h1>OnionTalk Protocol — Repository Archived & Consolidated</h1>
  <p><strong>Moved to <a href="https://github.com/onion-talk/oniontalk-relay/blob/main/docs/PROTOCOL.md"><code>onion-talk/oniontalk-relay/docs/PROTOCOL.md</code></a></strong></p>

  <p>
    <img src="https://img.shields.io/badge/Status-Archived_%26_Consolidated-6E7681?style=for-the-badge" alt="Archived Repository" />
    <a href="https://github.com/onion-talk/oniontalk-relay/blob/main/docs/PROTOCOL.md">
      <img src="https://img.shields.io/badge/ENVELOPE__V3_Spec-oniontalk--relay-00E676?style=for-the-badge&logo=rust&logoColor=black" alt="Read ENVELOPE_V3 Spec" />
    </a>
    <a href="https://oniontalk.co/">
      <img src="https://img.shields.io/badge/Official_Site-oniontalk.co-00E5FF?style=for-the-badge" alt="Official Website" />
    </a>
  </p>
</div>

---

## 📦 Repository Decommissioned & Consolidated (Read-Only Archive)

This standalone repository has been **archived in read-only mode** and its GitHub Pages mirror has been retired to eliminate stale documentation drift and duplicate binary/web artifacts.

All canonical protocol documentation now lives directly alongside the production Rust relay implementation in [**`onion-talk/oniontalk-relay`**](https://github.com/onion-talk/oniontalk-relay):

- **📜 Wire Protocol Specification (`ENVELOPE_V3`, `ML-KEM-768`, `otcrl1:` Offline Root CA PKI, Tor 0.4.9 Equi-X PoW, GossipSub v1.2 & S/Kademlia XOR)**:
  [**`onion-talk/oniontalk-relay/docs/PROTOCOL.md`**](https://github.com/onion-talk/oniontalk-relay/blob/main/docs/PROTOCOL.md)
- **🧅 Architectural Manifesto & Anti-Censorship Engineering**:
  [**`onion-talk/oniontalk-relay/docs/MANIFESTO.md`**](https://github.com/onion-talk/oniontalk-relay/blob/main/docs/MANIFESTO.md)
- **🌐 Official Website & Privacy Policy**:
  [**https://oniontalk.co/**](https://oniontalk.co/) · [**Privacy Policy**](https://oniontalk.co/privacy.html)
- **📱 Official Android App (Google Play & Direct Signed APK)**:
  [**Google Play Store**](https://play.google.com/store/apps/details?id=org.oniontalk.messenger) · [**Download `OnionTalk.apk` (latest)**](https://github.com/onion-talk/oniontalk-demo/releases/latest/download/OnionTalk.apk) ![Latest Messenger Release](https://img.shields.io/github/v/release/onion-talk/oniontalk-demo?style=flat-square&label=release&color=00E5FF) ([`SHA256SUMS.txt`](https://github.com/onion-talk/oniontalk-demo/releases/latest/download/SHA256SUMS.txt))
- **🦀 Standalone Android Relay Node APK**:
  [**Download `OnionTalk-RelayNode.apk` (latest)**](https://github.com/onion-talk/oniontalk-relay/releases/latest/download/OnionTalk-RelayNode.apk) ![Latest Relay Release](https://img.shields.io/github/v/release/onion-talk/oniontalk-relay?style=flat-square&label=release&color=00E676) ([`SHA256SUMS.txt`](https://github.com/onion-talk/oniontalk-relay/releases/latest/download/SHA256SUMS.txt))

---

## 🔒 Source Code Availability Disclaimer / Aviso sobre o Código-Fonte

- **EN:** The federated Tor v3 Rust Relay ([`oniontalk-relay`](https://github.com/onion-talk/oniontalk-relay)) and the formal `ENVELOPE_V3` Wire Protocol Specification ([`docs/PROTOCOL.md`](https://github.com/onion-talk/oniontalk-relay/blob/main/docs/PROTOCOL.md)) remain **100% open-source under the MIT License**. The source code of the client applications (`org.oniontalk.messenger` Android, `onion-talk-web`, and iOS) is **temporarily locked / restricted for now** while ongoing security hardening, architectural stabilization, and pre-audit reviews are underway.
- **PT-BR:** O servidor Relay federado em Rust ([`oniontalk-relay`](https://github.com/onion-talk/oniontalk-relay)) e a especificação formal do protocolo `ENVELOPE_V3` ([`docs/PROTOCOL.md`](https://github.com/onion-talk/oniontalk-relay/blob/main/docs/PROTOCOL.md)) permanecem **100% open-source sob licença MIT**. **O código-fonte dos aplicativos clientes (`org.oniontalk.messenger`, `onion-talk-web` e iOS) está bloqueado/fechado temporariamente** durante a fase atual de hardening criptográfico e estabilização pré-auditoria.

---

## ⚠️ Legal Disclaimers, Limitation of Liability & Sovereign Terms of Use

1. **"AS IS" Provision, Open-Source Relay & Temporarily Restricted Client Source**: The OnionTalk federated Rust relay (`oniontalk-relay`) and `ENVELOPE_V3` wire specification are open-source under the MIT License. The source code of the client applications (`org.oniontalk.messenger`, `onion-talk-web`, and iOS) is temporarily restricted/closed for now during active security hardening. All binaries and containers are distributed strictly **"AS IS"**, without warranties of any kind, as cryptographic engineering and digital privacy technology (`Privacy by Design`).
2. **Irreversible Zero-Knowledge Custody (No Password Recovery)**: Because OnionTalk operates without central servers, user accounts, emails, or phone numbers, **the developers cannot recover forgotten vault passwords, restore lost private keys, or reverse the 5-Strike Anti-Coercion Wipe (`DoD 5220.22-M`) or Synchronized Bilateral Burn (`🔥`)**. Users are solely responsible for safeguarding their local credentials and backups.
3. **Blind Common-Carrier Relay Safe Harbor**: Federated `.onion` v3 relay nodes act strictly as **blind, non-custodial encrypted envelope routers**. Relays possess neither the private `X25519` keys nor the post-quantum `ML-KEM-768` decapsulation keys required to inspect, filter, or modify message contents, and expose only deterministic synthetic topology coordinates (`Zero IP / Zero Cloud Provider Leak`).
4. **Lawful Use & User Responsibility**: Users assume full and exclusive legal responsibility for their use of the software in their respective jurisdictions. Using OnionTalk for unlawful activities is strictly prohibited by the project's terms of use.
5. **Non-Affiliation**: OnionTalk is an independent project and is not affiliated with, endorsed by, or sponsored by *The Tor Project, Inc.*
