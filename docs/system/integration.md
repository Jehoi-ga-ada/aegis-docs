# System Integration

This document describes how the six repositories communicate and the technology stack that connects them.

## Communication Channels
* **Real-time Streaming:** Most components communicate via **WebSockets** or a **Message Broker** (like NATS or Redis Pub/Sub) to ensure sub-millisecond delivery of market data.
* **State Access:** The **Surface (UI)** and **Cortex (API)** communicate via **REST** for configuration and **WebSockets** for live portfolio updates.

## Data Persistence
* **TimescaleDB:** Used for high-speed time-series data (Price Ticks and Execution Reports).
* **Relational Storage:** Used for user settings and strategy configurations.

## Standardization
All communication must strictly adhere to the `aegis-genome` protocol. No component is allowed to send "Raw JSON" to another; data must be normalized by the sender before transmission.