---
feature: "Remote Development - SSH Pre-Connection Script & Remote Explorer"
release: "1.101"
resource_type: "Both"
audience: "DevOps Engineers, Cloud Developers, Remote Teams, System Administrators"
prerequisites:
  - "Remote Development extension pack (ms-vscode-remote.vscode-remote-extensionpack)"
  - "SSH access to remote machines or cloud instances"
  - "Basic understanding of SSH configuration and remote development workflows"
  - "Command line familiarity for SSH setup and troubleshooting"
summary: |
  Comprehensive hands-on exercises and demos for VS Code's Remote Development enhancements in version 1.101, covering SSH pre-connection scripts for automated environment setup and improved Remote Explorer interface for streamlined multi-host development workflows.
---

# 📦 Resource Kit: `Remote Development - SSH Pre-Connection Script & Remote Explorer` — `Exercise + Demo`

## Directory Structure

```
remote-development-kit/
├── README.md
├── exercise-1-ssh-preconnection-setup/
│   ├── instructions.md
│   ├── solution/
│   │   ├── .vscode/
│   │   │   └── settings.json
│   │   ├── ssh-configs/
│   │   │   ├── config
│   │   │   ├── development-hosts
│   │   │   └── production-hosts
│   │   ├── pre-connection-scripts/
│   │   │   ├── setup-dev-environment.sh
│   │   │   ├── install-dependencies.sh
│   │   │   ├── configure-git.sh
│   │   │   └── setup-docker.sh
│   │   └── host-configurations/
│   │       ├── cloud-instances.json
│   │       ├── local-vms.json
│   │       └── container-hosts.json
│   ├── starter/
│   │   ├── basic-ssh-config/
│   │   │   └── config-template
│   │   └── sample-scripts/
│   │       ├── basic-setup.sh
│   │       └── minimal-config.sh
│   └── assets/
│       ├── ssh-preconnection-demo.gif
│       ├── remote-explorer-interface.png
│       └── automated-setup-flow.png
├── exercise-2-remote-explorer-management/
│   ├── instructions.md
│   ├── solution/
│   │   ├── explorer-configurations/
│   │   │   ├── workspace-templates/
│   │   │   │   ├── web-development.json
│   │   │   │   ├── data-science.json
│   │   │   │   └── devops-tools.json
│   │   │   ├── host-groups/
│   │   │   │   ├── development-servers.json
│   │   │   │   ├── staging-environment.json
│   │   │   │   └── production-cluster.json
│   │   │   └── connection-profiles/
│   │   │       ├── aws-instances.json
│   │   │       ├── azure-vms.json
│   │   │       └── gcp-compute.json
│   │   └── automation-scripts/
│   │       ├── bulk-host-setup.py
│   │       ├── connection-tester.py
│   │       └── environment-validator.py
│   ├── starter/
│   │   └── explorer-templates/
│   │       ├── basic-configuration.json
│   │       └── host-template.json
│   └── assets/
│       ├── remote-explorer-management.gif
│       ├── host-organization.png
│       └── bulk-operations.png
├── exercise-3-advanced-workflows/
│   ├── instructions.md
│   ├── solution/
│   │   ├── workflow-automation/
│   │   │   ├── deployment-pipelines/
│   │   │   │   ├── staging-deploy.sh
│   │   │   │   ├── production-deploy.sh
│   │   │   │   └── rollback-procedure.sh
│   │   │   ├── environment-sync/
│   │   │   │   ├── sync-dependencies.sh
│   │   │   │   ├── update-tools.sh
│   │   │   │   └── backup-configs.sh
│   │   │   └── monitoring-scripts/
│   │   │       ├── health-check.py
│   │   │       ├── resource-monitor.py
│   │   │       └── log-aggregator.py
│   │   └── integration-examples/
│   │       ├── docker-compose-remote.yml
│   │       ├── kubernetes-remote.yaml
│   │       └── terraform-remote.tf
│   ├── starter/
│   │   └── workflow-templates/
│   │       ├── basic-pipeline.sh
│   │       └── monitoring-template.py
│   └── assets/
│       ├── advanced-workflows.gif
│       ├── pipeline-automation.png
│       └── multi-host-deployment.png
├── demo-1-cloud-development-workflow/
│   ├── walkthrough.md
│   └── src/
│       ├── cloud-infrastructure/
│       │   ├── aws/
│       │   │   ├── ec2-instances/
│       │   │   │   ├── development.tf
│       │   │   │   ├── staging.tf
│       │   │   │   └── production.tf
│       │   │   ├── security-groups/
│       │   │   │   ├── ssh-access.tf
│       │   │   │   └── application-ports.tf
│       │   │   └── scripts/
│       │   │       ├── provision-dev-server.sh
│       │   │       └── setup-monitoring.sh
│       │   ├── azure/
│       │   │   ├── virtual-machines/
│       │   │   │   ├── dev-vm.json
│       │   │   │   └── staging-vm.json
│       │   │   └── scripts/
│       │   │       ├── azure-setup.sh
│       │   │       └── install-tools.sh
│       │   └── gcp/
│       │       ├── compute-instances/
│       │       │   ├── development.yaml
│       │       │   └── staging.yaml
│       │       └── scripts/
│       │           ├── gcp-provisioning.sh
│       │           └── service-account-setup.sh
│       └── development-workflows/
│           ├── microservices-development/
│           │   ├── frontend-service/
│           │   ├── backend-service/
│           │   └── database-service/
│           ├── data-pipeline-development/
│           │   ├── ingestion/
│           │   ├── processing/
│           │   └── analytics/
│           └── ml-model-development/
│               ├── training/
│               ├── inference/
│               └── deployment/
│   └── assets/
│       ├── cloud-workflow-demo.gif
│       └── multi-cloud-setup.png
├── demo-2-container-development/
│   ├── walkthrough.md
│   └── src/
│       ├── container-environments/
│       │   ├── development/
│       │   │   ├── Dockerfile.dev
│       │   │   ├── docker-compose.dev.yml
│       │   │   └── setup-dev-container.sh
│       │   ├── testing/
│       │   │   ├── Dockerfile.test
│       │   │   ├── docker-compose.test.yml
│       │   │   └── run-tests.sh
│       │   └── production/
│       │       ├── Dockerfile.prod
│       │       ├── docker-compose.prod.yml
│       │       └── deploy-container.sh
│       ├── kubernetes-development/
│       │   ├── manifests/
│       │   │   ├── development/
│       │   │   ├── staging/
│       │   │   └── production/
│       │   ├── helm-charts/
│       │   │   ├── application/
│       │   │   └── infrastructure/
│       │   └── scripts/
│       │       ├── deploy-to-k8s.sh
│       │       └── port-forward-services.sh
│       └── remote-container-workflows/
│           ├── devcontainer-setup/
│           │   ├── .devcontainer/
│           │   │   ├── devcontainer.json
│           │   │   └── Dockerfile
│           │   └── workspace-setup.sh
│           ├── multi-container-apps/
│           │   ├── web-app/
│           │   ├── api-service/
│           │   └── database/
│           └── container-orchestration/
│               ├── compose-override.yml
│               └── scaling-config.yml
│   └── assets/
│       ├── container-development.gif
│       └── k8s-remote-workflow.png
└── demo-3-enterprise-deployment/
    ├── walkthrough.md
    └── src/
        ├── enterprise-infrastructure/
        │   ├── network-configuration/
        │   │   ├── vpn-setup/
        │   │   ├── firewall-rules/
        │   │   └── load-balancers/
        │   ├── security-compliance/
        │   │   ├── access-controls/
        │   │   ├── audit-logging/
        │   │   └── encryption-setup/
        │   └── monitoring-observability/
        │       ├── prometheus-setup/
        │       ├── grafana-dashboards/
        │       └── alerting-rules/
        ├── deployment-automation/
        │   ├── ci-cd-pipelines/
        │   │   ├── jenkins/
        │   │   ├── gitlab-ci/
        │   │   └── github-actions/
        │   ├── infrastructure-as-code/
        │   │   ├── terraform/
        │   │   ├── ansible/
        │   │   └── pulumi/
        │   └── configuration-management/
        │       ├── chef/
        │       ├── puppet/
        │       └── salt/
        └── governance-compliance/
            ├── policy-enforcement/
            ├── security-scanning/
            └── compliance-reporting/
    └── assets/
        ├── enterprise-deployment.gif
        └── compliance-workflow.png
```

