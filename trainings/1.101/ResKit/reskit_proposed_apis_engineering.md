---
feature: "Proposed APIs & Engineering - Authentication Providers, Electron 35, ESM Adoption"
release: "1.101"
resource_type: "Both"
audience: "Extension Developers, Platform Engineers, API Designers"
prerequisites:
  - "Extension development experience with VS Code API"
  - "Understanding of OAuth and authentication protocols"
  - "Knowledge of JavaScript/TypeScript module systems"
  - "Familiarity with Node.js and modern web technologies"
summary: |
  Essential exercises and demos for VS Code's Proposed APIs & Engineering enhancements in version 1.101, covering Authentication Provider APIs with authorization server support, Electron 35 runtime upgrades, and ESM adoption patterns for modern extension development.
---

# ⚙️ Resource Kit: `Proposed APIs & Engineering - Authentication Providers, Electron 35, ESM Adoption` — `Exercise + Demo`

## Directory Structure

```
proposed-apis-engineering-kit/
├── README.md
├── exercise-1-authentication-providers/
│   ├── instructions.md
│   ├── solution/
│   │   ├── auth-extension/
│   │   │   ├── package.json
│   │   │   ├── src/
│   │   │   │   ├── extension.ts
│   │   │   │   ├── auth-provider.ts
│   │   │   │   └── mcp-integration.ts
│   │   │   └── README.md
│   │   ├── server-configs/
│   │   │   ├── github-auth.json
│   │   │   ├── oauth2-generic.json
│   │   │   └── custom-server.json
│   │   └── integration-examples/
│   │       ├── mcp-auth-flow.ts
│   │       ├── session-management.ts
│   │       └── multi-server-auth.ts
│   ├── starter/
│   │   ├── basic-auth/
│   │   │   ├── package.json
│   │   │   └── src/
│   │   │       └── extension.ts
│   │   └── auth-templates/
│   │       └── provider-template.ts
│   └── assets/
│       ├── auth-flow-demo.gif
│       └── oauth-integration.png
├── exercise-2-esm-adoption/
│   ├── instructions.md
│   ├── solution/
│   │   ├── esm-extension/
│   │   │   ├── package.json
│   │   │   ├── webpack.config.js
│   │   │   ├── src/
│   │   │   │   ├── extension.ts
│   │   │   │   ├── modules/
│   │   │   │   │   ├── utils.mjs
│   │   │   │   │   └── helpers.mjs
│   │   │   │   └── legacy/
│   │   │   │       └── commonjs-compat.js
│   │   │   └── tsconfig.json
│   │   ├── migration-examples/
│   │   │   ├── commonjs-to-esm.md
│   │   │   ├── bundler-config.js
│   │   │   └── import-patterns.ts
│   │   └── compatibility-tests/
│   │       ├── esm-test.mjs
│   │       ├── commonjs-test.js
│   │       └── mixed-modules.test.ts
│   ├── starter/
│   │   └── legacy-extension/
│   │       ├── package.json
│   │       └── src/
│   │           └── extension.js
│   └── assets/
│       ├── esm-migration-demo.gif
│       └── module-system-comparison.png
├── demo-1-modern-extension-platform/
│   ├── walkthrough.md
│   └── src/
│       ├── platform-showcase/
│       │   ├── package.json
│       │   ├── src/
│       │   │   ├── extension.ts
│       │   │   ├── features/
│       │   │   │   ├── auth-manager.ts
│       │   │   │   ├── electron-features.ts
│       │   │   │   └── esm-loader.ts
│       │   │   └── utils/
│       │   │       ├── platform-detection.ts
│       │   │       └── runtime-info.ts
│       │   ├── webpack.config.js
│       │   └── README.md
│       ├── runtime-tests/
│       │   ├── electron-35-features.test.ts
│       │   ├── node-22-compatibility.test.ts
│       │   └── chromium-134-apis.test.ts
│       └── deployment-configs/
│           ├── modern-bundling.config.js
│           ├── legacy-support.config.js
│           └── hybrid-deployment.json
│   └── assets/
│       ├── platform-showcase-demo.gif
│       └── runtime-architecture.png
└── demo-2-authentication-workflow/
    ├── walkthrough.md
    └── src/
        ├── auth-workflow-extension/
        │   ├── package.json
        │   ├── src/
        │   │   ├── extension.ts
        │   │   ├── providers/
        │   │   │   ├── github-auth.ts
        │   │   │   ├── oauth2-provider.ts
        │   │   │   └── custom-auth.ts
        │   │   ├── integrations/
        │   │   │   ├── mcp-client.ts
        │   │   │   ├── ai-service-auth.ts
        │   │   │   └── multi-tenant-auth.ts
        │   │   └── ui/
        │   │       ├── auth-panel.ts
        │   │       └── session-manager.ts
        │   └── README.md
        ├── server-implementations/
        │   ├── mock-oauth-server.js
        │   ├── github-integration.ts
        │   └── custom-auth-server.ts
        └── test-scenarios/
            ├── auth-flow-tests.ts
            ├── session-management.test.ts
            └── multi-provider.test.ts
    └── assets/
        ├── auth-workflow-demo.gif
        └── multi-provider-architecture.png
```

