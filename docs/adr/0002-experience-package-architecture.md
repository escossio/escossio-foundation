# ADR 0002 — Experience Package Architecture

## Status

Accepted

## Context

Os produtos do ecossistema precisam entregar conhecimento, experiências ou decisões para diferentes plataformas sem acoplamento.

Não é desejável que Android, Desktop, Wear OS, Home Assistant ou futuros consumidores conheçam detalhes internos dos motores.

## Decision

Experience Package is the official concept for distributing complete experiences across the Escossio ecosystem.

An Experience Package represents a complete experience, ready to be consumed by another platform.

The package describes what should happen.

The platform decides only how to execute it.

The package does not belong to Agenda Falante.

It belongs to the Escossio ecosystem.

## Philosophy

"Não distribuímos arquivos.

Distribuímos experiências."

An Experience Package encapsulates everything a platform needs to deliver an experience to the user.

## Conceptual Structure

The structure below is conceptual only:

- Experience Package
- manifest.json
- identity/
- context/
- experience/
- segments/
- templates/
- metadata/
- version
- signature
- checksums

No physical format is defined at this stage.

## Content

An Experience Package may contain, in future stages:

- identity;
- context;
- narrative;
- segments;
- templates;
- preferences;
- metadata;
- version;
- integrity;
- signature.

Not all items are mandatory.

## Consumers

The same Experience Package may be used by:

- Agenda Falante Android;
- Wear OS;
- Android Auto;
- Automotive OS;
- Desktop;
- Home Assistant;
- future projects.

## Benefits

- decoupling;
- portability;
- versioning;
- cache;
- incremental updates;
- synchronization;
- offline distribution;
- reuse.

## Conceptual Examples

- Incoming Call Experience Package.
- Home Assistant Notification Package.
- RouteBrain Diagnostic Experience.

All of them follow the same concept.

## Relationship with Other Concepts

- Acoustic Identity defines who is being communicated.
- Experience Engine defines which experience should exist.
- Experience Package transports that experience.
- The platform only executes it.

## Future Evolution

Possible future evolutions include:

- compression;
- digital signature;
- cloud distribution;
- experience marketplace;
- premium packages;
- synchronization between devices;
- differential updates;
- encryption.

## Result

Experience Package becomes the universal format for distributing experiences between the Core and any consuming platform within the Escossio ecosystem.