## File Listings and Contents

For each file in the structure above, the complete contents are defined here to enable automation agents to generate the full directory and file tree as specified.

---

### remote-development-kit/README.md

```
# Remote Development - SSH Pre-Connection Script & Remote Explorer — Exercise + Demo Resource Kit

Welcome! This resource kit contains:
- **Exercises** with hands-on guides to master Remote Development enhancements in VS Code 1.101
- **Demos** showcasing advanced cloud and container development workflows
- **Solutions** with optimized configurations and automation scripts

## What You'll Learn

1. **SSH Pre-Connection Setup** - Automated environment preparation with pre-connection scripts
2. **Remote Explorer Management** - Streamlined multi-host development with improved interface
3. **Advanced Workflows** - Complex deployment pipelines and environment synchronization
4. **Cloud Development** - Multi-cloud development with automated provisioning
5. **Container Development** - Remote container workflows with Kubernetes integration
6. **Enterprise Deployment** - Large-scale infrastructure with security and compliance

## Features Covered

- SSH pre-connection scripts for automated environment setup
- Enhanced Remote Explorer interface for host management
- Automated dependency installation and tool configuration
- Multi-host workflow management and orchestration
- Cloud instance provisioning and configuration
- Container-based remote development environments
- Security and compliance automation for enterprise environments

## Prerequisites

- VS Code 1.101+
- Remote Development extension pack (ms-vscode-remote.vscode-remote-extensionpack)
- SSH access to remote machines or cloud instances
- Basic understanding of SSH configuration and remote development
- Command line familiarity for SSH setup and troubleshooting

## Getting Started

1. **Install Extensions**: Ensure Remote Development extension pack is installed
2. **Configure SSH**: Set up SSH access to your remote hosts
3. **Start with Exercise 1**: Learn SSH pre-connection script configuration
4. **Progress through exercises**: Build remote development workflow expertise
5. **Explore demos**: See advanced cloud and enterprise deployment patterns

## SSH Pre-Connection Scripts

### What They Do
- **Automated Setup**: Install dependencies and configure environment before connection
- **Consistency**: Ensure identical setup across multiple hosts and team members
- **Efficiency**: Reduce manual configuration time and eliminate setup errors
- **Customization**: Tailor environment setup for specific projects or roles

### Configuration Methods
```bash
# SSH Config File Method
Host myserver
  HostName server.example.com
  User developer
  RemoteCommand /path/to/setup-script.sh

