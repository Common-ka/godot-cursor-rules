
# Godot 4.4 Game Development Rules for Cursor AI

This repository contains comprehensive development rules designed to enhance your Godot 4.4 game development experience when using [Cursor AI](https://docs.cursor.com/context/rules-for-ai).

## What are Cursor Rules?

Cursor rules allow you to customize the behavior of Cursor AI to follow specific conventions and best practices for your project. As explained in the [Cursor documentation](https://docs.cursor.com/context/rules-for-ai):

> Using rules in Cursor you can control the behavior of the underlying model. You can think of it as instructions and/or a system prompt for LLMs.

## Project Structure

This repository provides rules in two formats for maximum compatibility:

### Modern Format: `.cursor/rules/` Directory
- **Recommended approach** for new projects
- Organized into focused rule files by category
- Better maintainability and organization
- Follows current Cursor best practices

### Legacy Format: `.cursorrules` File
- **Backward compatibility** for existing projects
- Single file containing all rules
- Still supported but deprecated

## How to Use

### Option 1: Modern Rules (Recommended)
1. Copy the `.cursor` folder to your Godot 4.4 project root
2. Cursor AI will automatically use the organized rule files

### Option 2: Legacy Rules
1. Download the `.cursorrules` file from this repository
2. Place it in the root directory of your Godot 4.4 project

## What's Included

### Core Development Guidelines
- Strict typing in GDScript for better error detection and IDE support
- Proper lifecycle function implementation with explicit super() calls
- @onready annotations instead of direct node references
- Composition over inheritance approach
- Signal-based loose coupling between nodes
- Godot naming conventions (PascalCase for nodes, snake_case for methods)

### Code Style Standards
- Type hints for all variables and function parameters
- Comprehensive function documentation with docstrings
- Focused methods under 30 lines
- Meaningful variable and function names
- Logical grouping of related properties and methods

### Naming Conventions
- **Files**: snake_case (e.g., `player_character.gd`, `main_menu.tscn`)
- **Classes**: PascalCase with `class_name` (e.g., `PlayerCharacter`)
- **Variables**: snake_case (e.g., `health_points`)
- **Constants**: ALL_CAPS_SNAKE_CASE (e.g., `MAX_HEALTH`)
- **Functions**: snake_case (e.g., `move_player()`)
- **Enums**: PascalCase types, ALL_CAPS values
- **Nodes**: PascalCase in scene tree (e.g., `PlayerCharacter`, `MainCamera`)
- **Signals**: snake_case in past tense (e.g., `health_depleted`, `enemy_defeated`)

### Scene Organization
- Minimal scene tree depth for better performance
- Scene inheritance for reusable components
- Proper cleanup with `queue_free()`
- Careful use of SubViewport nodes
- Step-by-step scene creation instructions

### Signal Best Practices
- Clear, contextual signal names
- Typed signals for safety and IDE assistance
- Strategic signal usage (important events only)
- EventBus singleton for global signals
- Proper signal disconnection to prevent memory leaks

### Resource Management
- Resource cleanup in `_exit_tree()`
- `preload()` for essential resources, `load()` for optional
- PackedByteArray compatibility considerations
- Asset unloading for unused resources

### Performance Optimization
- Strategic use of node groups vs. direct references
- Object pooling for frequently spawned objects
- Physics layer optimization
- Packed arrays over regular arrays

### Error Handling
- Graceful fallbacks for missing resources
- Development-time assertions
- Production-appropriate error logging
- Network error handling for multiplayer

### TileMap Implementation (Godot 4.4)
- TileMap node deprecation notes
- TileMapLayer usage guidelines
- Navigation map access methods
- Layer-specific property management

## Migration Guide

If you're currently using the `.cursorrules` file, consider migrating to the modern `.cursor/rules` system:

1. Copy the `.cursor` folder to your project
2. Remove the old `.cursorrules` file
3. Enjoy better organization and maintainability

## Note on Cursor Rules Evolution

According to the [Cursor documentation](https://docs.cursor.com/context/rules-for-ai):

> For backward compatibility, you can still use a `.cursorrules` file in the root of your project. We will eventually remove .cursorrules in the future, so we recommend migrating to the new Project Rules system for better flexibility and control.

---

*This repository is not affiliated with Godot Engine or Cursor AI.*
