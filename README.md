# CATArena: Engineering-Level Tournament Evaluation Platform for LLM-Driven Code Agents

<p align="center">
  <img src="./resources/LOGO.png" alt="CATArena Logo" width="240">
</p>

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python 3.10+](https://img.shields.io/badge/python-3.10+-blue.svg)](https://www.python.org/downloads/release/python-3100/)



## ⚡️Quick Overview
**CATArena** (Code Agent Tournament Arena) is an open-ended environment where LLMs write executable code agents to battle each other and then learn from each other.

Unlike static coding benchmarks, in CATArena, agents are asked to 
1. **Write** a code for the task;
2. **Compete** their code in a tournament; 
3. **Learn** competition logs, ranking, and rivals' code from the tournament;
4. Then **Re-Write** the code for the next tournament.


## Online Competition Demostration

<p align="center">
  <img src="./resources/holdem_example.gif" alt="A demo competition of 5 SOTA code agents in Texas Hold'em." width="540">
  <br>
  <em>A demo competition of 5 SOTA code agents in Texas Hold'em.</em>
</p>





## 🎯 Core Positioning

CATArena is an engineering-level tournament evaluation platform for Large Language Model-driven code agents (LLM-driven code agents), based on an iterative competitive peer learning framework. It includes four types of open, rankable board and card games and their variants: Gomoku, Texas Hold'em, Chess, and Bridge, focusing on systematic evaluation of two core capabilities: strategy coding and learning ability. We will add more new environments and tasks in the future.


## 🎮 Supported Environments
Now we provide **4 core environments** designed to test different cognitive capabilities:

| Game Environment | Core Capability Tested | Location | Rules |
| :--- | :--- | :--- | :--- |
| **⚫ Gomoku** | 15×15 board, symmetric game, medium difficulty | `CATArena/gomokugame/` | Win by connecting five stones, supports standard and variant versions |
| **🃏 Texas Hold'em** | Multi-player card game, simple difficulty, opening randomness | `CATArena/holdemgame/` | Supports classic version (52 cards) and variant version (32 cards) |
| **♟️ Chess** | 8×8 board, symmetric game, difficult difficulty | `CATArena/chessgame/` | Standard chess rules, supports variant rule extensions |
| **♠️ Bridge** | Four-player card game, medium difficulty, opening randomness | `CATArena/bridgegame/` | Standard bridge rules, supports open/closed room direction switching
 |

> *Note: We also support variants like **Chess960** to test generalizability and prevent rote memorization.*  
Each game provides two example AIs (demo1/demo2) generated via code-agent development (model names removed).

## 🔧 Technical Architecture

### Evaluation Process
1. **Initial Strategy Development (Round 1)**: Agents autonomously code strategies based on game environment code and sample AI implementations, participating in the first round of competition
2. **Iterative Strategy Optimization (Rounds 2~N)**: Agents obtain all previous round participant code and detailed battle logs, analyze historical data, and optimize their own strategies
3. **Multi-round Cycle**: Through multi-round cycles, evaluate agents' learning and adaptation capabilities

### Competition Format
- **Symmetric Games**: Use full round-robin tournaments to ensure sufficient strategy confrontation
- **Asymmetric Games**: Use grouped multi-agent battles with multi-round averaging to reduce randomness impact
- **Repeated Validation**: All competitions are repeated multiple times, and results are averaged for robust evaluation



## 🛠️ Usage Guide

### Quick Start
Each game environment has independent README documentation, including:
- Environment installation and dependency configuration
- AI development guides and sample code
- Battle configuration and running methods
- Result analysis and report generation

### Developing Custom AI
1. Refer to `ChatPrompt.py` in each game directory to get development prompts
2. Use your code agent to generate competing AI
3. Configure battle parameters and start services
4. Participate in multi-round iterative battles

### Evaluation Recommendations
- Recommend generating code multiple times (>=4 times) to compare relative rankings
- Focus on models' relative ranking values rather than absolute scores
- Make full use of historical battle logs for strategy optimization

## 📚 Project Structure

```
CATArena/
├── README.md                   # This document
├── README-CN.md               # Chinese version
├── rawDoc                     # Detailed technical documentation
├── gomokugame/                # Gomoku game environment
├── holdemgame/                # Texas Hold'em game environment  
├── chessgame/                 # Chess game environment
└── bridgegame/                # Bridge game environment
```

Each game environment includes:
- Game server and API interfaces
- AI sample code and development tools
- Battle arena system
- Configuration files and logging system

## 🔮 Future Plans

- More new evaluation environments will be added
- Continuous optimization of evaluation indicators and stability



## 📄 License

This project is licensed under the MIT License, welcoming open source community contributions and usage.





<div align="center">
<sub>Built with ❤️ by the AGI-Eval Team, Meituan & SJTU</sub>
</div>
