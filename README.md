# P2P Auction System

## About

**P2P Auction System** is a C network programming project developed as a third-year Bachelor's (L3) project at Université Paris Cité. Built entirely from scratch, this project demonstrates a deep understanding of advanced C socket programming, IPv6 networking, multicast communication, and decentralized consensus algorithms.

The application allows peers to dynamically join a distributed network, initiate auctions, place bids, and handle system synchronizations through a robust multi-threaded architecture.

*Note: As this was originally an academic project evaluated on networking and concurrency, the codebase emphasizes manual socket management, non-blocking I/O with `poll`, and secure message exchange protocols. The source code and comments might contain some French.*

## Tech Stack

- **Language:** C (Standard C17)
- **Networking:** IPv6, TCP/UDP Sockets, Multicast, `poll()`
- **Concurrency:** POSIX Threads (`pthread`)
- **Build System:** Makefile

## Key Features

- **Decentralized Architecture:** Peer-to-peer system where nodes can join, manage, and leave dynamic auction groups seamlessly.
- **Multicast & Unicast Communication:** Hybrid networking model utilizing UDP multicast for broadcast messages and TCP for reliable peer-to-peer data sharing.
- **Consensus Mechanism:** Robust validation and signature verification workflow to ensure synchronization and reliability across all peers during critical operations.
- **Automated Timers & Watchdogs:** Background threads managing inactive auctions, automatic timeout notifications, and supervisor monitoring.
- **Robust Error Handling & Signal Management:** Clean interception of system signals and rigorous resource cleanup to prevent memory leaks and dangling sockets.

## Project Structure

```text
📁 network-auction-project
│
├── 📁 include/                     # Header files
├── 📁 src/                         # C source files (.c)
│   ├── 📄 auction.c                # Main application entry point & CLI
│   ├── 📄 auction_handler.c        # Auction state machines & bidding logic
│   ├── 📄 collections.c            # Data structures implementation
│   ├── 📄 consensus.c              # Consensus and signature validation
│   ├── 📄 handlers.c               # Thread execution handlers
│   ├── 📄 linking.c                # Network integration workflow
│   ├── 📄 netio.c                  # Safe read/write utilities
│   ├── 📄 netutils.c               # Socket creation and address binding
│   └── 📄 protocol.c               # Message serialization and parsing
│
├── 📄 LICENSE                      # License of the project
├── 📄 Makefile                     # Build configuration
└── 📄 README.md                    # Project documentation
```

## Getting Started

### Prerequisites

- C Compiler (GCC supporting C17)
- Make
- A Unix environment supporting IPv6 and Multicast

### Compilation and Execution

1. **Clone the repository:**

```bash
git clone https://moule.informatique.univ-paris-diderot.fr/.../programmation-reseau-projet.git
cd network-auction-project
```

2. **Compile the project:**

```bash
make
```

3. **Launch the auction program:**

```bash
./auction
```

4. **Run with Valgrind (Memory Leak Check):**

```bash
make valgrind
```

5. **Cleaning build artifacts:**

```bash
make clean
```

## Available Commands

Once the program is running, you can use the following interactive commands:
- `init <initial_price>` — Initialize a new auction with a starting price.
- `bid <auction_num> <price>` — Place a bid on an active auction.
- `list` — Display all active and closed auctions.
- `help` — Show the list of available commands.
- `quit` — Safely leave the auction system and exit.

## Team

This project was developed collaboratively as part of the M1 curriculum at Université Paris Cité:

- **CHEN Michel** — C Development & Network Architecture
  [![GitHub](https://img.shields.io/badge/GitHub-Profile-181717?logo=github)](https://github.com/SuyuKuka)
  [![LinkedIn](https://img.shields.io/badge/LinkedIn-Profile-0A66C2?logo=linkedin)](https://linkedin.com/in/chen-michel)

- **LIN Qinghui** — C Development & Network Architecture
  [![GitHub](https://img.shields.io/badge/GitHub-Profile-181717?logo=github)](https://github.com/qinghui-lin)

- **ROIG Lucas** — C Development & Network Architecture
  [![GitHub](https://img.shields.io/badge/GitHub-Profile-181717?logo=github)](https://github.com/ll-tykas)


## License

This project is licensed under the GPL 3.0 License — see [LICENSE](LICENSE) for details.