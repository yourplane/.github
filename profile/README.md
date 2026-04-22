# Yourplane

Run and collaborate with AI agents in infrastructure you control. It's your control plane.

# Overview

**Yourplane** is a system for building software with AI agents - without giving up control of your infrastructure, workflows, or tools.

Most AI development tools take one of two approaches:

* abstract away infrastructure and lock you into their platform
* expose raw cloud primitives with little cohesion

Yourplane sits in between:

structured workflows on top, full control underneath

# Why Yourplane exists

AI agents don’t have long-term memory - they have context windows.

Most tools try to hide this by:

* stitching together context behind the scenes
* encouraging long-running chats
* introducing opaque, fragile state

Yourplane takes a different approach:

> Design workflows that work with context limits, not against them.

# Core ideas
## 1. Work alongside agents

Agents aren’t black boxes that replace developers.

Yourplane is designed for:

* running multiple agents
* observing what they’re doing
* stepping in and working alongside them

## 2. Structure work to fit within context

Instead of trying to generalize context management:

* each task has a clear scope
* agents operate within bounded context
* long-term state lives in code and files

This makes AI workflows:

* predictable
* debuggable
* restartable

## 3. Make state explicit

Yourplane introduces a comms directory:

* a persistent, file-based interface for agent context
* used for instructions, notes, and feedback
* acts as the bridge between runs

Integrations (like PR comments) flow through this same interface.

> No hidden memory. No opaque state. Just files.

## 4. Stay unopinionated where it matters

Yourplane is:

* unopinionated about infrastructure
- run on EC2, Docker, or your own systems
* unopinionated about agent providers
- no lock-in to a single model or platform

But:

* opinionated about workflow
- structured task flow (plan → implement)
- persistent context
- integration with real development workflows

# Architecture

Yourplane is built in three layers:

## 1. Compute fleet management (`desk`)

Provision and manage environments where work runs.

* cloud workstations (EC2)
* future support for containers and other backends
* fully owned by the user

## 2. Agent orchestration (`agency`)

Run and manage agents across environments.

* start / stop agents
* stream output
* manage multiple agents
* provider-agnostic

## 3. Workflow layer (`dev`)

Define how work gets done with agents.

* task-based workflows
* comms directory for context
* plan → implement loop
* PR integration

# Philosophy

* Control stays with the developer
* Agents are collaborators, not authorities
* State should be explicit and inspectable
* Everything should be composable and replaceable

# What’s coming next

* richer multi-agent workflows
* improved remote interaction (web terminal)
* lightweight environments (Docker workers)
* build and deployment tooling

> Bringing platform-team-level capabilities to individual developers—without taking away control.

# Status

yourplane is under active development.

Core components:

* `desk` - cloud developer environments
* `dev` - AI agent workflow system

# Vision

> As software becomes easier to build, more people will build it.
> 
> Yourplane aims to give those developers the same level of control, structure, and power that previously required a full platform team.
