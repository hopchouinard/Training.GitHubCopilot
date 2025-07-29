---
feature: "Extension Authoring - MCP APIs, Secret Scanning & Web Environment Detection"
release: "1.101"
prerequisites:
  - "Node.js and npm/yarn for extension development"
  - "VS Code Extension Development experience"
  - "VSCE (Visual Studio Code Extensions CLI) installed"
  - "Understanding of TypeScript/JavaScript and VS Code Extension API"
audience: "Extension Developers, VS Code Plugin Authors, DevTools Engineers, Platform Developers"
---

# 🚀 Feature Training: `Extension Authoring - MCP APIs, Secret Scanning & Web Environment Detection` in VS Code `1.101`

## 1. Overview

- **Feature Name:** `Extension Authoring - MCP APIs, Secret Scanning & Web Environment Detection`
- **Release Version:** `1.101`
- **Feature Type:** `Developer Platform Enhancement, Security Improvement, Cross-Platform Compatibility`
- **Summary:**  
  Comprehensive extension authoring improvements including MCP (Model Context Protocol) extension APIs for AI integration, automated secret scanning in VSCE packaging, and enhanced web environment detection with Node.js extension host updates. These features enhance security, enable advanced AI functionality, and improve cross-platform extension compatibility.

## 2. Why It Matters

- **Core Problem Solved:** Enables secure AI integration in extensions, prevents accidental secret exposure during publishing, and ensures consistent extension behavior across web and desktop environments.
- **Target Users:** Extension developers building AI-powered extensions, security-conscious developers, and teams creating cross-platform VS Code extensions for both web and desktop.
- **Context:** As VS Code extensions become more sophisticated with AI integration and cross-platform deployment, developers need robust tools for secure development and consistent behavior across environments.

## 3. Feature Details

### 3.1 Prerequisites

- Required VS Code version: `1.101+`
- Node.js development environment
- VSCE CLI tool: `npm install -g vsce`
- TypeScript/JavaScript knowledge for extension development
- Understanding of VS Code Extension API fundamentals

### 3.2 How to Enable/Access

- **MCP Extension APIs:** Available through VS Code Extension API for compatible extensions
- **Secret Scanning:** Automatically enabled in VSCE packaging process
- **Web Environment Detection:** Built-in environment detection APIs in extension host
- **Node.js Global Navigator:** Controlled via `extensions.supportNodeGlobalNavigator` setting

### 3.3 Step-by-Step Usage

#### 3.3.1 MCP Extension APIs Implementation

**Basic MCP Server Integration:**

1. **Install MCP Dependencies:** Add MCP packages to extension
2. **Define MCP Server:** Create or reference MCP server configuration
3. **Register with Extension:** Integrate MCP server with VS Code extension lifecycle
4. **Handle Authentication:** Implement authorization server integration

**MCP Extension Structure:**

```typescript
// package.json contribution
{
  "contributes": {
    "mcpServers": [
      {
        "name": "my-ai-server",
        "command": "node",
        "args": ["./out/mcp-server.js"],
        "env": {
          "API_KEY": "${config:myExtension.apiKey}"
        }
      }
    ]
  }
}
```

**Implementation Example:**

```typescript
// extension.ts
import * as vscode from 'vscode';
import { McpServerProvider } from './mcp-server-provider';

export function activate(context: vscode.ExtensionContext) {
    const mcpProvider = new McpServerProvider();
    
    // Register MCP server
    const mcpRegistration = vscode.extensions.registerMcpServerProvider(
        'my-ai-server',
        mcpProvider
    );
    
    context.subscriptions.push(mcpRegistration);
}
```

#### 3.3.2 Secret Scanning with VSCE

**Automatic Secret Detection:**

1. **Package Extension:** Run standard `vsce package` command
2. **Automatic Scan:** VSCE automatically scans for secrets
3. **Review Results:** Address any detected secrets before publishing
4. **Bypass Options:** Use flags for legitimate secrets if needed

**Common Secret Types Detected:**

- API keys and tokens
- Database connection strings
- Private keys and certificates
- Environment files (`.env`, `.env.local`)
- OAuth secrets and credentials

**Handling Secret Detection:**

```bash
# Standard packaging (with secret scanning)
vsce package

# Error output example:
# Error: Potential secrets detected:
# - API key found in src/config.ts:15
# - Environment file detected: .env.example

# Bypass specific secret types (use cautiously)
vsce package --allow-package-secrets api_key
vsce package --allow-package-env-file

# Best practice: Remove secrets before packaging
# Use environment variables or secure configuration
```

**Secure Configuration Pattern:**

```typescript
// config.ts - Secure approach
export class Config {
    static getApiKey(): string {
        // Read from environment or secure storage
        return process.env.API_KEY || 
               vscode.workspace.getConfiguration('myExtension').get('apiKey') || 
               '';
    }
    
    // Avoid hardcoded secrets
    // private static readonly API_KEY = "sk-123..."; // ❌ Will be detected
}
```

