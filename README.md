# Raft Implementation
This project is centered around building a fault-tolerant key-value store system that relies on the Raft consensus algorithm. The main aim is to ensure consistent data across replicas even in the face of failures and network partitions.

## Project Structure

- [3700kvstore](./3700kvstore): contains all application logic and implementation.
- [run](./run): a compiled test suite to test the implementation in various scenarios.

## Key Features
- State Management: Efficiently manages different states of a replica (follower, candidate, leader) to ensure smooth state transitions and appropriate actions based on the state.
- Election Process: Implements timeouts that trigger elections to promote replicas to candidates or leaders, enhancing the system's availability by ensuring there is always a leader when possible.
- Log Replication: Ensures all committed entries are consistently replicated across all replicas, maintaining data integrity and state consistency.
- Heartbeats: Utilizes heartbeats for leaders to maintain authority and prevent unnecessary re-elections, contributing to system stability.
- Fault Tolerance: Designed to handle network failures and ensure the system remains consistent and available, even under less-than-ideal network conditions.

## Challenges Encountered
- Network Partitions: Dealing with network partitions required implementing robust mechanisms to handle split votes and message delays effectively.
- Election Safety: It was crucial to ensure that no two leaders can be elected in the same term and that logs remain consistent across all replicas.

## Instructions