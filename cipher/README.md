# CipherQuest

A web-based interactive cryptography puzzle game where players decode encrypted messages across multiple difficulty levels using classical and modern cipher techniques.

## Description

CipherQuest is a single-page web application that challenges users to crack encrypted messages. It features four difficulty tiers (beginner to expert), 50 total challenges spanning cipher types like Caesar, Vigenere, Atbash, Morse Code, Binary, Base64, ROT13, Hexadecimal, and Leetspeak. The platform includes a built-in learning center, interactive cipher tools, and a local leaderboard to track progress.

## Features

- **50 Cipher Challenges** across 4 difficulty levels (Beginner: 5, Intermediate: 10, Advanced: 15, Expert: 20)
- **Supported Cipher Types**: Caesar, Vigenere, Atbash, Morse Code, Binary, Hexadecimal, Decimal ASCII, Base64, ROT13, Leetspeak, Pattern ciphers, and combination ciphers
- **Interactive Tools** for Caesar, Vigenere, Atbash, and Binary encoding/decoding
- **Learn Section** with detailed explanations, mathematical notation, and interactive demos for Caesar, Vigenere, and Morse Code
- **Hint System** with contextual hints for every challenge
- **Leaderboard** with persistent local storage, sorted by difficulty and level
- **Progress Tracking** per difficulty level using browser localStorage
- **Responsive Design** with dark terminal-style UI

## Installation

No installation required. This is a self-contained HTML file with no external dependencies.

```bash
git clone https://github.com/yourusername/cipherquest.git
cd cipherquest
```

Then open `cipherquest.html` in any modern web browser:

```bash
# Windows
start cipherquest.html

# macOS
open cipherquest.html

# Linux
xdg-open cipherquest.html
```

## Usage

1. Open `cipherquest.html` in a browser
2. Navigate to **Challenges**
3. Enter a username and click **Start**
4. Select a difficulty level (Beginner, Intermediate, Advanced, Expert)
5. Decode the encrypted message and type your answer
6. Click **Submit** to advance or use the **Show Hint** button if stuck
7. Track your progress via the **Leaderboard** tab
8. Use the **Tools** section to practice cipher techniques
9. Visit the **Learn** section for tutorials on each cipher type

### Cipher Tools

```javascript
// Caesar Cipher - shift each letter by a fixed number
caesarCipher("Hello", 3)   // "Khoor"

// Vigenere Cipher - shift by keyword characters
vigenereCipher("Hello", "KEY")  // "Rijvs"

// Atbash Cipher - reverse the alphabet (A↔Z, B↔Y)
atbashCipher("Hello")  // "Svool"
```

### Challenge Format

Each challenge follows this structure:

```javascript
{
    level: 1,
    encryptedMessage: "Khoor",
    hint: "This is a Caesar Cipher with a shift of 3...",
    solution: "Hello",
    cipherType: "Caesar"
}
```

## Project Structure

```
cipher/
├── cipherquest.html    # Main application (HTML + CSS + JS)
├── answers.txt         # Answer key for all 50 challenges
└── README.md           # Project documentation
```

## Configuration

No configuration files exist. The application uses `localStorage` for:

| Key | Purpose |
|-----|---------|
| `leaderboard` | Array of solver entries (name, level, difficulty, timestamp) |
| `currentLevel-{difficulty}` | Current progress per difficulty tier |

To reset progress, use the **Reset Progress** button in the Challenges section or clear browser localStorage manually:

```javascript
localStorage.clear();
```

## Dependencies

None. The application is built with vanilla HTML, CSS, and JavaScript. No frameworks, libraries, build tools, or package managers are required.

## Browser Compatibility

Works in all modern browsers that support:

- ES6 (arrow functions, template literals, `const`/`let`)
- localStorage API
- CSS Flexbox

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/new-cipher-type`)
3. Add challenges to the `challenges` object in `cipherquest.html` following the existing format
4. Update `answers.txt` with the corresponding answer key
5. Commit your changes (`git commit -m "Add new cipher challenges"`)
6. Push to the branch (`git push origin feature/new-cipher-type`)
7. Open a Pull Request

## License

Copyright (c) 2025 CipherQuest. All rights reserved. This project is provided for educational and entertainment purposes only.

## Contact

For issues, feature requests, or questions, open an issue on the GitHub repository.

## Acknowledgments

- Caesar cipher historically attributed to Julius Caesar
- Vigenere cipher invented by Blaise de Vigenere in the 16th century
- Morse code developed by Samuel Morse and Alfred Vail in the 1830s
