# Sanguine Queen’s Blood

## Overview
**Sanguine Queen’s Blood** is a two-player, turn-based strategy card game implemented in **Java**, featuring both **human and AI-controlled players**. Players take turns placing cards onto a grid-based board, competing for control of row score and board influence through card placement.

The project follows a **Model–View–Controller (MVC)** architecture and supports **pluggable AI agents**, allowing multiple strategies to be composed into a single decision-making agent. The game includes both a **GUI and textual view**, with full validation and feedback for player actions.

This project was developed as part of a **Northeastern's CS3100** course (previously Object-Oriented Design). As a result, the code is private to maintain the academic integrity of the class, but can be made available upon request for a limited time.

## Key Features
- Turn-based, two-player strategy gameplay  
- MVC architecture with model immutability for views  
- Grid-based board with pawn and card mechanics  
- GUI and text-based views  
- Human and AI-controlled players  
- Composable AI agents with multiple strategies  
- Input validation and error handling
- Full JUnit test suite 

## How to Play

### Quickstart
To start a game, run the provided JAR file with command-line arguments specifying the board size, hand size, shuffle option, deck files, and player agents in the following format:

java -jar hw7-dev.jar [rowCount:int] [columnCount:int] [startingHandSize:int] [shuffleDecks:boolean] [redDeck:string] [blueDeck:string] [redAgentType:string] [blueAgentType:string]

Example:
```bash
java -jar hw7-dev.jar 3 5 5 true docs/example.deck docs/example.deck user "control winrow simple"
```

### Controls
- **Mouse Click** – Select/Deselect cards and board cells  
- **Enter** – Confirm a move  
- **Space** – Pass turn

### Rules Overview
- The game is played by **two players** on a rectangular grid-based board.
- Players take turns either **playing a card** from their hand onto the board or **passing**.
- Cards may only be played on cells owned by the player and only if that cell contains enough pawns to cover the card’s cost.
- Each card contributes to the row score of the selected row and influences nearby cells (by adding pawns or taking enemy pawns).
- Each row is scored in a winner-takes-all manner.
- The game ends when both players pass consecutively.
- The player with the **highest total score across all rows** wins. Ties are possible.

## Screenshots
| | |
|---|---|
| ![](https://github.com/user-attachments/assets/d2500d1f-2232-4934-958f-a55bd04b114e) | ![](https://github.com/user-attachments/assets/a752da14-3d0f-4b7e-86e8-b35dad65a271) |
| ![](https://github.com/user-attachments/assets/cee833b6-b858-4cf1-afa3-e079e4cef4fd) | ![](https://github.com/user-attachments/assets/7e0f68fb-338c-4f58-b7cc-cd9831d7ed76) |

## Architecture Highlights
### Model
Represents the board, cells, cards, pawns, decks, and scoring logic.  
Includes a read-only model interface to prevent view-side mutation.

### View
Provides both GUI and textual representations of the game state, displaying board ownership, scores, player hands, and endgame results. The current version of this game utilizes a GUI representation for intuitive use.

### Controller 
Coordinates actions between the Model and View based on Player input. The Controller does not distinguish between User and AI agent Players, allowing for easy configuration of User vs User, User vs AI, and AI vs AI games.

### AI Agents
Uses an **agent-based controller system** where each agent decides actions per turn.  
Agents can be human-driven or AI-driven and may combine multiple strategies in priority order.

The game supports multiple AI strategies that can be combined into a single agent:
- **User Agent** – Accepts direct player input  
- **Simple Agent** – Plays the first valid move  
- **WinRow Agent** – Prioritizes winning individual rows  
- **Control Agent** – Attempts to maximize ownership of cells on board
- **Default Agent** – Passes when no valid move exists  

Agents are composed using a strategy chain, allowing complex behavior to emerge from simple components. The **User Agent** cannot be composed with other agents.

## Status
Archived — maintained for portfolio and academic documentation purposes.

## Contributors
This project was developed using a **pair programming** workflow.
- **Cooper Wick** ([@cooper-wick](https://github.com/cooper-wick))
- **Wyatt Smith** ([@Wyatt-Smith1](https://github.com/Wyatt-Smith1))
