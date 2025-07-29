---
feature: "Remote Development - SSH Pre-Connection Script & Remote Explorer"
release: "1.101"
prerequisites:
  - "Remote Development extension pack (ms-vscode-remote.vscode-remote-extensionpack)"
  - "SSH access to remote machines or cloud instances"
  - "Basic understanding of SSH configuration and remote development workflows"
  - "Command line familiarity for SSH setup and troubleshooting"
audience: "DevOps Engineers, Cloud Developers, Remote Teams, System Administrators"
---

# 🚀 Feature Training: `Remote Development - SSH Pre-Connection Script & Remote Explorer` in VS Code `1.101`

## 1. Overview

- **Feature Name:** `Remote Development - SSH Pre-Connection Script & Remote Explorer`
- **Release Version:** `1.101`
- **Feature Type:** `Remote Development Enhancement, Infrastructure Automation, Developer Experience`
- **Summary:**  
  Enhanced remote development capabilities featuring SSH pre-connection scripts for automated environment setup and improved Remote Explorer interface for streamlined host management. These improvements reduce friction in multi-host workflows and enable consistent remote environment preparation.

## 2. Why It Matters

- **Core Problem Solved:** Eliminates manual environment setup on remote hosts, reduces connection friction for complex SSH configurations, and provides unified management interface for multiple remote development targets.
- **Target Users:** Developers working across multiple cloud instances, teams with standardized development environments, DevOps engineers managing remote workspaces, and organizations requiring compliance or security setup before remote access.
- **Context:** Remote development is increasingly critical as teams adopt cloud-first development, containerized environments, and distributed infrastructure requiring consistent setup and management.

## 3. Feature Details

### 3.1 Prerequisites

- Required VS Code version: `1.101+`
- Remote Development extension pack: `ms-vscode-remote.vscode-remote-extensionpack`
- SSH client configured on local machine
- Remote hosts accessible via SSH with appropriate permissions
- Understanding of SSH configuration files and connection parameters

### 3.2 How to Enable/Access

- **SSH Pre-Connection Script:** Configure via SSH host settings in VS Code or SSH config file
- **Remote Explorer:** Built-in panel accessible via Activity Bar or `Ctrl+Shift+P` → `Remote-SSH: Connect to Host`
- **Host Management:** Remote Explorer automatically detects SSH configurations and provides management interface
- **Script Configuration:** Define scripts through VS Code settings or SSH configuration parameters

### 3.3 Step-by-Step Usage

#### 3.3.1 SSH Pre-Connection Script Setup

**Configuration Methods:**

1. **VS Code Settings:** Configure per-host scripts through remote settings
2. **SSH Config File:** Add script parameters to `~/.ssh/config`
3. **Workspace Settings:** Define scripts specific to project requirements

**Basic Configuration:**

1. **Open SSH Config:** Command Palette → `Remote-SSH: Open SSH Configuration File`
2. **Add Host with Script:**

   ```
   Host my-dev-server
       HostName server.example.com
       User developer
       PreConnectionScript /path/to/setup-script.sh
   ```

3. **Create Setup Script:** Design script for environment preparation
4. **Test Connection:** Connect through Remote Explorer to verify script execution

**Script Example:**

```bash
#!/bin/bash
# setup-script.sh - Environment preparation script

# Set environment variables
export NODE_ENV=development
export PYTHON_PATH=/opt/python3.11/bin

# Activate virtual environment
source /home/developer/venv/bin/activate

# Mount additional filesystems
sudo mount /dev/sdb1 /mnt/data

# Configure SSH agent forwarding
eval $(ssh-agent)
ssh-add ~/.ssh/id_rsa

# Log setup completion
echo "Environment setup completed for VS Code connection" >> ~/.vscode-setup.log
```

#### 3.3.2 Remote Explorer Enhanced Management

**Host Organization:**

1. **Access Remote Explorer:** Activity Bar → Remote Explorer icon
2. **View SSH Targets:** All configured SSH hosts displayed with status indicators
3. **Host Actions:** Right-click for context menu with connection options
4. **Search and Filter:** Use search to quickly locate specific hosts

**Connection Management:**

1. **Quick Connect:** Click host name for immediate connection
2. **New Window:** Open host in new VS Code window
3. **Edit Configuration:** Direct access to SSH config editing
4. **Connection History:** Recently used hosts prominently displayed

**Advanced Features:**

- **Host Status Indicators:** Visual representation of connection state
- **Bulk Operations:** Manage multiple hosts simultaneously
- **Connection Profiles:** Save different connection configurations per host
- **Error Diagnostics:** Clear feedback for connection issues

#### 3.3.3 Workflow Integration

**Development Environment Setup:**

1. **Define Standard Script:** Create organization-wide setup script
2. **Configure Host:** Add script to SSH configuration
3. **Connect Seamlessly:** Remote Explorer handles automated setup
4. **Begin Development:** Environment ready with all dependencies

**Multi-Host Workflow:**

```
Development → Testing → Production
↓              ↓           ↓
Script A    Script B   Script C
(Dev deps) (Test env) (Prod config)
```

### 3.4 Example(s)

