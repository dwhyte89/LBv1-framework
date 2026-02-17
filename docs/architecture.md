# LBV1 High-Level Architecture

LBV1 is an offline-first AI operating framework designed around modular cognition, persistent memory, and controlled task execution.

## Goals
- Offline by default; external providers optional and gated
- Strict separation of code, config, and runtime data
- Stable core execution logic with swappable per-user persona layer
- Auditable task execution with optional confirmation gates

## Layers (Conceptual)

UI / Client
  ↓
Session Controller
  ↓
Core Brain (immutable)
  - Safety + policy constraints
  - Permissions + authorization gates
  - Task engine + execution planner
  - Memory manager (store/recall/prune)
  - Model router (local-first; external optional)
  ↓
Model Backends
  - Local model(s)
  - External providers (disabled by default; explicit authorize required)

## Data Separation
- Code: application logic only
- Config: instance settings and feature flags
- Data: user memory, logs, chats, backups (never shipped with the app)
