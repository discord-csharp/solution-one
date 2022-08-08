# Decentralizing the Net with .NET

## Description

Building secure E2EE P2P systems has never been simpler, with .NET and SignalR – In this talk, we will walk through the process of building a P2P backplane for SignalR, and connect our application as nodes together dynamically, discussing tradeoffs and security considerations along the way.

## Outline

- Setting the Stage
  - Briefly walk through the example chat application architecture and the client-server model.
  - Review the data model and specific qualities that make it translatable to peer-to-peer implicitly.
- Plan of Attack: SignalR Backplanes
  - Introduce the concept of backplanes in SignalR, with the typical Redis example.
  - Idea: Create a SignalR Backplane using a peer-to-peer gossip protocol
  - Idea: Swap out user registry with cryptographic identities, discuss tradeoffs - how do we verify? Strategies: PKI, Web of Trust
- Implementation: Backplane
  - Creating the P2P HubLifetimeManager implementation
  - Hooking it up and watching it go
- Implementation: User Registry
  - Cryptographic identities, how do they work?
  - PKI/WoT hybrid implementation
- Implementation: Securing the protocol
  - Demonstration: Bad actors - message forgeries, message censorship, message reordering, break-ins
  - Adding the Triple-Ratchet algorithm
- Final notes/observations, close out