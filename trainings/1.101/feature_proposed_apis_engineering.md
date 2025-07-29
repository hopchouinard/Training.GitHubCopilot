---
feature: "Proposed APIs & Engineering - Authentication Providers, Electron 35, ESM Adoption"
release: "1.101"
prerequisites:
  - "Extension development experience with VS Code API"
  - "Understanding of OAuth and authentication protocols"
  - "Knowledge of JavaScript/TypeScript module systems"
  - "Familiarity with Node.js and modern web technologies"
audience: "Extension Developers, Platform Engineers, API Designers, DevTools Architects"
---

# 🚀 Feature Training: `Proposed APIs & Engineering - Authentication Providers, Electron 35, ESM Adoption` in VS Code `1.101`

## 1. Overview

- **Feature Name:** `Proposed APIs & Engineering - Authentication Providers, Electron 35, ESM Adoption`
- **Release Version:** `1.101`
- **Feature Type:** `Platform Enhancement, API Evolution, Runtime Upgrade`
- **Summary:**  
  Advanced platform improvements including proposed Authentication Provider APIs with authorization server support for MCP integration, Electron 35 runtime upgrade with Chromium 134 and Node.js 22, and real-world ESM adoption patterns for modern JavaScript module support in extensions.

## 2. Why It Matters

- **Core Problem Solved:** Enables standardized authentication integration for AI agents, provides modern runtime capabilities, and supports contemporary JavaScript development patterns in VS Code extensions.
- **Target Users:** Extension developers building authentication-aware extensions, platform engineers requiring modern runtime features, and teams adopting modern JavaScript/TypeScript development practices.
- **Context:** As VS Code evolves to support AI integration and modern web technologies, these foundational improvements enable more sophisticated and secure extension development.

## 3. Feature Details

### 3.1 Prerequisites

- Required VS Code version: `1.101+`
- Extension development experience with proposed APIs
- Understanding of OAuth 2.0 and authentication flows
- Knowledge of JavaScript ES modules and modern bundling
- Familiarity with Node.js runtime and Electron platform

### 3.2 How to Enable/Access

- **Proposed APIs:** Enable via extension manifest and API proposal adoption
- **Authentication Providers:** Implement via `vscode.authentication` API
- **Electron 35 Features:** Automatically available in VS Code 1.101+
- **ESM Support:** Configure via bundler and extension packaging setup

### 3.3 Step-by-Step Usage

#### 3.3.1 Authentication Providers with Authorization Server Support

**API Proposal Overview:**

- Extensions can declare supported authorization servers for MCP integration
- Dynamic authentication provider creation based on authorization server URLs
- Enhanced security and standardization for AI agent authentication

**Basic Implementation:**

```typescript
// package.json - Declare authorization server support
{
  "contributes": {
    "authentication": [
      {
        "label": "GitHub",
        "id": "github",
        "authorizationServerGlobs": [
          "https://github.com/login/oauth"
        ]
      }
    ]
  }
}
```

**Advanced Authentication Provider:**

