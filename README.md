# Parcial: Hangman

## Overview

Create a **command-line Hangman game** in **Python** that is engaging, resilient, and well-structured. You’ll combine **imperative programming**, **modular design**, **robust error handling**, and **OOP concepts** (objects, classes, inheritance, abstract classes, attributes, properties) to deliver a polished experience. Players choose a **theme**, a word is selected from a **15-word list**, and results are **saved to JSON** so users can replay and view their history (attempts, wins/losses, words solved).

> **Deliverable:** a runnable CLI program plus a short README

---

## Learning Goals

- **Imperative programming:** input/loops/conditionals and state updates during gameplay.
- **Modular programming:** separate responsibilities across multiple Python files.
- **Error handling:** validate input, handle I/O failures, and avoid crashes.
- **OOP concepts:** implement objects, classes, inheritance, abstract classes, attributes, properties.
- **Persistence:** record results to a JSON file and display user stats across runs.

---

## Functional Requirements

### Gameplay
- The user selects a **theme** (e.g., Animals, Movies, Sports, etc.).
- The program selects a **random word** from a **theme-specific list of at least 15 words**.
- Show a masked word (e.g., `_ _ a _ _`) and track:
  - **Correct letters**, **incorrect letters**, **remaining attempts**.
- End conditions:
  - **Win** when the word is fully revealed.
  - **Loss** when attempts reach zero.
- Offer **replay** without restarting the program.

### CLI Features
- Menu-driven flow (e.g., **New Game**, **View Stats**, **Reset Stats**, **Exit**).
- During a game: prompt for a **single-letter guess** and reject invalid input.
- Optional: ASCII progress (gallows or progress meter).

### Persistence & Stats
- Save results to a **JSON file** after each completed game:
  - Player identifier (prompt for a simple name/alias).
  - Timestamps, chosen word, number of attempts used, result (win/loss).
  - Aggregate stats (e.g., total games, wins, losses, solved words list, most-missed letters).
- **View Stats** shows a readable summary (totals and recent history).
- **Reset Stats** clears the file with a confirmation step.

---

## Technical Requirements

- **Imperative programming:** clear control flow for the game loop, input prompts, and updates.
- **Modular programming:** split responsibilities across multiple files (e.g., CLI/menu, game logic, persistence, words, stats).
- **Error handling:** 
  - Invalid menu choices or guesses.
  - Repeated guesses.
  - File I/O (missing JSON file on first run, corrupted JSON, permissions).
  - Graceful recovery with user-friendly messages.
- **OOP usage (required):**
  - Use **classes** and **objects** to represent game entities and behavior.
  - Apply **inheritance** and **abstract classes** where appropriate.
  - Use **attributes** and **properties** for encapsulation and validation.
- **Data files:** You may store word lists in text/JSON files.

---

## Example CLI Output (Illustrative Only)

> Below is **example output** to guide UX. Do **not** include code or class designs in your submission.

```
========================================
        HANGMAN — MIDTERM EDITION
========================================
Player name: jose

Welcome, jose!
Select an option:
1) New Game
2) View Stats
3) Reset Stats
4) Exit
> 1

Starting NEW GAME (Theme: Animals)
Word: _ _ _ _ _ _   Attempts left: 6
Guessed letters: [ ]

Enter a letter: a
Good guess!
Word: _ a _ _ _ _   Attempts left: 6
Guessed letters: [ a ]

Enter a letter: e
Nope.
Word: _ a _ _ _ _   Attempts left: 5
Guessed letters: [ a, e ]

Enter a letter: i
Good guess!
Word: _ a _ i _ _   Attempts left: 5
Guessed letters: [ a, e, i ]

Enter a letter: o
Nope.
Word: _ a _ i _ _   Attempts left: 4
Guessed letters: [ a, e, i, o ]

Enter a letter: r
Good guess!
Word: r a _ i _ _   Attempts left: 4
Guessed letters: [ a, e, i, o, r ]

Enter a letter: b
Good guess!
Word: r a b i _ _   Attempts left: 4
Guessed letters: [ a, b, e, i, o, r ]

Enter a letter: t
Good guess!
Word: r a b i t _   Attempts left: 4
Guessed letters: [ a, b, e, i, o, r, t ]

Enter a letter: y
Good guess!
Word: r a b i t y   Attempts left: 4
Guessed letters: [ a, b, e, i, o, r, t, y ]

Congratulations, jose! You solved it: RABITY
(Result saved)

Play again? (y/n): y

Select an option:
1) New Game
2) View Stats
3) Reset Stats
4) Exit
> 3

========== STATS ==========
Player: jose
Total games: 7
Wins: 5
Losses: 2
Win rate: 71%
Recent words:
 - 2025-08-24 14:02: rabbit  (win, 8 guesses)
 - 2025-08-24 13:38: jaguar  (loss, revealed 4/6 letters)
 - 2025-08-24 13:20: dolphin (win, 7 guesses)
===========================
```

---

## Data & Themes

- Prepare at least **one theme** with **≥ 15 words**.  
- Additional themes are welcome (each with its own list).
- Words should be lowercase alphabetic (no spaces/punctuation) or validate how you handle them.

---

## Error Handling Expectations

- Reject non-letter input, multiple-character guesses, and previously guessed letters with clear messages.
- Handle missing or malformed word files gracefully (fallback or error prompt).
- When reading stats JSON:
  - If the file doesn’t exist: initialize an empty structure.
  - If file is corrupted: notify the user and offer to reset or back up.
- Ensure the game never crashes due to typical input mistakes.

---

## Evaluation (100 pts)

| Criterion                                           | Points |
|-----------------------------------------------------|--------|
| **Gameplay completeness** (win/loss loop, replay)   | 20     |
| **Imperative control flow** (input/loops/logic)     | 15     |
| **Modular design** (clear separation of concerns)   | 15     |
| **OOP usage** (objects, inheritance, abstract, props)| 25     |
| **Error handling** (input + I/O robustness)         | 15     |
| **Persistence & stats** (JSON save/load & display)  | 10     |

**Bonus (+10 max):**
- Multiple themes with seamless switching.
- Difficulty modes (attempt limits, hint system).
- ASCII progress visuals.
- Per-letter frequency insights in stats.

---

## Constraints

- **Language:** Python (standard library only).
- **Runtime:** Works in a standard terminal.
- No external packages or web calls.
- Keep the user experience responsive and clear.

---

## Rules

- You can only use a single page hand written cheat sheet
- Internet use is prohibited (you may commit throughout the period and push at the end)
- No use of LLMs or code completion
- No talking to other classmates
