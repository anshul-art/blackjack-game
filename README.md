# Blackjack Game

A command-line Blackjack (21) card game built in Python as part of **Milestone Project 2**.

## Table of Contents

- [About the Project](#about-the-project)
- [How to Play](#how-to-play)
- [Game Rules](#game-rules)
- [Project Architecture](#project-architecture)
- [Classes Overview](#classes-overview)
- [How to Run](#how-to-run)
- [Example Gameplay](#example-gameplay)

---

## About the Project

This is a text-based Blackjack game where a player competes against a computer dealer. The player starts with 100 chips and can place bets each round. The game follows standard Blackjack rules including Ace adjustment logic (Ace counts as 11 or 1 depending on the hand total).

## How to Play

1. You start with **100 chips**
2. Place a bet at the beginning of each round
3. You and the dealer each receive two cards
4. One of the dealer's cards stays hidden until the end
5. Choose to **Hit** (draw another card) or **Stand** (keep your hand)
6. Try to get as close to **21** as possible without going over
7. After you stand, the dealer draws until reaching at least 17
8. Whoever is closer to 21 wins the round

## Game Rules

| Rule | Description |
|------|-------------|
| **Card Values** | Number cards = face value, Face cards (J/Q/K) = 10, Ace = 11 or 1 |
| **Blackjack** | A hand totaling exactly 21 |
| **Bust** | Going over 21 — automatic loss |
| **Dealer Rule** | Dealer must hit until hand value is 17 or higher |
| **Push** | A tie — no chips won or lost |
| **Ace Handling** | If busting with an Ace, it switches from 11 to 1 automatically |

## Project Architecture

```
Global Variables (suits, ranks, values)
       ↓
  Card Class         → Represents a single card
       ↓
  Deck Class         → 52 cards, shuffle & deal
       ↓
  Hand Class         → Player/Dealer hand, tracks value & aces
       ↓
  Chips Class        → Manages betting and chip balance
       ↓
  Game Functions     → take_bet, hit, hit_or_stand, show_some,
                       show_all, player_busts, player_wins, etc.
       ↓
  Game Loop          → Main while loop that runs the game
```

## Classes Overview

### `Card`
Represents a single playing card with a suit and rank. Has a `__str__` method for readable output like *"Ace of Spades"*.

### `Deck`
Creates a standard 52-card deck using all suit and rank combinations. Supports shuffling and dealing (popping cards off the list).

### `Hand`
Holds a list of `Card` objects and tracks the total hand value. Includes ace adjustment logic — if the hand goes over 21 and contains an ace, the ace value drops from 11 to 1.

### `Chips`
Tracks the player's chip balance (starts at 100) and the current bet. Has methods to add or subtract chips on wins and losses.

## How to Run

**Requirements:** Python 3.6+

```bash
git clone https://github.com/anshul-art/blackjack-game.git
cd blackjack-game
python blackjack.py
```

No external libraries needed — only uses Python's built-in `random` module.

## Example Gameplay

```
Welcome to BlackJack!
How many chips would you like to bet? 50

Dealer's Hand:
 First card hidden!
 Six of Hearts

Player's Hand:
 Jack of Diamonds
 Nine of Clubs

Hit or Stand? Enter h or s: s
Player Stands. Dealer's Turn.

Dealer's Hand:
 Ten of Spades
 Six of Hearts
 Queen of Clubs
Value of Dealer's hand: 26

Player's Hand:
 Jack of Diamonds
 Nine of Clubs
Value of Player's hand: 19

PLAYER WINS! DEALER BUSTED!

Player's total chips: 150
Would you like to play again? (y/n): n
Thank you for playing!
```

---

*Built as Milestone Project 2 — Python OOP*
