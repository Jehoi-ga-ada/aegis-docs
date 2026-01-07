# System Overview

The **Aegis Terminal** is a modular, high-performance algorithmic trading system. It is designed to decouple data ingestion, strategy logic, and order execution to ensure speed and reliability.

## The Core Philosophy: aegis-genome
At the center of the system is the **genome**. This is a shared definition library that ensures every repository speaks the same "language." By using standardized types (e.g., `genome.Tick`, `genome.OrderRequest`), we can swap out a strategy (Synapse) or an exchange connector (Pulse) without rebuilding the entire system.

## Repository Breakdown
1. **aegis-pulse:** Data Ingestion (Sensors).
2. **aegis-synapse:** Strategy Logic (Brain).
3. **aegis-axon:** Risk & Execution (Hands).
4. **aegis-cortex:** State & API (Memory).
5. **aegis-surface:** Dashboard & UI (Eyes).
6. **aegis-genome:** Shared Types & Constants (DNA).