[![Release](https://img.shields.io/github/v/release/Common-ka/cursor-unity-rules)](https://github.com/Common-ka/cursor-unity-rules/releases)

## 📋 Description

Production-ready `.cursor/rules` configuration for Unity 2022+ projects. Modern AI rules system for Cursor IDE (2025) using the new `.mdc` format instead of the deprecated `.cursorrules`.

This ruleset provides comprehensive guidelines for Unity development, including:
- **TEngine Framework** architecture and best practices
- Modern C# coding standards (Unity 2022 / C# 12.0)
- Performance optimization patterns
- UI development with UGUI and TEngine UIModule
- Input System integration
- Testing frameworks
- DOTS/ECS patterns
- Networking with Netcode for GameObjects

## 🚀 Quick Start

### Requirements

- Unity 2022 or higher
- Cursor IDE
- .NET SDK for C# development

### Installation

1. Clone the repository into your Unity project root:

```bash
cd YourUnityProject
git clone https://github.com/Common-ka/cursor-unity-rules.git
```

2. Or manually copy the `.cursor/` folder to your project root

3. Copy `.vscode/settings.json` to your project (if exists):
```bash
cp cursor-unity-rules/.vscode/settings.json YourUnityProject/.vscode/
```

4. Open your project in Cursor IDE

5. Rules will automatically apply when working with code

## 📚 Rules Overview

The rules are organized into the following files:

### Always Applied Rules

These rules are always active and apply to all code:

- **`code-organization.mdc`** - Project structure, naming conventions, assembly definitions, folder organization
- **`unity-core.mdc`** - Core Unity rules: MonoBehaviour lifecycle, serialization, C# naming conventions, modern C# features
- **`unity-architecture.mdc`** - TEngine Framework architecture: module system, Procedure FSM, hot-update support, resource management (YooAsset), event system

### Context-Specific Rules

These rules apply automatically based on file patterns or can be manually requested:

- **`unity-ui.mdc`** - UGUI with TEngine UIModule (applies to `**/UI*.cs`, `**/*UI.cs`, `**/UIWindow*.cs`, `**/UIWidget*.cs`)
  - UIWindow and UIWidget patterns
  - UI lifecycle management
  - Event registration
  - Component binding

- **`unity-input.mdc`** - New Input System guidelines (applies to `**/Input*.cs`, `**/Player*.cs`, `**/*Controller*.cs`)
  - Input Actions setup
  - PlayerInput component
  - Generated C# class approach
  - Input rebinding
  - TEngine integration

- **`unity-performance.mdc`** - Performance optimization patterns
  - Update/FixedUpdate/LateUpdate usage
  - Object pooling (TEngine ObjectPoolModule)
  - Resource management (YooAsset)
  - Memory management
  - Async programming (UniTask)

- **`unity-testing.mdc`** - Unity Test Framework guidelines
  - Edit Mode tests
  - Play Mode tests
  - AAA pattern (Arrange, Act, Assert)
  - TEngine module testing

- **`unity-networking.mdc`** - Netcode for GameObjects
  - NetworkBehaviour patterns
  - NetworkVariable usage
  - Server/Client RPCs

- **`unity-ecs.mdc`** - DOTS/ECS patterns
  - ISystem vs SystemBase
  - IJobEntity patterns
  - Burst compilation
  - Component and System structure

## 🎯 Key Features

### TEngine Framework Support

This ruleset is optimized for projects using **TEngine Framework**, including:

- **Module System**: Access via `ModuleSystem.GetModule<T>()` (main domain) or `GameModule.X` (hot update domain)
- **Procedure System**: FSM-based state management
- **Hot Update**: HybridCLR integration patterns
- **Resource Management**: YooAsset integration (forbidden to use `Resources.Load()`)
- **UI Module**: TEngine UIModule patterns for UIWindow/UIWidget
- **Object Pooling**: TEngine ObjectPoolModule usage
- **Event System**: GameEvent patterns

### Modern C# Standards

- **Naming Conventions**: Microsoft C# style (`_camelCase` for private fields, `PascalCase` for public members)
- **Modern Features**: Unity 2022 Awaitable, pattern matching, null-conditional operators
- **Best Practices**: Expression-bodied members, string interpolation, readonly structs

### Performance Optimization

- Zero-allocation patterns
- Object pooling
- Memory pool usage
- Async/await with UniTask (instead of Coroutines)
- Component caching

## 📖 Usage

### Automatic Application

Rules are automatically applied based on:
- **File patterns** (globs) - e.g., UI rules apply to `**/UI*.cs` files
- **Always apply** flag - Core rules are always active

### Manual Request

You can manually request specific rules by mentioning them:
- "Follow unity-ecs rules"
- "Apply unity-performance guidelines"
- "Use unity-testing patterns"

### Rule Priority

1. **Always Applied Rules** - Active for all code
2. **Context-Specific Rules** - Active based on file patterns
3. **Manually Requested Rules** - Active when explicitly mentioned

## 🔧 Customization

To customize rules for your project:

1. Edit the `.mdc` files in `.cursor/rules/` directory
2. Modify `alwaysApply` flag to change automatic application
3. Adjust `globs` patterns to change file matching
4. Add project-specific rules in new `.mdc` files

## 📄 License

MIT License - see [LICENSE](LICENSE)

