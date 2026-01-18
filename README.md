# Sanguine Queen’s Blood

## Overview
**Sanguine Queen’s Blood** is a two-player, turn-based strategy card game implemented in **Java**, featuring both **human and AI-controlled players**. Players take turns placing cards onto a grid-based board, competing for control of rows through pawn placement, card effects, and positional strategy.

The project follows a **Model–View–Controller (MVC)** architecture and supports **pluggable AI agents**, allowing multiple strategies to be composed into a single decision-making agent. The game includes both a **GUI and textual view**, with full validation and feedback for player actions.

This project was developed as part of a university software design course and is archived as a **demonstration of object-oriented design, MVC architecture, and AI strategy composition**.

## Key Features
- Turn-based, two-player strategy gameplay  
- MVC architecture with strict model immutability for views  
- Grid-based board with pawn and card mechanics  
- GUI and text-based views  
- Human and AI-controlled players  
- Composable AI agents with multiple strategies  
- Robust input validation and game-state feedback  

## Architecture Highlights
### Model
Represents the board, cells, cards, pawns, decks, and scoring logic.  
Includes a read-only model interface to prevent view-side mutation.

### View
Provides both GUI and textual representations of the game state, displaying board ownership, scores, player hands, and endgame results.

### Controller / Agents
Uses an **agent-based controller system** where each agent decides actions per turn.  
Agents can be human-driven or AI-driven and may combine multiple strategies in priority order.

## AI Agents
The game supports multiple AI strategies that can be combined into a single agent:
- **User Agent** – Accepts direct player input  
- **Simple Agent** – Plays the first valid move  
- **WinRow Agent** – Prioritizes winning individual rows  
- **Control Agent** – Attempts to control board ownership  
- **Default Agent** – Passes when no valid move exists  

Agents are composed using a strategy chain, allowing complex behavior to emerge from simple components.

## Status
Archived — maintained for portfolio and academic documentation purposes.
