# Typewright

A small browser-based typing test built with plain HTML, CSS, and JavaScript.

Typewright is a typing practice app with different test modes, races, drills, statistics, achievements, and local progress tracking.

## Features

* 15, 30, 60, and 120 second typing tests
* Easy, medium, and hard difficulty
* Flow mode for normal typing practice
* Drill mode for practicing commonly missed keys
* Solo races against up to four bots
* Pass-and-play mode for 2–4 players
* Optional punctuation
* Live WPM and accuracy
* Raw WPM and consistency statistics
* Speed-over-time graph
* Recent test history
* Personal records
* Keyboard error heatmap
* 14 achievements
* Sound effects with adjustable volume
* Export and import of progress as JSON
* Responsive layout
* No account or backend required

## Running the project

There is no build step or package manager required.

Simply open the HTML file in a modern browser:

```text
index.html
```

JavaScript needs to be enabled for the app to work.

You can also use a simple local web server if you prefer.

## How to use

Choose a test duration and difficulty, then start typing.

The timer starts when you type the first character. Your WPM and accuracy are updated while you type. Once the test ends, Typewright displays your results and statistics.

### Flow mode

Flow is the normal typing mode. Text is generated from the built-in word lists and quote collection.

### Drill mode

Drill mode uses your previous typing mistakes to generate practice text containing keys that you have struggled with.

It works better after you have completed a few normal typing tests.

### Race mode

You can race against 1–4 computer-controlled opponents.

The bot speeds are based on stored performance data.

### PvP mode

PvP is a pass-and-play mode for multiple players using the same keyboard.

Each player gets the same text and takes their turn before the results are compared.

## Results and statistics

After completing a test, Typewright shows:

* Net WPM
* Accuracy
* Raw WPM
* Consistency
* Total keystrokes
* Test duration
* Speed-over-time graph
* Problem keys when enough data is available

WPM uses the standard five-characters-per-word calculation.

## The Ledger

Typewright stores your progress in the browser.

The ledger keeps track of things such as:

* Best WPM
* Best accuracy
* Tests completed
* Total typing time
* Race wins
* Drill sessions
* Day streak
* Recent tests
* Key hits and errors
* Achievement progress

The data is stored using `localStorage`.

The current storage key is:

```text
typewright.v2
```

There is also a migration path for older `typewright.v1` data.

## Export and import

You can export your current ledger as a JSON file.

The exported file is named:

```text
typewright-ledger.json
```

The JSON file can later be imported to restore your progress.

This can also be useful for keeping a backup or moving your data to another browser.

## Clearing progress

The **clear the ledger** option removes the stored Typewright data after confirmation.

This removes your history, achievements, records, and key statistics.

If you want to keep your progress, export the ledger before clearing it.

## Keyboard shortcuts

| Key                    | Action                                     |
| ---------------------- | ------------------------------------------ |
| `Tab`                  | Restart the test                           |
| `Esc`                  | Restart the test                           |
| `Enter`                | Start another test from the results screen |
| `Backspace`            | Delete the previous character              |
| `Ctrl/Cmd + Backspace` | Clear the current word                     |

## Text generation

Typewright includes several built-in text sources:

* Common words for easier tests
* Harder vocabulary
* Short quotes
* JavaScript code snippets for hard mode

The text is generated directly in the browser.

No external text-generation API is required.

Drill mode uses the stored key error rates to select words containing frequently missed characters.

## Achievements

Typewright includes 14 achievements covering things such as:

* Completing your first test
* Reaching 30, 50, 70, and 100 WPM
* Getting a flawless test
* Completing a 120-second test
* Reaching 60+ WPM in a sprint
* Building a three-day streak
* Completing 25 tests
* Finishing a hard test
* Winning a bot race
* Maintaining high accuracy
* Completing five drill sessions

Unlocked achievements are stored locally and displayed in the Ledger.

## Technologies used

Typewright keeps the technology stack simple:

* HTML
* CSS
* Vanilla JavaScript
* `localStorage`
* Web Audio API
* SVG
* Lucide Icons
* Google Fonts

There is no framework, bundler, database, or backend.

## Project structure

The current version is a single-page application:

```text
.
└── index.html
```

The HTML file contains the markup, styles, word lists, application logic, statistics, storage, race system, PvP system, and UI.

If the project is split into separate files later, it could look like:

```text
.
├── index.html
├── styles.css
└── script.js
```

## Browser storage

Typewright keeps user data locally in the browser.

Test history, settings, achievements, and statistics are not stored on a Typewright server.

The page does load external resources such as fonts and the Lucide icon library.

## License

This project is licensed under the MIT License.

You are free to use, copy, modify, merge, publish, distribute, sublicense, and sell copies of the software, subject to the conditions of the license.

### MIT License

```text
MIT License

Copyright (c) 2026 Typewright

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```
