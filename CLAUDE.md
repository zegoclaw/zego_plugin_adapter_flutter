# CLAUDE.md

> **Note**: This library is part of the `zego_uikits` monorepo.
> For detailed architecture documentation, see [ARCHITECTURE.md](./ARCHITECTURE.md).

This file provides guidance to Claude Code when working with code in this repository.

## Project Overview

**ZegoPluginAdapter** is an internal Flutter plugin that provides a unified interface for connecting ZegoUIKit with various optional plugins (signaling, beauty, etc.). This is a low-level library not typically used directly by developers.

## Architecture

> For comprehensive architecture details, see [ARCHITECTURE.md](./ARCHITECTURE.md).

### Purpose

The plugin adapter defines abstract interfaces (`IZegoUIKitPlugin`) that all plugins must implement:

```dart
abstract class IZegoUIKitPlugin {
  Future<void> init();
  Future<void> uninit();
  // ... lifecycle methods
}
```

### Key Concepts

- **Plugin Interface**: All plugins must implement `IZegoUIKitPlugin`
- **Plugin Core**: Plugins interact with `ZegoUIKit` through the plugin core
- **Extension Points**: New plugins can be added by implementing the interface

## Usage

This library is primarily used internally by:
- `zego_uikit` - To discover and manage plugins
- `zego_uikit_signaling_plugin` - Plugin implementation
- `zego_uikit_beauty_plugin` - Plugin implementation

## Commands

```bash
# Install dependencies
flutter pub get

# Analyze code
flutter analyze
```