```typescript
// authentication-provider.ts
import * as vscode from 'vscode';

export class CustomAuthProvider implements vscode.AuthenticationProvider {
    private _onDidChangeSessions = new vscode.EventEmitter<vscode.AuthenticationProviderAuthenticationSessionsChangeEvent>();
    readonly onDidChangeSessions = this._onDidChangeSessions.event;

    async getSessions(scopes?: readonly string[], options?: vscode.AuthenticationProviderSessionOptions): Promise<readonly vscode.AuthenticationSession[]> {
        // Handle authorization server specific logic
        const authServer = options?.authorizationServer;
        if (authServer) {
            console.log(`Authenticating with server: ${authServer}`);
            // Server-specific authentication logic
        }
        
        // Return existing sessions
        return this.retrieveStoredSessions(scopes);
    }

    async createSession(scopes: readonly string[], options?: vscode.AuthenticationProviderSessionOptions): Promise<vscode.AuthenticationSession> {
        const authServer = options?.authorizationServer;
        
        // Construct authorization URL with server-specific parameters
        const authUrl = this.buildAuthorizationUrl(scopes, authServer);
        
        // Handle OAuth flow
        const session = await this.performOAuthFlow(authUrl, scopes);
        
        this._onDidChangeSessions.fire({ 
            added: [session], 
            removed: [], 
            changed: [] 
        });
        
        return session;
    }

    async removeSession(sessionId: string): Promise<void> {
        // Remove session implementation
        const session = await this.findSession(sessionId);
        if (session) {
            await this.revokeSession(session);
            this._onDidChangeSessions.fire({ 
                added: [], 
                removed: [session], 
                changed: [] 
            });
        }
    }

    private buildAuthorizationUrl(scopes: readonly string[], authServer?: vscode.Uri): string {
        if (authServer) {
            // Use provided authorization server
            return `${authServer.toString()}?scope=${scopes.join('%20')}&client_id=${this.clientId}`;
        }
        
        // Fall back to default authorization server
        return `https://default-auth.example.com/oauth?scope=${scopes.join('%20')}`;
    }
}
```

**Registration with Authorization Server Support:**

```typescript
// extension.ts
export function activate(context: vscode.ExtensionContext) {
    const authProvider = new CustomAuthProvider();
    
    // Register with authorization server support
    const registration = vscode.authentication.registerAuthenticationProvider(
        'custom-auth',
        'Custom Authentication',
        authProvider,
        {
            supportsMultipleAccounts: true,
            supportedAuthorizationServers: [
                vscode.Uri.parse('https://auth.example.com/oauth'),
                vscode.Uri.parse('https://auth.example.com/*/v2.0') // Wildcard support
            ]
        }
    );
    
    context.subscriptions.push(registration);
}
```

#### 3.3.2 MCP Integration with Dynamic Authentication

**MCP Server Authentication Setup:**

```typescript
// mcp-auth-integration.ts
export class McpAuthIntegration {
    async setupMcpServerAuth(serverConfig: any) {
        const authServerUrl = serverConfig.authorizationServer;
        
        if (authServerUrl) {
            // Request authentication using specific authorization server
            const session = await vscode.authentication.getSession(
                'custom-auth',
                ['read', 'write'],
                {
                    createIfNone: true,
                    authorizationServer: vscode.Uri.parse(authServerUrl)
                }
            );
            
            // Use session for MCP server authentication
            return this.configureMcpServer(serverConfig, session);
        }
        
        throw new Error('No authorization server specified for MCP server');
    }
    
    private async configureMcpServer(config: any, session: vscode.AuthenticationSession) {
        return {
            ...config,
            headers: {
                'Authorization': `Bearer ${session.accessToken}`
            }
        };
    }
}
```

#### 3.3.3 Electron 35 Runtime Features

**Node.js 22 Feature Utilization:**

```typescript
// modern-runtime-features.ts
export class ModernRuntimeFeatures {
    // Utilize Node.js 22 features
    async useModernNodeFeatures() {
        // Node.js 22 navigator global object support
        if (typeof navigator !== 'undefined') {
            console.log('Navigator available in Node.js:', navigator.userAgent);
        }
        
        // Enhanced performance features
        const perfObserver = new PerformanceObserver((list) => {
            const entries = list.getEntries();
            console.log('Performance entries:', entries);
        });
        
        perfObserver.observe({ entryTypes: ['measure'] });
    }
    
    // Chromium 134 web platform features
    useChromiumFeatures() {
        // Access to latest web APIs in webview contexts
        if (typeof crypto !== 'undefined' && crypto.subtle) {
            return this.useWebCrypto();
        }
        
        return null;
    }
    
    private async useWebCrypto() {
        // Utilize modern Web Crypto API
        const key = await crypto.subtle.generateKey(
            {
                name: 'AES-GCM',
                length: 256
            },
            true,
            ['encrypt', 'decrypt']
        );
        
        return key;
    }
}
```

#### 3.3.4 ESM Adoption in Extensions

**Dual-Target Extension Configuration:**

```javascript
// esbuild.mjs - Inspired by GitHub Issue Notebooks extension
import esbuild from 'esbuild';

const production = process.argv.includes('--production');
const watch = process.argv.includes('--watch');

/**
 * @type {import('esbuild').Plugin}
 */
const esbuildProblemMatcherPlugin = {
    name: 'esbuild-problem-matcher',
    setup(build) {
        build.onStart(() => {
            console.log('[watch] build started');
        });
        build.onEnd((result) => {
            result.errors.forEach(({ text, location }) => {
                console.error(`✘ [ERROR] ${text}`);
                console.error(`    ${location.file}:${location.line}:${location.column}:`);
            });
            console.log('[watch] build finished');
        });
    },
};

async function main() {
    const ctx = await esbuild.context({
        entryPoints: [
            'src/extension.ts'
        ],
        bundle: true,
        format: 'esm', // Use ESM format for Node.js extension host
        minify: production,
        sourcemap: !production,
        sourcesContent: false,
        platform: 'node',
        outfile: 'out/extension.js',
        external: ['vscode'],
        logLevel: 'silent',
        plugins: [
            esbuildProblemMatcherPlugin,
        ],
    });

    // Build for web worker extension host (still requires CommonJS)
    const webCtx = await esbuild.context({
        entryPoints: [
            'src/extension.ts'
        ],
        bundle: true,
        format: 'cjs', // CommonJS for web worker compatibility
        minify: production,
        sourcemap: !production,
        sourcesContent: false,
        platform: 'browser',
        outfile: 'out/extension.web.js',
        external: ['vscode'],
        logLevel: 'silent',
        plugins: [
            esbuildProblemMatcherPlugin,
        ],
    });

    if (watch) {
        await Promise.all([ctx.watch(), webCtx.watch()]);
    } else {
        await Promise.all([ctx.rebuild(), webCtx.rebuild()]);
        await Promise.all([ctx.dispose(), webCtx.dispose()]);
    }
}