## File Listings and Contents

For each file in the structure above, the complete contents are defined here to enable automation agents to generate the full directory and file tree as specified.

---

### proposed-apis-engineering-kit/README.md

```
# Proposed APIs & Engineering - Authentication Providers, Electron 35, ESM Adoption — Exercise + Demo Resource Kit

Welcome! This essential resource kit contains:
- **Core Exercises** for key proposed APIs and platform improvements
- **Modern Development Demos** showcasing platform upgrades and API adoption
- **Migration Guidance** for adopting modern JavaScript patterns and authentication flows

## What You'll Learn

1. **Authentication Providers** - OAuth integration with authorization server support
2. **ESM Adoption** - Modern JavaScript module system migration patterns
3. **Platform Showcase** - Electron 35 and Node.js 22 runtime capabilities
4. **Authentication Workflows** - Complete multi-provider authentication integration

## Features Covered

- Authentication Provider APIs with authorization server support for MCP
- Electron 35 runtime upgrade (Chromium 134, Node.js 22)
- ESM (ECMAScript Modules) adoption patterns and migration strategies
- Modern bundling and packaging for VS Code extensions
- OAuth 2.0 integration patterns for AI service authentication

## Prerequisites

- VS Code 1.101+
- Extension development experience with VS Code API
- Understanding of OAuth and authentication protocols
- Knowledge of JavaScript/TypeScript module systems
- Familiarity with Node.js and modern web technologies

## Getting Started

1. **Update Development Environment**: Ensure latest tools support ESM and modern runtimes
2. **Review Proposed APIs**: Understand authentication provider proposal requirements
3. **Start with Exercise 1**: Learn authentication provider implementation
4. **Progress through exercises**: Build expertise with ESM migration and modern patterns
5. **Explore demos**: See complete modern extension development workflows

## Platform Improvements

### Authentication Providers
- **Authorization Server Support**: Declare supported OAuth servers for MCP integration
- **Dynamic Provider Creation**: Create providers based on authorization server URLs
- **Enhanced Security**: Standardized authentication flows for AI agents
- **Multi-Tenant Support**: Handle multiple authentication contexts

### Electron 35 Runtime
- **Chromium 134**: Latest web platform features and security improvements
- **Node.js 22**: Modern JavaScript runtime with enhanced performance
- **Security Updates**: Latest security patches and vulnerability fixes
- **API Improvements**: Enhanced platform integration and capabilities

### ESM Adoption
- **Modern Module System**: ES modules support in extensions
- **Tree Shaking**: Better bundle optimization with ES modules
- **Dynamic Imports**: Lazy loading and code splitting capabilities
- **Interoperability**: Seamless CommonJS and ESM integration

### Migration Benefits
- **Performance**: Improved startup time and memory usage
- **Security**: Enhanced security with modern runtime features
- **Maintainability**: Modern development patterns and tooling
- **Future-Proofing**: Alignment with web platform evolution

## Development Patterns

### Authentication Integration
```typescript
// Modern authentication provider implementation
export class ModernAuthProvider implements vscode.AuthenticationProvider {
  async getSessions(scopes?: readonly string[], options?: AuthOptions) {
    const authServer = options?.authorizationServer;
    return this.handleServerSpecificAuth(authServer, scopes);
  }
}
```

### ESM Module Loading

```typescript
// Dynamic ESM imports for modern extensions
const { ModernFeature } = await import('./features/modern-feature.mjs');
const feature = new ModernFeature();
```

### Platform Detection

```typescript
// Detect platform capabilities
const platformInfo = {
  electronVersion: process.versions.electron,
  nodeVersion: process.versions.node,
  chromiumVersion: process.versions.chrome
};
```

## Common Workflows

### Authentication Setup

- **Provider Registration**: Register authentication providers with authorization server support
- **Session Management**: Handle authentication sessions and token refresh
- **MCP Integration**: Connect authenticated providers with MCP servers
- **Security Controls**: Implement proper credential storage and access controls

### Module Migration

- **CommonJS to ESM**: Convert existing CommonJS modules to ES modules
- **Bundle Configuration**: Update webpack/bundler configs for ESM support
- **Import Optimization**: Implement tree shaking and dynamic imports
- **Compatibility Testing**: Ensure backward compatibility during migration

### Platform Utilization

- **Runtime Features**: Leverage new Node.js 22 and Chromium 134 capabilities
- **Performance Optimization**: Use platform improvements for better performance
- **Security Enhancement**: Implement latest security features and practices
- **API Adoption**: Adopt new platform APIs and deprecate legacy patterns

## Keyboard Shortcuts

### Extension Development

- **Debug Extension**: `F5` (Launch extension development host)
- **Reload Extension**: `Ctrl+R` (Reload extension in development host)
- **View Logs**: `Ctrl+Shift+U` → Select "Extension Host" output

### Authentication Testing

- **Test Auth Flow**: Custom commands defined in extension
- **Clear Sessions**: Available through Command Palette
- **View Auth Status**: Status bar indicators and panels

### Module Development

- **Build Extension**: `Ctrl+Shift+P` → "Tasks: Run Build Task"
- **Watch Mode**: `Ctrl+Shift+P` → "Tasks: Run Watch Task"
- **Bundle Analysis**: Custom tasks for bundle size analysis

## Migration Checklist

### ESM Migration

- [ ] Update package.json to specify module type
- [ ] Convert require() calls to import statements
- [ ] Update bundler configuration for ESM
- [ ] Test compatibility with existing dependencies
- [ ] Verify tree shaking and bundle optimization

### Authentication Provider

- [ ] Implement authentication provider interface
- [ ] Declare authorization server support
- [ ] Handle session lifecycle and token refresh
- [ ] Test with MCP server integration
- [ ] Implement security best practices

### Platform Upgrade

- [ ] Test extension with Electron 35 runtime
- [ ] Verify Node.js 22 compatibility
- [ ] Update dependencies for new runtime
- [ ] Test platform-specific features
- [ ] Document runtime requirements

Happy modern extension development with enhanced platform capabilities!

```