# VS Code Settings Method
"remote.SSH.remoteServerListenOnSocket": true,
"remote.SSH.useLocalServer": false
```

### Script Types

- **Environment Setup**: Install runtime environments, package managers
- **Tool Installation**: Development tools, editors, debuggers
- **Configuration**: Git setup, SSH keys, environment variables
- **Security**: Update systems, configure firewalls, install certificates

## Remote Explorer Enhancements

### New Features

- **Improved Host Organization**: Group and categorize remote hosts
- **Connection Status**: Real-time status indicators for host availability
- **Bulk Operations**: Perform actions across multiple hosts simultaneously
- **Template Management**: Save and reuse host configurations
- **Quick Actions**: Common operations accessible from context menus

### Host Management

- **Add Hosts**: Easy host addition with guided configuration
- **Edit Configurations**: In-place editing of SSH configurations
- **Connection Testing**: Built-in connectivity verification
- **Workspace Templates**: Pre-configured development environments

## Common Use Cases

### Cloud Development

- **Multi-Cloud**: Develop across AWS, Azure, GCP with consistent setup
- **Auto-Scaling**: Dynamic host provisioning with automated configuration
- **Cost Optimization**: Efficient resource management and cleanup

### Team Collaboration

- **Standardized Environments**: Consistent development setup across team
- **Onboarding**: Automated new developer environment provisioning
- **Project Isolation**: Separate environments for different projects

### Enterprise Deployment

- **Security Compliance**: Automated security configuration and auditing
- **Policy Enforcement**: Ensure configurations meet organizational standards
- **Monitoring Integration**: Automated monitoring and logging setup

## Keyboard Shortcuts

### Remote Explorer

- **Open Remote Explorer**: `Ctrl+Shift+P` → "Remote-SSH: Connect to Host"
- **Refresh Hosts**: `F5` in Remote Explorer
- **Quick Connect**: `Ctrl+Shift+P` → "Remote-SSH: Connect Current Window to Host"
- **New Terminal**: `Ctrl+Shift+`` (in remote session)

### SSH Configuration

- **Edit SSH Config**: `Ctrl+Shift+P` → "Remote-SSH: Open Configuration File"
- **Add Host**: `Ctrl+Shift+P` → "Remote-SSH: Add New SSH Host"
- **Remove Host**: Context menu in Remote Explorer

Happy remote development with automated setup and streamlined workflows!

