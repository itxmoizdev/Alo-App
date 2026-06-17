# Alo App – VoIP Communication System (Telnyx + WebRTC)

## Overview

Alo App is a production-grade VoIP communication platform that enables users to purchase international phone numbers and make/receive real-time voice calls over mobile networks.

The system bridges traditional PSTN telephony with modern WebRTC-based communication, enabling seamless cloud-to-mobile voice connectivity through Telnyx infrastructure.

Built for real-world usage, Alo App focuses on low-latency voice communication, reliable call routing, and scalable session management.

---

## My Role

### Full-Stack Developer (Mobile + Backend + Telecom Systems)

Responsible for the end-to-end implementation of the system, including:

- Mobile application development (React Native)
- Backend architecture (Node.js / Fastify)
- Telecom integration (Telnyx Voice APIs)
- Real-time signaling system design
- Call lifecycle and session management
- WebRTC integration and optimization
- Production deployment and stability improvements

---

## Core Features

### International Number Provisioning

- Purchase and manage international phone numbers via Telnyx API
- Dynamic number assignment per user
- Number lifecycle management

---

### Real-Time Voice Communication

- WebRTC-based voice calling system
- Low-latency audio transmission
- Peer-to-peer connection establishment where applicable

---

### Call Routing System

- PSTN ↔ WebRTC bridging via Telnyx
- Intelligent routing between mobile clients and telecom network
- Secure call session orchestration

---

### Call Session Management

- Call initiation, ringing, active, and termination states
- Session persistence across network changes
- Call recovery handling for dropped connections

---

### Real-Time Signaling Layer

- WebSocket-based signaling server
- Offer/Answer exchange for WebRTC negotiation
- ICE candidate handling for NAT traversal
- Connection lifecycle synchronization between client and backend

---

## System Architecture

```text
                    ┌──────────────────────┐
                    │  React Native App    │
                    │  (Mobile Client)     │
                    └──────────┬───────────┘
                               │
                               ▼
                 ┌──────────────────────────┐
                 │  Fastify Backend API     │
                 │  (Node.js Server)       │
                 └──────────┬───────────────┘
                            │
        ┌───────────────────┼────────────────────┐
        ▼                   ▼                    ▼
┌──────────────┐  ┌────────────────┐  ┌────────────────────┐
│ Telnyx Voice │  │ WebSocket      │  │ PostgreSQL         │
│ API (PSTN)   │  │ Signaling      │  │ + Redis State      │
└──────────────┘  └────────────────┘  └────────────────────┘
```

---

## Engineering Highlights

### Telecom Integration

- Integrated Telnyx Voice API for number provisioning and call routing
- Managed PSTN connectivity with real-time WebRTC sessions

---

### WebRTC System Design

- Implemented signaling server for peer negotiation
- Handled ICE candidate exchange and NAT traversal
- Optimized connection stability under mobile network conditions

---

### Call Lifecycle Engineering

- Designed deterministic call state machine
- Managed transitions: idle → ringing → active → terminated
- Ensured synchronization between client and backend state

---

### Reliability & Edge Case Handling

- Call drop recovery mechanisms
- Network switching (WiFi ↔ Mobile data) handling
- Retry logic for failed signaling exchanges
- Session consistency across reconnects

---

## Challenges Solved

### Real-Time Communication Stability

Ensured consistent voice quality and connection stability across varying mobile network conditions.

---

### WebRTC + PSTN Bridging

Solved complexity of bridging browser/mobile WebRTC sessions with traditional telecom infrastructure via Telnyx.

---

### State Synchronization

Maintained consistent call state across:

- Mobile client
- Backend API
- Telephony provider (Telnyx)

---

### NAT Traversal & Connectivity

Handled ICE negotiation and NAT traversal issues to maintain reliable peer connections.

---

## Tech Stack

| Layer | Technologies |
|------|-------------|
| Mobile | React Native |
| Backend | Node.js, Fastify |
| Telecom | Telnyx Voice API |
| Real-Time | WebRTC, WebSocket |
| Database | PostgreSQL |
| Cache | Redis |

---

## Status

- Production system (actively maintained and scaling)
- Real-world telecom integration in use
- Ongoing improvements in call stability and routing efficiency

---

## Confidentiality Notice

This system involves live telecom integrations and production call routing logic. Core implementation details and proprietary routing logic are not publicly available due to security and operational constraints.