---

### proposed-apis-engineering-kit/exercise-1-authentication-providers/instructions.md

```

# Exercise 1: Authentication Providers with Authorization Server Support

## Goal

Learn to implement VS Code Authentication Providers with authorization server support for MCP integration, including OAuth 2.0 flows and session management.

## Task

1. Create an authentication provider extension with authorization server support
2. Implement OAuth 2.0 authentication flow
3. Integrate with MCP servers requiring authentication
4. Test multi-provider authentication scenarios

## Input/Output

**Starter**: Basic authentication provider template
**Expected Outcome**: Fully functional authentication provider with MCP integration

## Steps

1. **Set Up Authentication Provider**

   ```json
   {
     "contributes": {
       "authentication": [
         {
           "label": "Custom OAuth",
           "id": "custom-oauth",
           "authorizationServerGlobs": [
             "https://auth.example.com/*",
             "https://api.github.com/login/oauth"
           ]
         }
       ]
     }
   }
   ```

   - Declare authorization server support in package.json
   - Specify OAuth server URL patterns
   - Configure provider identification

2. **Implement Authentication Provider**

   ```typescript
   export class CustomAuthProvider implements vscode.AuthenticationProvider {
     async getSessions(scopes?: readonly string[], options?: AuthOptions) {
       const authServer = options?.authorizationServer;
       return this.handleServerAuth(authServer, scopes);
     }
     
     async createSession(scopes: readonly string[], options?: AuthOptions) {
       return this.performOAuthFlow(options?.authorizationServer, scopes);
     }
   }
   ```

   - Implement required authentication provider interface
   - Handle authorization server-specific logic
   - Manage OAuth 2.0 authentication flows

3. **Integrate with MCP Servers**

   ```typescript
   // MCP server authentication integration
   const authSession = await vscode.authentication.getSession(
     'custom-oauth',
     ['read', 'write'],
     { authorizationServer: 'https://api.example.com' }
   );
   
   const mcpClient = new McpClient({
     authToken: authSession.accessToken,
     serverUrl: 'https://mcp.example.com'
   });
   ```

   - Connect authenticated sessions with MCP servers
   - Pass authentication tokens to MCP clients
   - Handle authentication failures and retries

4. **Test Authentication Workflows**
   - Test OAuth 2.0 authorization code flow
   - Verify session persistence and refresh
   - Test with multiple authorization servers
   - Validate MCP server authentication

## Tips

- Use secure token storage for authentication sessions
- Implement proper error handling for authentication failures
- Test with real OAuth providers (GitHub, Google, etc.)
- Monitor authentication logs for debugging
- Follow OAuth 2.0 security best practices

```

