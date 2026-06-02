# Wazuh for Umbrel

A [Community App Store](https://github.com/getumbrel/umbrel-community-app-store)
for [umbrelOS](https://umbrel.com) that packages **[Wazuh](https://wazuh.com)** —
the free and open source security platform (XDR + SIEM) — as a one‑click app.

## Add this store to your Umbrel

1. Open the **App Store** on your Umbrel.
2. Click the **⋮** menu (top right) → **Community App Stores**.
3. Paste this repository URL:

   ```
   https://github.com/gabrysh/umbrel-wazuh
   ```

4. Click **Add**, then open the **Wazuh for Umbrel** store and install **Wazuh**.

After installing, open the app and log in with the default credentials
(`admin` / `SecretPassword`) — **change the password right after the first
login**. The first start can take a few minutes while the indexer initializes.

## What is Wazuh?

Wazuh is a free and open source security platform that unifies **XDR** and
**SIEM** capabilities. It protects workloads across on‑premises, virtualized,
containerized, and cloud environments, giving you a single place to detect
threats, monitor integrity, and respond to incidents.

This app deploys the full **single‑node** stack:

| Component         | Role                                                        |
| ----------------- | ----------------------------------------------------------- |
| Wazuh indexer     | Stores and indexes alerts and security events (OpenSearch). |
| Wazuh manager     | Analyzes events and manages the connected agents.           |
| Wazuh dashboard   | Web interface for monitoring, hunting, and configuration.   |

### Key capabilities

- **Intrusion detection** and log data analysis
- **File integrity monitoring** (FIM)
- **Vulnerability detection** on monitored endpoints
- **Security configuration assessment** (CIS benchmarks)
- **Threat hunting** with rules mapped to **MITRE ATT&CK**
- **Regulatory compliance** support (PCI DSS, GDPR, HIPAA, NIST 800‑53)

## How it works on Umbrel

- The dashboard is served behind Umbrel's app proxy and protected by your
  Umbrel account password.
- TLS certificates are generated automatically on first boot and reused on
  every restart.
- The required `vm.max_map_count` kernel setting is applied automatically.
- The Wazuh manager exposes the standard ports (`1514`, `1515`, `514/udp`,
  `55000`) so agents on your network can report in.

## Licensing

The packaging in this repository is released under the **[MIT License](LICENSE)**.
**Wazuh itself** is developed by Wazuh, Inc. and distributed under the
**GPLv2** license. This project only packages the official Wazuh Docker images;
all Wazuh trademarks and copyrights belong to their respective owners.

## Credits

- [Wazuh](https://github.com/wazuh/wazuh) and the official
  [wazuh-docker](https://github.com/wazuh/wazuh-docker) deployment.
- [Umbrel](https://github.com/getumbrel/umbrel) and the
  [community app store template](https://github.com/getumbrel/umbrel-community-app-store).

---

Wazuh agents can be installed on Linux, Windows, macOS, and more,
and report back to your Umbrel node for centralized monitoring.

⚠️ Recommended: 4GB RAM minimum, 8GB+ for production use.
