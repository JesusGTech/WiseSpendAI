# WiseSpend AI

WiseSpend AI is an educational browser-based game and classroom research tool that helps students explore financial decision-making by teaching an AI the difference between needs and wants.

Players act as the AI's coach. During the game, they train the AI by labeling items as `Need` or `Want`, then watch the AI apply those patterns during later testing rounds. The goal is to help the AI make accurate decisions while protecting a limited budget over a 30-day challenge.

## Overview

WiseSpend AI was designed to support two connected goals:

- Teach students core budgeting ideas, especially the difference between needs and wants
- Study how students train, evaluate, and reflect on AI decision-making in a classroom setting

The software combines financial literacy, AI literacy, and lightweight data collection into a single experience.

## Running the Project

Because the project is a static HTML app, you can run it locally in a browser.

### Option 1: Open directly

Open `index.html` in your browser.

### Option 2: Use a local server

If you prefer running it through a simple local server:

```bash
python3 -m http.server 8000
```

Then open:

```text
http://localhost:8000
```

## How the Game Works

Each run is structured as a 30-day challenge split into 3 rounds.

- Days 1-5 of each round are `training` days
- Days 6-10 of each round are `testing` days
- Total per run: 15 training decisions and 15 AI test decisions

During training:

- The player sees one item at a time
- The player labels the item as `Need` or `Want`
- `Need` items are automatically bought
- `Want` items are automatically skipped
- The AI stores these examples as part of its learned pattern

During testing:

- The AI labels the item on its own
- If the AI labels it `Need`, the item is bought
- If the AI labels it `Want`, the item is skipped
- The player then answers whether the AI was right or wrong

Throughout the run, the player tries to balance two things:

- Train the AI accurately
- Avoid wasting money or going broke

## What the AI Does

WiseSpend AI uses a simple rule-based learning model rather than a full machine learning system.

The AI learns from:

- Overall counts of `Need` and `Want` labels
- Category-level patterns such as `food`, `school`, `safety`, `personal`, `games`, `devices`, and `media`
- Basic confidence adjustments based on training and test feedback

When making a test decision, the AI:

1. Checks whether it has seen that category before
2. Uses the majority label for that category if one exists
3. Falls back to the overall majority pattern if the category is unclear
4. Uses a built-in starter bias if there still is not enough training data

This makes the game useful for showing students that AI behavior depends on the examples it is given.

## Educational Purpose

WiseSpend AI is meant to help students:

- Practice distinguishing needs from wants
- See how spending choices affect a limited budget
- Understand that AI systems learn from examples and patterns
- Notice that bad training can produce bad automated decisions
- Reflect on why an AI may still make mistakes even after training

The game encourages students to think about both personal finance and how automated systems reason.

## Research Purpose

WiseSpend AI also supports classroom research on student thinking and AI-supported learning.

The project is set up to study questions such as:

- How students classify real-world items as needs or wants
- How students' labels influence later AI decisions
- Whether students understand that AI behavior comes from training patterns
- How students interpret AI mistakes
- How reflection and feedback affect their understanding of AI and budgeting

The software records structured session data so the gameplay can be analyzed after use.

## Scoring

The final score is based on both AI performance and money management.

- Base score: `40` points
- AI accuracy: up to `35` points
- Budget left: up to `25` points

Additional penalties may apply for:

- Mislabeling critical needs as wants
- Mislabeling clear needs as wants
- Mislabeling clear wants as needs
- Training the AI with too few need examples
- Finishing with a negative balance

Only a core set of scoring items is used for the main accuracy calculation, while other items still appear for gameplay and discussion.

## Features

- Single-page browser game with no build step required
- Player setup with name, grade, and avatar selection
- Three-round train/test structure
- AI confidence and decision feedback
- Reflection prompts during the experience
- Local leaderboard storage
- Session export with keyboard shortcut
- Research-friendly JSON session data

## Saving and Exporting

The app stores game state and leaderboard data in browser local storage.

- Leaderboard data is kept locally in the browser
- Session/player data can be exported as JSON

## Intended Audience

WiseSpend AI appears to be designed for middle school learners, especially in classroom settings where students are exploring:

- Financial literacy
- Needs vs. wants classification
- Introductory AI concepts
- Reflection on how training data affects automated decisions
