# Tic-Tac-Toe
A simple and interactive Tic Tac Toe game built using HTML, CSS, and JavaScript.

Features:

    Two-player mode: Play with a friend on the same device.
    
    Responsive design: Works seamlessly on desktops and mobile devices.
    
    Real-time feedback: Highlights the winning combination and displays the winner.
    
    Restart game: Easily restart the game with a single click.
How to Play

    Open the game in your browser.
    
    Player 1 and Player 2 take turns clicking on the grid to place their mark (X or O).
    
    The first player to get three of their marks in a row (horizontally, vertically, or diagonally) wins!
    
    Click "Restart" to play again.
Tech Stack
    HTML: For creating the structure of the game.
    
    CSS: For styling the game board and making it visually appealing.
    
    JavaScript: For game logic and interactivity.


# 🎮 Tic-Tac-Toe Game  

A simple **Tic-Tac-Toe game** built using **HTML, CSS, and JavaScript**. The game allows two players (X and O) to take turns, checks for winners based on predefined patterns, and provides reset/new game options.  

---

## 🚀 Features  
- Two-player mode (X vs O)  
- Winner detection using predefined win patterns  
- Reset and New Game functionality  
- Disables boxes once selected to prevent overwriting  
- Displays a congratulatory message for the winner  

---

## 🛠️ Technologies Used  
- **HTML5** → Structure of the game board  
- **CSS3** → Styling the board and buttons  
- **JavaScript (Vanilla JS)** → Game logic, event handling, DOM manipulation  

---

## 📂 Project Structure  



---

## ⚡ Core Logic  

### 1. **Game State Management**
```js
if(turnO) {
    box.innerText = "O";
    turnO = false;
} else {
    box.innerText = "X";
    turnO = true;
}
box.disabled = true;



# win patterns
const winPatterns = [
  [0,1,2], [3,4,5], [6,7,8],   // Rows
  [0,3,6], [1,4,7], [2,5,8],   // Columns
  [0,4,8], [2,4,6]             // Diagonals
];

# winner detection

const checkwinner = () => {
  for (let pattern of winPatterns) {
    let [a, b, c] = pattern;
    if (
      boxes[a].innerText !== "" &&
      boxes[a].innerText === boxes[b].innerText &&
      boxes[b].innerText === boxes[c].innerText
    ) {
      showWinner(boxes[a].innerText);
    }
  }
};

# reset and new game
const resetGame = () => {
  turnO = true;
  enableBoxes();
  msgContainer.classList.add("hide");
};





## ❓ FAQ / Interview Questions  

### 1. How is the winner detected?  
The game checks predefined **winning patterns** (rows, columns, diagonals) after each move.  
If three boxes in a pattern contain the same non-empty value (`"X"` or `"O"`), that player is declared the winner.  

```js
if (
  boxes[a].innerText !== "" &&
  boxes[a].innerText === boxes[b].innerText &&
  boxes[b].innerText === boxes[c].innerText
) {
  showWinner(boxes[a].innerText);
}

2. Why do we disable boxes after a click?

To prevent a player from overwriting a move.
Once clicked, a box is disabled (box.disabled = true), ensuring fairness and proper turn-taking.

3. What data structure is used to store win conditions?

A 2D array (winPatterns) is used, where each sub-array represents a possible winning line.

const winPatterns = [
  [0,1,2], [3,4,5], [6,7,8],   // Rows
  [0,3,6], [1,4,7], [2,5,8],   // Columns
  [0,4,8], [2,4,6]             // Diagonals
];

4. How is the game state (turn tracking) managed?

A boolean variable turnO keeps track of whose turn it is.

true → O’s turn

false → X’s turn
It toggles after every valid move.

if(turnO) {
  box.innerText = "O";
  turnO = false;
} else {
  box.innerText = "X";
  turnO = true;
}




5. Difference between Reset Game and New Game buttons?

Reset Game: Clears the board but continues in the same session.

New Game: Clears the board and hides the winner message (starts a fresh session).

Both use the same resetGame() logic, but the New Game button only appears after a winner is declared.

6. How can you extend this project (like adding AI to play against computer)?

Possible improvements:

AI Opponent (minimax algorithm or random moves).

Draw Detection (when all boxes are filled with no winner).

Scoreboard (track wins for X and O).

Responsive UI for mobile devices.

Multiplayer Online using WebSo


