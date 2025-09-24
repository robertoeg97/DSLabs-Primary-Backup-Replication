# Primary-Backup Replication Project

The project source code and detailed report are private and can be shared conditionally upon request. This public summary outlines the core objectives, challenges, and achievements.

## Project Overview

This project implements a fault-tolerant key-value store using the primary-backup replication protocol, a classic approach in distributed systems for ensuring data consistency and high availability. The system is designed to tolerate server and network failures, maintaining exactly-once semantics for client operations.

### Problem Statement

In distributed environments, server failures and network partitions can disrupt service availability and consistency. The goal of this project is to design and implement a replicated key-value store that continues to serve client requests correctly even in the presence of such failures, using a primary-backup architecture.

### High-Level Design

- **Primary-Backup Replication:** The system maintains a primary server responsible for handling client requests and a backup server that mirrors the primary's state. If the primary fails, the backup is promoted to primary, and a new backup is selected.
- **ViewServer Coordination:** A dedicated ViewServer monitors server liveness and manages view changes, ensuring that only one server acts as primary at any time.
- **Exactly-Once Semantics:** The protocol ensures that each client operation is executed exactly once, even in the face of retries or network issues.
- **Failure Detection & Recovery:** Servers periodically ping the ViewServer to signal liveness. The system detects failures and orchestrates seamless failover and state synchronization.
- **Network Partition Tolerance:** The design accounts for scenarios where clients or servers may be temporarily unable to communicate, ensuring eventual consistency and progress.

### My Contributions

- Designed and implemented the primary-backup protocol logic, including view management, failure detection, and state synchronization.
- Developed mechanisms for exactly-once command execution and robust client-server interaction.
- Extensively tested the system under simulated failure and partition scenarios to validate correctness and liveness.
- Authored comprehensive documentation and a technical report outlining design decisions and trade-offs.

### Skills & Technologies

- Distributed systems concepts: replication, fault tolerance, consistency models
- Java (core language for implementation)
- Event-driven programming and state machine design
- Debugging and testing distributed protocols

### Learning Outcomes

- Gained hands-on experience with designing and implementing fault-tolerant distributed protocols.
- Developed a deep understanding of the challenges in maintaining consistency and availability in the presence of failures.
- Improved skills in debugging, testing, and reasoning about distributed systems.
