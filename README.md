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

## Running the Project
Once paths are corrected:
```bash
npm start
```
Or:
```bash
node index.js
```
Expected flow: choose a category, select question count, answer questions, view immediate feedback and explanations, review the score and incorrect answers, and choose whether to play again.

## Available npm Scripts
### Start
```bash
npm start
```
Runs `node index.js`.

### Tests
```bash
npm test
```
Runs `node --test`. No automated test files are currently present, so there is no committed test suite or coverage.

## Project Structure
```text
.
├── colors.js       # Terminal color and formatting utilities
├── download        # Unreferenced binary or non-UTF-8 file
├── index.js        # Application entry point
├── input.js        # Interactive command-line input handling
├── package.json    # Project metadata and npm scripts
├── questions.json  # Quiz categories and question data
└── quiz.js         # Quiz flow, scoring, and answer processing
```

## Question Data
`questions.json` stores quiz content by category. Each question contains question text, multiple choices, the correct answer, and an explanation. Preserve valid JSON, the existing category structure, consistent property names, multiple choices, and an explanation for every question when editing data.

## Development
The project uses native Node.js APIs and ECMAScript modules, configured via `"type": "module"`. Ensure local imports include `.js`, point to existing files, and that the question-data path matches the actual location. Preserve the interactive flow and test all categories when modifying the app.

## Testing Status
`npm test` is configured but no automated test files are present. Contributions should consider tests for question loading, category selection, input validation, score and percentage calculation, incorrect-answer tracking, and replay behavior. Until then, test manually by running the quiz through each path after fixing the path issues.

## Troubleshooting
- **Cannot find module:** Ensure `index.js` imports match the root file locations or move files into `src/`.
- **Question file not found:** Ensure the data path matches the root `questions.json` or move it to `data/`.
- **Import/module syntax error:** Use Node.js 18+ and keep `"type": "module"` in `package.json`.
- **No packages installed:** Expected because there are no external dependencies.

## Contributing
1. Fork the repository.
2. Create a feature branch: `git checkout -b feature/your-change`
3. Make and manually verify changes.
4. Add or update tests where appropriate.
5. Commit and push the branch.
6. Open a pull request.

Keep question data valid, preserve the CLI experience, and document setup or structure changes.

## License
This project is licensed under the MIT License, as specified in `package.json`.