#### 3.3.3 Web Environment Detection

**Environment Detection Implementation:**

```typescript
// environment-detection.ts
export class EnvironmentDetector {
    static isWeb(): boolean {
        // Check for web environment
        return typeof process === 'undefined' || !process.versions?.node;
    }
    
    static isDesktop(): boolean {
        return typeof process === 'object' && !!process.versions?.node;
    }
    
    static getEnvironmentType(): 'web' | 'desktop' {
        return this.isWeb() ? 'web' : 'desktop';
    }
}

// Conditional feature loading
export function loadFeatures() {
    if (EnvironmentDetector.isDesktop()) {
        // Load Node.js-specific features
        const fs = require('fs');
        const path = require('path');
        // ... desktop-only functionality
    } else {
        // Load web-compatible features
        // Use fetch, localStorage, etc.
    }
}
```

**Navigator Global Object Handling:**

```typescript
// navigator-compatibility.ts
export class NavigatorCompat {
    static checkNavigatorSafely() {
        // New approach for Node.js v22+ with navigator global
        if (typeof process === 'object' && process.versions?.node) {
            // Desktop/Node.js environment
            return false; // Not web environment
        }
        
        // Check for web environment
        if (typeof navigator === 'object' && navigator.userAgent) {
            return true; // Web environment
        }
        
        return false;
    }
    
    // Migration pattern for existing code
    static isWebEnvironment(): boolean {
        // Old pattern (deprecated):
        // return typeof navigator === 'object';
        
        // New pattern (recommended):
        return typeof process === 'undefined' || !process.versions?.node;
    }
}
```

#### 3.3.4 Node.js Extension Host Compatibility

**Extension Host Configuration:**

```json
// settings.json for development
{
    "extensions.supportNodeGlobalNavigator": false, // Enable polyfill
    // or
    "extensions.supportNodeGlobalNavigator": true   // Use native navigator
}
```

**Migration Strategy:**

```typescript
// migration-example.ts
export class ExtensionMigration {
    static checkEnvironmentCompatibility() {
        try {
            // Test navigator access with error handling
            const hasNavigator = typeof navigator === 'object';
            
            if (hasNavigator && typeof process === 'object') {
                // Log migration warning in development
                console.warn('Extension using navigator in Node.js environment');
                // Update telemetry for migration tracking
            }
            
            return this.getCorrectEnvironmentCheck();
        } catch (error) {
            console.error('Environment detection error:', error);
            return 'unknown';
        }
    }
    
    private static getCorrectEnvironmentCheck(): string {
        // Recommended approach
        if (typeof process === 'object' && process.versions?.node) {
            return 'desktop';
        } else if (typeof window === 'object' && window.document) {
            return 'web';
        }
        return 'unknown';
    }
}
```

### 3.4 Example(s)

#### Simple Example: Basic MCP Integration

```typescript
// Basic MCP server extension
export class SimpleMcpExtension {
    activate(context: vscode.ExtensionContext) {
        // Register MCP server for AI tools
        const mcpServer = {
            name: 'code-analyzer',
            command: 'node',
            args: ['./mcp-analyzer.js']
        };
        
        vscode.extensions.registerMcpServer(mcpServer);
    }
}
```

#### Advanced Example: Cross-Platform Extension with Secret Management

```typescript
// advanced-extension.ts
export class AdvancedExtension {
    private config: SecureConfig;
    private features: FeatureSet;
    
    async activate(context: vscode.ExtensionContext) {
        // Environment-aware initialization
        this.config = new SecureConfig();
        this.features = this.createFeatures();
        
        // Register MCP with secure configuration
        if (this.features.supportsMCP()) {
            await this.registerMcpServer(context);
        }
        
        // Setup environment-specific functionality
        this.setupEnvironmentFeatures();
    }
    
    private createFeatures(): FeatureSet {
        const env = EnvironmentDetector.getEnvironmentType();
        return env === 'web' ? new WebFeatures() : new DesktopFeatures();
    }
    
    private async registerMcpServer(context: vscode.ExtensionContext) {
        const mcpConfig = {
            name: 'advanced-ai-tools',
            command: this.features.getMcpCommand(),
            args: this.features.getMcpArgs(),
            env: {
                'API_ENDPOINT': this.config.getApiEndpoint(),
                'AUTH_TOKEN': this.config.getAuthToken()
            }
        };
        
        const registration = await vscode.extensions.registerMcpServer(mcpConfig);
        context.subscriptions.push(registration);
    }
}

class SecureConfig {
    getApiEndpoint(): string {
        // Never hardcode secrets - use configuration or environment
        return vscode.workspace.getConfiguration('advancedExt').get('apiEndpoint', '');
    }
    
    getAuthToken(): string {
        // Retrieve from secure storage or prompt user
        return context.secrets.get('authToken') || '';
    }
}
```

#### Complex Example: Multi-Environment Extension with Migration

