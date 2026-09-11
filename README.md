# Quiz CLI

An interactive Node.js command-line quiz game for learning and reviewing programming concepts. Users can select a quiz category, choose how many questions to answer, respond to multiple-choice questions, and receive immediate feedback with explanations.

The game currently includes questions covering:
- JavaScript Basics
- Node.js Fundamentals
- General Programming

> **Repository status:** The current `main` branch contains runtime path inconsistencies that must be corrected before the application can be started successfully. Details are provided in [Known Limitations](#known-limitations).

## Features
- Interactive command-line interface
- Three programming-focused quiz categories
- Five multiple-choice questions per category
- Configurable number of questions
- Immediate correct/incorrect feedback
- Explanations for quiz answers
- Final score and percentage summary
- Review of incorrect answers
- Option to replay the quiz
- Native Node.js implementation with no external runtime dependencies
- ES module syntax

## Tech Stack
- **Runtime:** Node.js 18 or later
- **Language:** JavaScript
- **Module system:** ECMAScript modules
- **Interface:** Command line
- **Dependencies:** None
- **Package manager:** npm
- **License:** MIT

## Prerequisites
Install Node.js version 18 or later and Git. Verify with:
```bash
node --version
```

## Installation
```bash
git clone https://github.com/fahmidAlam104/test-app.git
cd test-app
npm install
```
This project has no declared npm dependencies, so npm install is optional but conventional.

## Known Limitations
The committed repository currently has path issues. `index.js` imports `./src/input.js`, `./src/quiz.js`, and `./src/colors.js`, but the files are at the repository root. It also attempts to load `data/questions.json`, while `questions.json` is at the root. Therefore `npm start` is likely to fail until paths are corrected.

Either update `index.js` paths to `./input.js`, `./quiz.js`, `./colors.js`, and `./questions.json`, or move the files into:
```text
src/
├── colors.js
├── input.js
└── quiz.js

data/
└── questions.json
```

The root-level `download` file is not referenced by the app, is not readable as UTF-8, and has an undocumented purpose.
