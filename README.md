# Gujarati Input Tools for macOS

[![Build Status](https://github.com/lennylxx/google-input-tools-macos/actions/workflows/build.yml/badge.svg?branch=main)](https://github.com/lennylxx/google-input-tools-macos/actions/workflows/build.yml?query=branch%3Amain)

A *cloud* input method that uses [Google Input Tools](https://www.google.com/inputtools/) as engine for macOS to type in Gujarati.

## How to use

1. Install Xcode 12.5.0+.

2. Clone and build the project.

  ```
  git clone https://github.com/lennylxx/google-input-tools-macos
  cd google-input-tools-macos
  ./build.sh
  ``` 

> The output will be `~/Library/Input\ Methods/GoogleInputTools.app`

3. Open `System Preferences` -> `Keyboard` -> `Input Sources`, click `+` to add a new input method, choose `Gujarati` -> `Gujarati Input Tools`.

4. If you want to remove it, simply run below command.

  ```
  rm -rf ~/Library/Input\ Methods/GoogleInputTools.app
  rm -rf ~/Library/Input\ Methods/GoogleInputTools.swiftmodule
  ```

## Screenshot
The input method will show Gujarati candidates when you type English letters. For example, typing "namaste" will show "નમસ્તે" as a candidate.

## Progress

- [x] Basic input handling logic
  - [x] `Space` key to commit current highlighted candidate
  - [x] `Return` key to ignore candidate and commit input string
  - [x] Number keys (`1`-`9`) to select candidate and commit
  - [x] Continue to show new candidates after partial matched candidate is selected and committed
  - [x] `Backspace` key to remove last composing letter
  - [x] `Esc` key to cancel composing
  - [ ] `-` and `=` keys to page up and page down candidate list respectively
- [x] System UI
- [x] Basic custom UI
  - [x] Numbered candidates
  - [x] Highlight current selected candidate
  - [ ] Arrow keys to switch between highlighted candidate
  - [ ] Group candidates into multiple pages, each page with at most `10` candidates
  - [ ] Page up and page down button
  - [ ] Draggable candidate window
- [ ] Advanced custom UI
  - [ ] Display tokenized input string and candidates
  - [ ] Settings for font name, font size, color, etc.
  - [ ] Skin display
  - [ ] Skin manager
- [x] Cloud engine
  - [ ] Cancel previous unnecessary web requests to speed up
- [ ] Gujarati/English mode toggle
- [ ] Fullwidth form of punctuation in Gujarati mode
- [ ] Input tool switching, such as Phonetic, InScript, etc.
- [ ] Allow to use HTTP/SOCKS proxy

## Input Methods Available

- **Gujarati (Default)**: Standard Gujarati transliteration
- **Gujarati Phonetic**: Phonetic-based input method
- **Gujarati InScript**: InScript keyboard layout for Gujarati

You can change the input method by modifying the `_inputTool` property in `CloudInputEngine.swift`.