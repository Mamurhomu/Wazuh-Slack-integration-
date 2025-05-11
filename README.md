# Wazuh-Slack-integration-
This project integrates Wazuh with Slack to enhance security operations for SOC teams. It forwards real-time alerts from Wazuh to Slack channels, enabling quick response and collaboration. This integration helps SOC analysts receive critical event data instantly, improving incident response times and overall operational efficiency.
# 🛡️ Wazuh + Slack Integration

This project demonstrates how to integrate the **Wazuh SIEM server** with **Slack** to receive real-time security alerts directly in a Slack channel. It includes setup steps, configuration snippets, and a working example.

## 📌 Project Overview

- ✅ Wazuh Server (v4.9.2) installed and running
- ✅ Slack App created and webhook configured
- ✅ Wazuh alerts forwarded to a specific Slack channel
- ✅ Alerts formatted in `JSON` for readability
- ✅ Verified with test logs from endpoint agent (Windows)

---

## ⚙️ Requirements

- Wazuh Manager installed and configured
- Slack Workspace and channel
- Incoming Webhook enabled in Slack
- Wazuh Agent(s) installed on endpoint(s)

---

## 🧪 Steps to Integrate Wazuh Alerts with Slack

### 1. 📥 Create Incoming Webhook in Slack

1. Go to: [https://api.slack.com/apps](https://api.slack.com/apps)
2. Create a new app → Select "From scratch"
3. Add `Incoming Webhooks` feature
4. Activate Webhooks → Click "Add New Webhook to Workspace"
5. Choose the desired Slack channel
6. Copy the generated **Webhook URL**

---

### 2. 🛠️ Configure Integration in Wazuh

Edit the Wazuh manager integration config file:
```bash
sudo nano /var/ossec/etc/ossec.conf
<integration>
  <name>slack</name>
  <hook_url>https://hooks.slack.com/services/XXXXX/YYYYY/ZZZZZZ</hook_url> <!-- Replace with your actual webhook -->
  <alert_format>json</alert_format>
</integration>
sudo systemctl restart wazuh-manager
4. ✅ Test the Integration
Trigger an event (e.g., login, file change, new agent registration) and check your Slack channel for alerts.

🔔 Example Slack Alert
Below is a screenshot of a successful alert received in the Slack channel after integration:
🧠 Summary
Integrating Slack with Wazuh provides instant visibility into security events. It's lightweight, quick to set up, and ideal for small SOC teams or personal labs.
📧 Contact
Mamurhomu Adugbo
🔗 GitHub: mamurhomu![Screenshot 2025-05-10 194653](https://github.com/user-attachments/assets/ea3c5adf-ccb9-48a6-86c3-803e0f055fac)
![IMG_3503](https://github.com/user-attachments/assets/af27c17c-48bc-441a-8d2f-a2597cc7b1b6)
![Screenshot 2025-05-11 090516](https://github.com/user-attachments/assets/792ef91f-c4da-4f0f-b581-353ac024d174)
![Screenshot 2025-05-11 090458](https://github.com/user-attachments/assets/c72322c5-769a-4b89-9ff4-9495d28e032e)
