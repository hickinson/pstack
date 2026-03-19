# Enterprise Adapter

## Purpose

This document explains how to translate the framework into constrained enterprise environments without changing the core design philosophy.

It is an adapter concept, not a separate framework.

## Why an adapter model exists

In enterprise environments:
- tool access may be restricted
- actions may need approval
- data boundaries matter
- logs may be required
- autonomy must be bounded
- platform choice may be imposed

The framework should still work, but through controlled implementation.

## Adapter principles

### 1. Keep the core intact
Do not rewrite the whole framework per platform.

### 2. Expose approved capabilities, not raw power
The enterprise adapter should present bounded actions such as:
- retrieve approved document set
- draft response from approved context
- create record in approved system
- route for approval
- summarise approved source set

### 3. Separate reasoning from action
Reasoning may be flexible. Actions into enterprise systems should be controlled.

### 4. Use least privilege
Access should be scoped to what the task actually needs.

### 5. Keep approval points explicit
High-risk actions should not happen invisibly.

### 6. Make logging proportionate
Not every action needs heavy logging, but meaningful actions should be explainable.

## What belongs here

- approved capability registry
- data boundary rules
- action wrappers
- approval gates
- logging expectations
- platform mapping notes
- scoped MCP profile

## What does not belong here

- unrestricted experimentation
- direct unmanaged access to sensitive systems
- hidden autonomous actions
- duplicated framework philosophy

## MCP note

In enterprise settings, MCP should sit in the integration layer as a tightly governed capability adapter.

That means:
- approved servers or wrappers only
- capability-level scoping
- clear ownership
- logging where appropriate
- no casual direct access to sensitive systems

## Future adapter work

Later, you may create:
- platform-specific mappings
- approved tool catalogs
- capability wrappers
- risk-tiered approval routes
- audit-friendly runbooks

Do that later, not in version one.