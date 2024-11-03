# Arduino Quiz Game

This project is a quiz game built with an Arduino, where questions and options are displayed on an LCD screen. The player can answer the questions using four buttons, and the results are indicated using LEDs and a buzzer.

## Components

- **Arduino Board** (e.g., Arduino Uno)
- **16x2 LCD Screen**: For displaying questions and answer options.
- **4 Push Buttons**: For selecting answers (A, B, C, D).
- **Green LED**: Lights up for a correct answer.
- **Red LED**: Lights up for an incorrect answer.
- **Buzzer**: Provides audio feedback for answers.

## Circuit Diagram

1. Connect the LCD to the Arduino following the LiquidCrystal library setup (pins 12, 11, 5, 4, 3, 2).
2. Connect each push button to digital pins 7, 8, 9, and 10 for options A, B, C, and D, respectively.
3. Connect the Green LED to pin 13 and the Red LED to pin 6.
4. Connect the Buzzer to pin 1.

## Code Overview

The code initializes an array of quiz questions, with each question containing:
- The question text
- Four answer options
- The correct answer

The main functions in the code:
- `scrollText()`: Scrolls text on the LCD screen for long questions.
- `displayQuestion()`: Displays each question and its options.
- `getAnswer()`: Reads button inputs to get the user’s selected answer.
- `checkAnswer()`: Checks the user’s answer, updates the score, and provides feedback via LEDs and the buzzer.

### Code Walkthrough

1. **Setup**: Initialize the LCD, LEDs, buzzer, and button pins.
2. **Loop**: For each question, display the question, wait for user input, check the answer, and display feedback.
3. **Quiz Completion**: After all questions, display the final score.

## How to Use

1. Upload the code to your Arduino.
2. Press the corresponding button for the answer you want to select:
   - Button A: Answer A
   - Button B: Answer B
   - Button C: Answer C
   - Button D: Answer D
3. After answering each question, you’ll receive feedback:
   - **Green LED** and a short beep for a correct answer.
   - **Red LED** and a long beep for an incorrect answer.
4. After all questions, the LCD displays your final score.

## Customizing the Quiz

You can modify the questions in the code by editing the `quiz` array. Each entry in the array should have the following structure:

```cpp
{"Question text?", {"A: Option1", "B: Option2", "C: Option3", "D: Option4"}, 'CorrectOptionLetter'}
