# General Concepts

## What is DIDComm?

DIDComm (Decentralized Identifier Communication) is a secure, privacy-preserving messaging protocol that enables direct communication between decentralized digital agents. Built on the foundation of Decentralized Identifiers (DIDs), DIDComm allows entities to exchange messages without relying on centralized intermediaries or exposing metadata to third parties.

At its core, DIDComm provides a standardized way for digital agents to discover each other's capabilities, establish secure communication channels, and exchange structured messages. This enables applications ranging from credential verification to secure peer-to-peer messaging, all while maintaining user privacy and control.

DIDComm sits within the broader self-sovereign identity ecosystem, providing the communication layer that connects DID-based identities with practical applications. It transforms DIDs from static identifiers into dynamic communication endpoints.

At it's core, DIDComm is a secure way to communicate, that is also friendly to the devices that humans use. Portable devices are not great hosts of APIs in the traditional sense, which has excluded them from enabling users to be first-class citizens on the Internet. DIDComm carries many similar attributes with APIs, but fixes the device friendlyness issue.

## Core Principles

**Decentralization**: DIDComm operates without central authorities or single points of failure. Participants communicate directly using their DIDs, maintaining control over their own communication channels and data.

**Privacy and Security by Design**: All communication is end-to-end encrypted by default. Message metadata is minimized and protected, ensuring that even transport providers cannot access message contents or detailed routing information. Because it promotes direct communication between parties, DIDComm naturally discourages surveilance. Those designing DIDComm protocols should avoid adding surveilance (including phoning home) back in to the protocol architecture.

**Interoperability**: DIDComm is designed to work across different platforms, devices, and implementations. The protocol is transport-agnostic, meaning it can operate over HTTP, WebSocket, Bluetooth, or other communication channels. The trust and security of DIDComm does not rely on the attributes of it's transport.

**Agent-Centric Architecture**: Communication happens between software agents acting on behalf of entities (people, organizations, or devices). These agents manage keys, route messages, and handle protocol interactions autonomously.

**End-to-End Encryption**: Messages are encrypted using the recipient's public keys, ensuring only the intended recipient can decrypt and read the content. This provides confidentiality and authenticity without trusting intermediaries.

## Key Components

### DIDs and DID Documents

DIDs serve as the addressing mechanism in DIDComm. Each participant has a DID that resolves to a DID document containing cryptographic keys and service endpoints. The DID document specifies how to reach the entity's agent and which keys to use for encryption and signing.

Service endpoints in DID documents indicate where messages should be delivered, while the associated keys enable secure communication including the use of message relays (mediators). Key management through DID documents allows for key rotation and multiple key types for different purposes.

### Agents

Agents are software components that send, receive, and process DIDComm messages on behalf of their owners. They handle the cryptographic operations, message routing, and protocol execution required for DIDComm communication.

**Edge agents** typically run on user devices (phones, computers) and provide direct access to DIDComm functionality. They store private keys locally and make protocol decisions on behalf of their users.

**Relay (Mediator) agents** provide routing services for agents that cannot be directly reached (such as mobile devices behind NAT or agents that are temporarily offline). They forward messages without being able to decrypt their contents.

Agents maintain the state of ongoing protocols, manage relationships with other agents, and provide the user interface for DIDComm interactions.

### Messages

DIDComm messages are structured JSON documents that contain both headers and payload data. The message format supports different types of content while maintaining consistency across all DIDComm interactions.

Message headers include metadata such as the message type, sender and recipient information, and protocol-specific fields. The standardized header structure enables agents to process messages efficiently and route them correctly.

Different message types serve various purposes: basic messages for simple communication, connection messages for establishing relationships, credential exchange messages for sharing verifiable credentials, and problem reports for error handling.

The message structure is designed to be both human-readable during development and efficient for automated processing by agents.

>Note: This book is a community-supported resource, under regular improvement. Corrections and contributions are welcome at our [GitHub Repo](https://github.com/decentralized-identity/didcomm-book/).
