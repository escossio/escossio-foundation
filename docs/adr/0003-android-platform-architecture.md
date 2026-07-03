# 0006 - Android Platform Architecture

## Status

Accepted

## Context

A Agenda Falante Android Platform will be the Android-facing layer of the ecosystem.

It must remain independent from the Core while still being able to consume the Core through a clearly defined public contract.

This separation prevents product logic, synthesis logic, and platform logic from being mixed into a single layer.

## Decision

The Agenda Falante Android Platform will be composed of independent modules.

The modules are:

- `app`
- `platform`
- `bridge`
- `services`
- `integrations`
- `permissions`
- `playback`
- `storage`
- `automation`
- `ui`
- `tests`

## Module Responsibilities

- `app`: entrypoint and top-level composition of the Android application.
- `platform`: platform-level orchestration and shared Android runtime concerns.
- `bridge`: public contract boundary with the Core.
- `services`: application services used by the Android layer.
- `integrations`: integrations with Android capabilities and external Android-facing features.
- `permissions`: permission flow and permission state handling.
- `playback`: local audio playback responsibilities.
- `storage`: local persistence and file management.
- `automation`: support for automation flows and exported experiences.
- `ui`: user interface and interaction surfaces.
- `tests`: validation of Android platform behavior.

## Android Boundary

Only the Bridge knows the public contract of the Core.

The Android layer never knows:

- Planner;
- Composer;
- Narrative Engine;
- TTS engine;
- provider;
- ElevenLabs;
- OpenAI;
- Google.

The Android layer receives only experiences ready for playback.

## Android Bridge

The Bridge is responsible for:

- importing manifests;
- receiving events;
- resolving local paths;
- delivering experiences to Android.

The Bridge acts as the controlled boundary between the Core and the Android Platform.

## Futuras Plataformas

The same architecture may later serve:

- Wear OS;
- Android Auto;
- Automotive OS;
- desktop;
- other platforms.

## Consequences

- the Android layer remains focused on platform concerns;
- the Core remains independent and reusable;
- the contract boundary stays explicit;
- future platforms can reuse the same conceptual separation;
- the system avoids leaking synthesis or planning details into Android.

## Result

The Android Platform is formally defined as an independent layer of the ecosystem, with the Bridge as its only knowledge point about the Core.