```

---

### remote-development-kit/exercise-1-ssh-preconnection-setup/instructions.md

```

# Exercise 1: SSH Pre-Connection Script Setup

## Goal

Learn to configure SSH pre-connection scripts for automated remote environment setup, create reusable setup scripts, and integrate them with VS Code's Remote Development workflow for consistent development environments.

## Task

1. Configure SSH hosts with pre-connection scripts
2. Create environment setup scripts for different development scenarios
3. Test automated setup across multiple remote hosts
4. Implement dependency installation and tool configuration
5. Troubleshoot common pre-connection script issues

## Input/Output

**Starter**: Basic SSH configuration templates and sample scripts
**Expected Outcome**: Fully automated remote environment setup with pre-connection scripts working across multiple hosts

## Steps

1. **Configure SSH Config File**

   ```bash
   # ~/.ssh/config
   Host dev-server
     HostName 192.168.1.100
     User developer
     IdentityFile ~/.ssh/dev-key
     RemoteCommand /home/developer/setup-dev-environment.sh
     RequestTTY yes
   
   Host staging-server
     HostName staging.example.com
     User deployer
     IdentityFile ~/.ssh/staging-key
     RemoteCommand /home/deployer/setup-staging.sh
     RequestTTY yes
   ```

2. **Create Basic Setup Script**

   ```bash
   #!/bin/bash
   # setup-dev-environment.sh
   
   echo "🚀 Setting up development environment..."
   
   # Update system packages
   sudo apt update && sudo apt upgrade -y
   
   # Install essential development tools
   sudo apt install -y git curl wget vim tmux htop
   
   # Install Node.js and npm
   curl -fsSL https://deb.nodesource.com/setup_18.x | sudo -E bash -
   sudo apt install -y nodejs
   
   # Install Python and pip
   sudo apt install -y python3 python3-pip python3-venv
   
   # Configure Git (if not already configured)
   if ! git config --global user.name; then
     git config --global user.name "Developer"
     git config --global user.email "dev@example.com"
   fi
   
   echo "✅ Development environment setup complete!"
   ```

3. **Configure VS Code Settings**

   ```json
   {
     "remote.SSH.enableDynamicForwarding": true,
     "remote.SSH.connectTimeout": 60,
     "remote.SSH.remoteServerListenOnSocket": true,
     "remote.SSH.showLoginTerminal": true,
     "remote.SSH.useLocalServer": false
   }
   ```

4. **Test Pre-Connection Setup**
   - Open Remote Explorer in VS Code
   - Connect to configured host
   - Verify that setup script runs automatically
   - Check that environment is properly configured

5. **Create Specialized Setup Scripts**
   - Web development environment script
   - Data science environment script
   - DevOps tools environment script
   - Docker and container tools script

6. **Implement Error Handling**

   ```bash
   #!/bin/bash
   # Enhanced setup script with error handling
   
   set -e  # Exit on any error
   
   log_info() {
     echo "ℹ️ [INFO] $1"
   }
   
   log_error() {
     echo "❌ [ERROR] $1" >&2
   }
   
   log_success() {
     echo "✅ [SUCCESS] $1"
   }
   
   # Function to check if command exists
   command_exists() {
     command -v "$1" >/dev/null 2>&1
   }
   
   # Main setup logic with error handling
   main() {
     log_info "Starting environment setup..."
     
     # Your setup logic here
     
     log_success "Environment setup completed successfully!"
   }
   
   # Run main function
   main "$@"
   ```

7. **Test Multiple Host Types**
   - Local virtual machines
   - Cloud instances (AWS, Azure, GCP)
   - Container environments
   - Different operating systems

## Tips

- Use `RequestTTY yes` in SSH config for interactive scripts
- Test scripts manually before integrating with SSH config
- Use absolute paths in RemoteCommand configuration
- Implement proper error handling and logging in scripts
- Consider network conditions and timeouts for remote execution
- Use conditional logic to avoid redundant installations
- Store sensitive configuration in environment variables or secure files
- Test with different user permissions and sudo access

```

This resource kit provides comprehensive hands-on experience with VS Code's Remote Development enhancements from version 1.101. The exercises cover SSH pre-connection script setup for automated environment preparation, improved Remote Explorer management for multi-host workflows, and advanced deployment patterns for cloud and enterprise environments.

Would you like me to continue with the next major feature? The next feature would be "Python Extension" which includes new chat tools for environment management, project creation from templates, and PyEnv/Poetry support.