main().catch(e => {
    console.error(e);
    process.exit(1);
});
```

**Package.json Configuration for ESM:**

```json
{
  "main": "./out/extension.js",
  "browser": "./out/extension.web.js",
  "type": "module",
  "engines": {
    "vscode": "^1.101.0"
  },
  "contributes": {
    "configuration": {
      "type": "object",
      "title": "ESM Extension",
      "properties": {
        "esmExtension.enableModernFeatures": {
          "type": "boolean",
          "default": true,
          "description": "Enable modern ESM features"
        }
      }
    }
  }
}
```

**ESM Extension Implementation:**

```typescript
// extension.ts using ESM
import * as vscode from 'vscode';
import { ModernRuntimeFeatures } from './runtime-features.js';
import { CustomAuthProvider } from './auth-provider.js';

export async function activate(context: vscode.ExtensionContext) {
    // ESM import syntax works in Node.js extension host
    const { default: someModule } = await import('./dynamic-module.js');
    
    // Initialize modern runtime features
    const runtimeFeatures = new ModernRuntimeFeatures();
    await runtimeFeatures.useModernNodeFeatures();
    
    // Setup authentication provider with ESM patterns
    const authProvider = new CustomAuthProvider();
    const authRegistration = vscode.authentication.registerAuthenticationProvider(
        'esm-auth',
        'ESM Authentication',
        authProvider
    );
    
    context.subscriptions.push(authRegistration);
    
    // Register command using dynamic imports
    const commandRegistration = vscode.commands.registerCommand(
        'esmExtension.dynamicImport',
        async () => {
            const { performAction } = await import('./action-handler.js');
            return performAction();
        }
    );
    
    context.subscriptions.push(commandRegistration);
}

export function deactivate() {
    // Cleanup code
}
```

### 3.4 Example(s)

#### Simple Example: Basic Authentication Provider

```typescript
// Simple auth provider for API service
export class ApiAuthProvider implements vscode.AuthenticationProvider {
    async getSessions(): Promise<readonly vscode.AuthenticationSession[]> {
        // Return stored sessions
        return [];
    }
    
    async createSession(scopes: readonly string[]): Promise<vscode.AuthenticationSession> {
        // Simple OAuth flow
        return {
            id: 'session-1',
            accessToken: 'token-123',
            account: { label: 'User', id: 'user-1' },
            scopes
        };
    }
    
    async removeSession(): Promise<void> {
        // Remove session
    }
}
```

#### Advanced Example: Multi-Server Authentication

```typescript
// Advanced auth provider supporting multiple authorization servers
export class MultiServerAuthProvider implements vscode.AuthenticationProvider {
    private serverConfigs = new Map<string, ServerConfig>();
    
    constructor() {
        // Initialize known server configurations
        this.serverConfigs.set('github.com', {
            authUrl: 'https://github.com/login/oauth',
            tokenUrl: 'https://github.com/login/oauth/access_token',
            clientId: 'github-client-id'
        });
        
        this.serverConfigs.set('gitlab.com', {
            authUrl: 'https://gitlab.com/oauth/authorize',
            tokenUrl: 'https://gitlab.com/oauth/token',
            clientId: 'gitlab-client-id'
        });
    }
    
    async createSession(scopes: readonly string[], options?: vscode.AuthenticationProviderSessionOptions): Promise<vscode.AuthenticationSession> {
        const authServer = options?.authorizationServer;
        const serverConfig = this.getServerConfig(authServer);
        
        if (!serverConfig) {
            throw new Error(`Unsupported authorization server: ${authServer}`);
        }
        
        return this.performOAuthFlow(serverConfig, scopes);
    }
    
    private getServerConfig(authServer?: vscode.Uri): ServerConfig | undefined {
        if (!authServer) return undefined;
        
        const hostname = authServer.authority;
        return this.serverConfigs.get(hostname);
    }
}
```

#### Complex Example: ESM Extension with Modern Features

```typescript
// Complex ESM extension utilizing Electron 35 features
export class ModernExtension {
    private authProvider?: CustomAuthProvider;
    private runtimeFeatures?: ModernRuntimeFeatures;
    