---

### proposed-apis-engineering-kit/exercise-2-esm-adoption/instructions.md

```

# Exercise 2: ESM Adoption and Modern Module Patterns

## Goal

Learn to migrate VS Code extensions from CommonJS to ESM (ECMAScript Modules), including bundler configuration, import patterns, and compatibility strategies.

## Task

1. Convert a CommonJS extension to use ESM
2. Configure modern bundling for ESM support
3. Implement dynamic imports and tree shaking
4. Ensure backward compatibility

## Input/Output

**Starter**: Legacy CommonJS extension
**Expected Outcome**: Modern ESM extension with optimized bundling

## Steps

1. **Update Package Configuration**

   ```json
   {
     "type": "module",
     "main": "./out/extension.mjs",
     "exports": {
       ".": {
         "import": "./out/extension.mjs",
         "require": "./out/extension.cjs"
       }
     }
   }
   ```

   - Add "type": "module" to package.json
   - Configure dual exports for compatibility
   - Update file extensions appropriately

2. **Convert Import/Export Patterns**

   ```typescript
   // Before (CommonJS)
   const vscode = require('vscode');
   module.exports = { activate, deactivate };
   
   // After (ESM)
   import * as vscode from 'vscode';
   export { activate, deactivate };
   ```

   - Replace require() with import statements
   - Convert module.exports to export statements
   - Update dynamic requires to dynamic imports

3. **Configure Modern Bundling**

   ```javascript
   // webpack.config.js for ESM
   export default {
     target: 'node',
     mode: 'production',
     experiments: {
       outputModule: true
     },
     output: {
       module: true,
       library: {
         type: 'module'
       }
     }
   };
   ```

   - Enable ESM output in webpack configuration
   - Configure tree shaking for better optimization
   - Set up development and production builds

4. **Test and Validate**
   - Verify extension functionality with ESM
   - Test dynamic imports and lazy loading
   - Validate bundle size improvements
   - Ensure compatibility across VS Code versions

## Tips

- Start with TypeScript configuration for better ESM support
- Use dynamic imports for optional features to reduce bundle size
- Test thoroughly with different VS Code versions
- Keep CommonJS compatibility for gradual migration
- Monitor bundle size and performance improvements

```

This simplified resource kit for Proposed APIs & Engineering features provides:

✅ **2 Focused Exercises** - Authentication providers and ESM adoption
✅ **2 Comprehensive Demos** - Modern platform showcase and authentication workflows
✅ **Platform Modernization** - Electron 35, Node.js 22, and ESM adoption patterns
✅ **Security Focus** - OAuth 2.0 integration with MCP authentication
✅ **Migration Guidance** - CommonJS to ESM conversion strategies

The resource kit covers the essential platform improvements while keeping complexity manageable and focused on practical implementation patterns.

This completes all the major features from VS Code 1.101! We've now created comprehensive resource kits for all 13 major feature areas, providing developers with hands-on experience across the entire release.
