# tailscale-vpn-exitnode
This repository provides a docker-compose setup for creating an encrypted VPN connection using Tailscale and ProtonVPN. The configuration allows your containerized applications to route traffic securely through Tailscale and uses ProtonVPN as an exit-node, enabling flexible and private networking across devices and environments.

## 🔧 Features

- 🔐 Secure outbound traffic via ProtonVPN (Wireguard-based connection).
- 📦 Fully containerized setup using docker-compose or portainer.
- 🧩 Suitable for cloud instances, home labs, or headless environments.
- ⚙️ Easily customizable and extensible for other VPN providers (with some modifications).
- 🛡️ Ideal for privacy-conscious developers and DevOps professionals.


## 📁 Contents

- compose.yaml: Multi-container setup for Gluetun (VPN) and Tailscale.
- README.md: Setup instructions, environment variables, and usage guide.


## 💡 Use Cases

- Remote development over Tailscale with ProtonVPN routing.
- Building self-hosted solutions with reliable encrypted traffic.
- Bypassing geo-restrictions while maintaining full privacy.

## 🚀 Installation

### 🧰 Prerequisites

Ensure you have the following installed:
- Docker
- Docker Compose or Portainer
- Active accounts for:
  - ProtonVPN
  - Tailscale

### 🔑 Step 1: Prepare Credential and Update compose.yaml

🔐 ProtonVPN
1.  Create WireGuard/OpenVPN configuration\
    Go to the ProtonVPN dashboard, go to “Downloads” menu, and select WireGuard/OpenVPN configuration for your preferred server. Then copy the configuration.
2.  Update compose.yaml\
    Update compose.yaml variables with your WireGuard/OpenVPN configuration.

🌐 Tailscale
1.  Generate a credential\
    Visit https://login.tailscale.com/admin/settings/trust-credentials and create a credential. Go to "Keys" section, check "Write" on "Auth Keys" only. Save changes and get your credential.
2.  Update compose.yaml\
    Update TS_AUTHKEY= with credential that generated before.

### ▶️ Step 2: Start the Services

### Step 3: Activate exit-node
1.  Visit Tailscale Machine\
    Go to https://login.tailscale.com/admin/machines/ and open the machine you just created. Machine's name should be the same with the TS_HOSTNAME you put in compose.yaml.
2.  Turn on the exit-node\
    Look for Exit Node in Routing Settings and click Edit. Turn on "Use as exit mode" then Save.
3.  Exit node is now ready to use.