    async activate(context: vscode.ExtensionContext) {
        // Dynamic ESM imports based on environment
        if (this.isNodeJsHost()) {
            const { NodeJsAuthProvider } = await import('./providers/nodejs-auth.js');
            this.authProvider = new NodeJsAuthProvider();
        } else {
            const { WebAuthProvider } = await import('./providers/web-auth.js');
            this.authProvider = new WebAuthProvider();
        }
        
        // Register authentication provider with multiple server support
        const authRegistration = vscode.authentication.registerAuthenticationProvider(
            'modern-auth',
            'Modern Authentication',
            this.authProvider,
            {
                supportsMultipleAccounts: true,
                supportedAuthorizationServers: [
                    vscode.Uri.parse('https://auth.example.com/oauth'),
                    vscode.Uri.parse('https://api.service.com/*/auth')
                ]
            }
        );
        
        // Initialize Electron 35 runtime features
        this.runtimeFeatures = new ModernRuntimeFeatures();
        await this.runtimeFeatures.useModernNodeFeatures();
        
        context.subscriptions.push(authRegistration);
    }
    
    private isNodeJsHost(): boolean {
        return typeof process === 'object' && !!process.versions?.node;
    }
}
```

### 3.5 Advanced Features and Integration

#### Authentication Provider Enhancements

- **Dynamic Server Discovery:** Runtime detection and configuration of authorization servers
- **Multi-Tenant Support:** Handle multiple tenant scenarios with wildcard URL patterns
- **Session Management:** Advanced session lifecycle management and token refresh
- **Security Features:** Enhanced security measures for token storage and transmission

#### Runtime Platform Improvements

- **Performance Optimizations:** Leverage Electron 35 and Node.js 22 performance improvements
- **Modern Web APIs:** Access to latest Chromium 134 web platform features
- **Memory Management:** Improved garbage collection and memory usage patterns
- **Developer Experience:** Enhanced debugging and development tool integration

#### ESM Ecosystem Integration

- **Tree Shaking:** Better dead code elimination with ESM static analysis
- **Dynamic Imports:** Runtime module loading for performance optimization
- **Interoperability:** Seamless integration between ESM and CommonJS modules
- **Bundling Strategies:** Advanced bundling configurations for dual-target extensions

## 4. Troubleshooting & FAQ

### Common Issues

- **Authorization Server Mismatches:** Ensure URL patterns match exactly with registered globs
- **ESM/CommonJS Conflicts:** Use appropriate bundling configuration for target environments
- **Runtime Feature Availability:** Check for feature availability before usage in different hosts
- **Authentication Flow Errors:** Implement proper error handling for OAuth flows

### How to Disable

- **Revert to Stable APIs:** Remove proposed API usage and use stable authentication APIs
- **CommonJS Fallback:** Configure bundler to output CommonJS for broader compatibility
- **Legacy Runtime Features:** Avoid Node.js 22 specific features for older runtime compatibility
- **Simple Authentication:** Use basic authentication patterns without authorization server support

### Edge Cases

- **Mixed Environment Extensions:** Handle extensions running in both Node.js and web worker hosts
- **Authorization Server Migration:** Handle scenarios where authorization servers change URLs
- **ESM Loading Failures:** Graceful fallback when dynamic imports fail
- **Performance Implications:** Monitor impact of modern features on extension startup time

### FAQ

**Q: Can I use proposed APIs in published extensions?**
A: Proposed APIs are experimental and may change. Use with caution and be prepared to update code.

**Q: Do ESM extensions work in web environments?**
A: Currently, ESM support is primarily for Node.js extension host. Web worker host still requires CommonJS.

**Q: How do I migrate from older authentication patterns?**
A: Gradually adopt new authorization server patterns while maintaining backward compatibility.

**Q: What are the benefits of Electron 35 upgrade?**
A: Improved performance, security updates, access to modern web APIs, and Node.js 22 features.

## 5. Additional Resources

- **Proposed API Repository:** [VS Code Proposed APIs](https://github.com/microsoft/vscode/tree/main/src/vscode-dts)
- **Authentication Provider Issue:** [GitHub Discussion](https://github.com/microsoft/vscode/issues/248775)
- **ESM Extension Sample:** [GitHub Issue Notebooks](https://github.com/microsoft/vscode-github-issue-notebooks)
- **Electron 35 Release Notes:** [Electron Platform Updates](https://www.electronjs.org/blog/electron-35-0)
- **Node.js 22 Features:** [Node.js Release Notes](https://nodejs.org/en/blog/release/v22.0.0)
- **Related Features:** MCP Support, Extension Authoring, Security Enhancements

## 6. Revision Log

| Date        | Author    | Change Summary                       |
|-------------|-----------|--------------------------------------|
| 2025-07-28  | Assistant | Initial micro-training for Proposed APIs and Engineering enhancements |
