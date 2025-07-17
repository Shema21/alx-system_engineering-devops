# 0x18. Webstack Monitoring

## Task 0: Sign up for Datadog and install datadog-agent

### Description

This task involves setting up monitoring for a web server (`web-01`) using Datadog. Datadog is a cloud-based monitoring and analytics platform for infrastructure, applications, logs, and more.

### Steps Followed

1. **Sign Up on Datadog**
   - Created an account on [https://app.datadoghq.com](https://app.datadoghq.com)
   - Region selected: **US1**

2. **Install Datadog Agent on web-01**
   - Followed the setup instructions from Datadog after selecting **Ubuntu** as the OS.
   - Commands executed on `web-01`:
     ```bash
     DD_API_KEY=<your_api_key> bash -c "$(curl -L https://s3.amazonaws.com/dd-agent/scripts/install_script.sh)"
     ```
   - Replaced `<your_api_key>` with the actual API key provided by Datadog.

3. **Create Datadog Application Key**
   - Navigated to **Integrations > APIs** in the Datadog dashboard.
   - Generated a new Application Key.

4. **Update Hostname (if needed)**
   - If the server did not appear with the correct name (`XX-web-01`), updated the hostname:
     ```bash
     sudo hostnamectl set-hostname XX-web-01
     ```

5. **Verify Server Visibility**
   - Used Datadog’s API to confirm that the host `XX-web-01` is visible.
   - Example API call:
     ```bash
     curl -X GET "https://api.datadoghq.com/api/v1/hosts" \
     -H "DD-API-KEY: <your_api_key>" \
     -H "DD-APPLICATION-KEY: <your_application_key>"
     ```

6. **Submit Keys to Intranet**
   - Pasted the **Datadog API Key** and **Application Key** into the ALX Intranet profile as required.

---

### Directory Structure

0x18-webstack_monitoring/
│
├── README.md # This file