```typescript
// platform-aware-extension.ts
export class PlatformAwareExtension {
    private environmentType: 'web' | 'desktop';
    private features: Map<string, boolean>;
    
    constructor() {
        this.environmentType = this.detectEnvironment();
        this.features = this.initializeFeatures();
    }
    
    private detectEnvironment(): 'web' | 'desktop' {
        // Handle navigator migration
        if (typeof process === 'object' && process.versions?.node) {
            // Desktop environment
            this.handleNavigatorMigration();
            return 'desktop';
        }
        return 'web';
    }
    
    private handleNavigatorMigration() {
        // Check if navigator is accessed (for migration)
        const navigatorPolyfillEnabled = vscode.workspace
            .getConfiguration('extensions')
            .get('supportNodeGlobalNavigator', false);
            
        if (!navigatorPolyfillEnabled && typeof navigator === 'object') {
            console.warn('PendingMigrationError: navigator access detected in Node.js environment');
            // Log telemetry for migration tracking
        }
    }
    
    private initializeFeatures(): Map<string, boolean> {
        const features = new Map();
        
        if (this.environmentType === 'desktop') {
            features.set('fileSystem', true);
            features.set('childProcess', true);
            features.set('mcpServers', true);
        } else {
            features.set('webWorkers', true);
            features.set('indexedDB', true);
            features.set('limitedMcp', true);
        }
        
        return features;
    }
}
```

### 3.5 Advanced Features and Integration

#### MCP Server Management

- **Dynamic Discovery:** Extensions can dynamically discover and register MCP servers
- **Lifecycle Management:** Proper startup, shutdown, and error handling for MCP servers
- **Authentication Integration:** Secure token management and authorization server configuration
- **Resource Optimization:** Efficient resource usage and server pooling

#### Security Enhancements

- **Comprehensive Secret Detection:** Advanced pattern matching for various secret types
- **Pre-publish Validation:** Automated security checks before extension publication
- **Secure Configuration Patterns:** Best practices for handling sensitive data
- **Audit Trail:** Logging and monitoring of security-related extension activities

#### Cross-Platform Compatibility

- **Environment Abstraction:** Unified APIs that work across web and desktop
- **Feature Detection:** Runtime capability detection for conditional functionality
- **Graceful Degradation:** Fallback strategies for unsupported features
- **Performance Optimization:** Environment-specific optimizations

## 4. Troubleshooting & FAQ

### Common Issues

- **Secret Scanning False Positives:** Review detected secrets and use bypass flags for legitimate cases
- **MCP Server Connection Failures:** Check server configuration, permissions, and network connectivity
- **Navigator Migration Errors:** Update environment detection logic to use process.versions.node
- **Cross-Platform Compatibility:** Test extensions on both web and desktop environments

### How to Disable

- **Bypass Secret Scanning:** Use `--allow-package-secrets` or `--allow-package-env-file` flags
- **Disable Navigator Polyfill:** Set `extensions.supportNodeGlobalNavigator` to true
- **Skip MCP Integration:** Remove MCP server registrations from extension
- **Revert Environment Detection:** Use traditional environment detection methods

### Edge Cases

- **Complex Secret Patterns:** Custom secret formats may not be detected automatically
- **MCP Server Dependencies:** External dependencies may affect server availability
- **Environment Transitions:** Extensions running in mixed environments (e.g., remote development)
- **Legacy Code Migration:** Existing extensions may need significant updates for compatibility

### FAQ

**Q: How do I handle legitimate secrets in my extension?**
A: Use environment variables, VS Code configuration, or secure storage APIs instead of hardcoding secrets in source files.

**Q: Can I create MCP servers that work in both web and desktop environments?**
A: Yes, but you may need to implement different server strategies for each environment based on available APIs.

**Q: What happens if my extension fails the secret scan?**
A: VSCE will prevent packaging until secrets are addressed or explicitly bypassed with appropriate flags.

**Q: How do I migrate from navigator-based environment detection?**
A: Replace `typeof navigator === 'object'` checks with `typeof process === 'object' && process.versions.node` for Node.js detection.

## 5. Additional Resources

- **MCP Extension Guide:** [MCP Extension Development](https://code.visualstudio.com/api/extension-guides/mcp)
- **MCP Extension Sample:** [GitHub Extension Sample](https://github.com/microsoft/vscode-extension-samples/blob/main/mcp-extension-sample)
- **Extension API:** [VS Code Extension API](https://code.visualstudio.com/api)
- **VSCE Documentation:** [Publishing Extensions](https://code.visualstudio.com/api/working-with-extensions/publishing-extension)
- **Web Extensions:** [Web Extension Development](https://code.visualstudio.com/api/extension-guides/web-extensions)
- **Related Features:** MCP Support, Authentication Providers, Security Enhancements

## 6. Revision Log

| Date        | Author    | Change Summary                       |
|-------------|-----------|--------------------------------------|
| 2025-07-28  | Assistant | Initial micro-training for Extension Authoring enhancements |