#### Simple Example: Python Development Setup

```bash
# ~/.ssh/config
Host python-dev
    HostName dev.company.com
    User developer
    PreConnectionScript ~/.ssh/scripts/python-setup.sh

# python-setup.sh
#!/bin/bash
# Activate Python virtual environment
source ~/projects/myapp/venv/bin/activate
# Set development environment variables
export DEBUG=true
export DATABASE_URL=postgresql://localhost/dev_db
# Ensure VS Code server dependencies
pip install pylsp black flake8
```

#### Advanced Example: Microservices Development Environment

```bash
# Multi-service setup script
#!/bin/bash
# microservices-setup.sh

# Start required services
docker-compose up -d database redis
sleep 10

# Setup environment for each service
for service in api worker frontend; do
    cd ~/microservices/$service
    npm install
    source .env.development
done

# Configure load balancer
sudo nginx -s reload

# Setup monitoring
systemctl --user start prometheus node-exporter

echo "Microservices development environment ready"
```

#### Complex Example: Compliance and Security Setup

```bash
#!/bin/bash
# compliance-setup.sh

# Apply security policies
sudo /opt/security/apply-dev-policies.sh

# Mount encrypted workspace
cryptsetup luksOpen /dev/sdb1 secure-workspace
mount /dev/mapper/secure-workspace /secure/workspace

# Configure audit logging
auditctl -w /secure/workspace -p wa -k vscode-access

# Setup VPN if required
if ! pgrep openvpn; then
    sudo openvpn --config /etc/openvpn/company.conf --daemon
fi

# Verify compliance
/opt/compliance/verify-environment.sh || exit 1

echo "Compliance and security setup completed"
```

### 3.5 Advanced Features and Integration

#### Script Security and Validation

- **Script Verification:** VS Code validates script permissions and integrity before execution
- **Error Handling:** Comprehensive error reporting if pre-connection scripts fail
- **Timeout Management:** Configurable timeouts prevent hanging connections
- **Logging Integration:** Script output available in VS Code Remote Development logs

#### Remote Explorer Enhancements

- **Session Management:** Track multiple concurrent remote sessions
- **Resource Monitoring:** Display basic resource usage for connected hosts
- **Configuration Sync:** Synchronize SSH configurations across VS Code instances
- **Integration APIs:** Extension points for custom remote connection types

#### Enterprise Integration

- **Centralized Configuration:** Support for organization-wide SSH configuration management
- **Policy Enforcement:** Integration with enterprise security and compliance frameworks
- **Audit Trail:** Detailed logging of remote connections and script executions
- **Single Sign-On:** Integration with enterprise authentication systems

## 4. Troubleshooting & FAQ

### Common Issues

- **Script Execution Fails:** Check script permissions, path validity, and execution environment
- **Connection Timeout:** Verify script execution time and adjust timeout settings
- **Remote Explorer Not Updating:** Refresh configuration or restart VS Code Remote Development extensions
- **SSH Config Not Detected:** Ensure SSH config file format and location are correct

### How to Disable

- **Disable Pre-Connection Scripts:** Remove script parameters from SSH configuration
- **Revert to Standard SSH:** Use traditional SSH connection without VS Code automation
- **Disable Remote Explorer:** Hide Remote Explorer panel or use command-line SSH
- **Manual Environment Setup:** Connect first, then manually configure environment

### Edge Cases

- **Cross-Platform Scripts:** Script compatibility between Windows, macOS, and Linux hosts
- **Network Limitations:** Script execution in restricted network environments
- **Resource Constraints:** Script behavior on resource-limited remote hosts
- **Permission Escalation:** Handling sudo/elevated permissions in automated scripts

### FAQ

**Q: Can pre-connection scripts access local environment variables?**
A: Scripts execute on the remote host, so they only have access to remote environment variables and those passed through SSH.

**Q: Are pre-connection scripts executed every time I connect?**
A: Yes, scripts run on each new connection. Use conditional logic in scripts to avoid redundant operations.

**Q: Can I use different scripts for different projects on the same host?**
A: Yes, configure project-specific SSH host entries with different script paths.

**Q: What happens if a pre-connection script fails?**
A: VS Code will display an error and prevent the remote connection, ensuring environment integrity.

## 5. Additional Resources

- **Remote Development:** [Remote Development with VS Code](https://code.visualstudio.com/docs/remote/remote-overview)
- **SSH Configuration:** [SSH Configuration Guide](https://code.visualstudio.com/docs/remote/ssh)
- **Remote Troubleshooting:** [Remote Development Troubleshooting](https://code.visualstudio.com/docs/remote/troubleshooting)
- **Extension Pack:** [Remote Development Extension Pack](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.vscode-remote-extensionpack)
- **Security Best Practices:** [Remote Development Security](https://code.visualstudio.com/docs/remote/ssh#_security-considerations)
- **Related Features:** Dev Containers, WSL, Codespaces, Remote Tunnels

## 6. Revision Log

| Date        | Author    | Change Summary                       |
|-------------|-----------|--------------------------------------|
| 2025-07-28  | Assistant | Initial micro-training for Remote Development enhancements |
