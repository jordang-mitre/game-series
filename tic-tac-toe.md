Python Tic-Tac-Toe Workshop
Student Worksheet
Name: ______________________
Date: ______________________

Goal

In this workshop, you will:
- build a working Tic-Tac-Toe game in Python
- practice variables, lists, functions, loops, conditionals, and user input
- use Git to save your work often with small commits

What you need

- Python
- Git
- A code editor
- A terminal

Files for this project

- `tic_tac_toe.py`
- `README.md`
- `.gitignore`

Part 1: Project setup and first Git commit

Step 1
Create your project folder and move into it.

```bash
mkdir tic-tac-toe-python
cd tic-tac-toe-python
```

Step 2
Start a Git repository.

```bash
git init
```

Step 3
Create your files.

```bash
touch tic_tac_toe.py README.md .gitignore
```

If `touch` does not work on your computer, create the files in your editor.

Step 4
Add this to `.gitignore`.

```text
__pycache__/
*.pyc
```

Step 5
Add this to `README.md`.

```text
This is my beginner Python Tic-Tac-Toe project.
```

Step 6
Add this to `tic_tac_toe.py`.

```python
print("Welcome to Tic-Tac-Toe!")
```

Step 7
Run your program.

```bash
python tic_tac_toe.py
```

If needed, use `python3` instead.

Step 8
Make your first commit.

```bash
git status
git add .
git commit -m "Initial project setup"
```

Checkpoint questions

1. What does `git init` do?
Answer: ____________________________________________

2. What does `git status` show you?
Answer: ____________________________________________

3. What does `git add .` do?
Answer: ____________________________________________

4. What is a commit message?
Answer: ____________________________________________

Mini challenge

Change the welcome message so it includes your name.

Write the new line here:
____________________________________________________

Run the program again.

Make a new commit:

```bash
git add .
git commit -m "Update welcome message"
```

Part 2: Create the board

Add this to `tic_tac_toe.py`.

```python
board = [" ", " ", " ", " ", " ", " ", " ", " ", " "]

print("Welcome to Tic-Tac-Toe!")
print(board)
```

Run it.

What do you see?
____________________________________________________

Now change the board so there is an `X` in the center.

```python
board = [" ", " ", " ", " ", "X", " ", " ", " ", " "]

print("Welcome to Tic-Tac-Toe!")
print(board)
```

Checkpoint questions

1. How many items are in the board list?
Answer: ____________________________________________

2. Why is the center square `board[4]`?
Answer: ____________________________________________

3. What does `board[0]` mean?
Answer: ____________________________________________

Mini challenge

Put an `O` in the top-left square and an `X` in the bottom-right square.

Write your board here:
____________________________________________________

Commit your work.

```bash
git add .
git commit -m "Create board as a list of 9 squares"
```

Part 3: Print the board nicely

Replace your code with this.

```python
def print_board(board):
    print()
    print(board[0] + " | " + board[1] + " | " + board[2])
    print("--+---+--")
    print(board[3] + " | " + board[4] + " | " + board[5])
    print("--+---+--")
    print(board[6] + " | " + board[7] + " | " + board[8])
    print()

board = ["O", " ", " ", " ", "X", " ", " ", " ", "X"]

print("Welcome to Tic-Tac-Toe!")
print_board(board)
```

Now add this function too.

```python
def print_positions():
    print()
    print("1 | 2 | 3")
    print("--+---+--")
    print("4 | 5 | 6")
    print("--+---+--")
    print("7 | 8 | 9")
    print()
```

Use both functions.

```python
def print_board(board):
    print()
    print(board[0] + " | " + board[1] + " | " + board[2])
    print("--+---+--")
    print(board[3] + " | " + board[4] + " | " + board[5])
    print("--+---+--")
    print(board[6] + " | " + board[7] + " | " + board[8])
    print()

def print_positions():
    print()
    print("1 | 2 | 3")
    print("--+---+--")
    print("4 | 5 | 6")
    print("--+---+--")
    print("7 | 8 | 9")
    print()

board = ["O", " ", " ", " ", "X", " ", " ", " ", "X"]

print("Welcome to Tic-Tac-Toe!")
print("Board positions:")
print_positions()
print("Current board:")
print_board(board)
```

Checkpoint questions

1. What is a function?
Answer: ____________________________________________

2. What is the difference between `print_positions()` and `print_board(board)`?
Answer: ____________________________________________

3. Why do we pass `board` into `print_board(board)`?
Answer: ____________________________________________

Mini challenge

Change the sample board so the top row is `X O X`.

Write your board here:
____________________________________________________

Commit your work.

```bash
git add .
git commit -m "Add functions to print the board and positions"
```

Part 4: Get one player move

Replace your code with this.

```python
def print_board(board):
    print()
    print(board[0] + " | " + board[1] + " | " + board[2])
    print("--+---+--")
    print(board[3] + " | " + board[4] + " | " + board[5])
    print("--+---+--")
    print(board[6] + " | " + board[7] + " | " + board[8])
    print()

def print_positions():
    print()
    print("1 | 2 | 3")
    print("--+---+--")
    print("4 | 5 | 6")
    print("--+---+--")
    print("7 | 8 | 9")
    print()

board = [" ", " ", " ", " ", " ", " ", " ", " ", " "]

print("Welcome to Tic-Tac-Toe!")
print_positions()
print_board(board)

position = input("Player X, choose a position (1-9): ")
position = int(position)
index = position - 1
board[index] = "X"

print_board(board)
```

Checkpoint questions

1. What type of value does `input()` return at first?
Answer: ____________________________________________

2. Why do we use `int(position)`?
Answer: ____________________________________________

3. Why do we subtract `1`?
Answer: ____________________________________________

4. If the player types `9`, what index is used?
Answer: ____________________________________________

Mini challenge

Change the code so it asks for Player O and places `"O"` instead.

Write the changed line or lines here:
____________________________________________________
____________________________________________________

Commit your work.

```bash
git add .
git commit -m "Accept a single player move from input"
```

Part 5: Validate the move

Replace your move code with this function.

```python
def print_board(board):
    print()
    print(board[0] + " | " + board[1] + " | " + board[2])
    print("--+---+--")
    print(board[3] + " | " + board[4] + " | " + board[5])
    print("--+---+--")
    print(board[6] + " | " + board[7] + " | " + board[8])
    print()

def print_positions():
    print()
    print("1 | 2 | 3")
    print("--+---+--")
    print("4 | 5 | 6")
    print("--+---+--")
    print("7 | 8 | 9")
    print()

def make_move(board, player):
    while True:
        position = input(f"Player {player}, choose a position (1-9): ")

        if not position.isdigit():
            print("Please enter a number.")
            continue

        position = int(position)

        if position < 1 or position > 9:
            print("Please choose a number from 1 to 9.")
            continue

        index = position - 1
        board[index] = player
        break

board = [" ", " ", " ", " ", " ", " ", " ", " ", " "]

print("Welcome to Tic-Tac-Toe!")
print_positions()
print_board(board)
make_move(board, "X")
print_board(board)
```

Test these inputs:
- a letter
- `0`
- `10`
- `5`

What happened?
____________________________________________________
____________________________________________________

Now improve `make_move()` so players cannot choose a square that is already taken.

```python
def make_move(board, player):
    while True:
        position = input(f"Player {player}, choose a position (1-9): ")

        if not position.isdigit():
            print("Please enter a number.")
            continue

        position = int(position)

        if position < 1 or position > 9:
            print("Please choose a number from 1 to 9.")
            continue

        index = position - 1

        if board[index] != " ":
            print("That spot is already taken.")
            continue

        board[index] = player
        break
```

Checkpoint questions

1. What does `while True` do?
Answer: ____________________________________________

2. What does `continue` do?
Answer: ____________________________________________

3. What does `break` do?
Answer: ____________________________________________

4. Why do we check `board[index] != " "`?
Answer: ____________________________________________

Mini challenge

Pre-fill the center square with `"X"`, then try to choose position `5`.

Write your board here:
____________________________________________________

Did the program reject the move?
____________________________________________________

Commit your work.

```bash
git add .
git commit -m "Add move validation and prevent occupied squares"
```

Part 6: Git review

Check your Git history.

```bash
git log --oneline
```

Checkpoint questions

1. How many commits do you have so far?
Answer: ____________________________________________

2. What is the most recent commit message?
Answer: ____________________________________________

3. Why is it useful to commit often?
Answer: ____________________________________________

Mini challenge

Run:

```bash
git status
```

If Git says your working tree is clean, what does that mean?
Answer: ____________________________________________

Part 7: Alternate between players

Add this function.

```python
def switch_player(player):
    if player == "X":
        return "O"
    return "X"
```

Now use this full version.

```python
def print_board(board):
    print()
    print(board[0] + " | " + board[1] + " | " + board[2])
    print("--+---+--")
    print(board[3] + " | " + board[4] + " | " + board[5])
    print("--+---+--")
    print(board[6] + " | " + board[7] + " | " + board[8])
    print()

def print_positions():
    print()
    print("1 | 2 | 3")
    print("--+---+--")
    print("4 | 5 | 6")
    print("--+---+--")
    print("7 | 8 | 9")
    print()

def make_move(board, player):
    while True:
        position = input(f"Player {player}, choose a position (1-9): ")

        if not position.isdigit():
            print("Please enter a number.")
            continue

        position = int(position)

        if position < 1 or position > 9:
            print("Please choose a number from 1 to 9.")
            continue

        index = position - 1

        if board[index] != " ":
            print("That spot is already taken.")
            continue

        board[index] = player
        break

def switch_player(player):
    if player == "X":
        return "O"
    return "X"

board = [" ", " ", " ", " ", " ", " ", " ", " ", " "]
current_player = "X"

print("Welcome to Tic-Tac-Toe!")
print_positions()

for _ in range(9):
    print_board(board)
    make_move(board, current_player)
    current_player = switch_player(current_player)

print_board(board)
```

Checkpoint questions

1. Where is the current player stored?
Answer: ____________________________________________

2. Why are there at most 9 moves?
Answer: ____________________________________________

3. What does `_` mean in `for _ in range(9)`?
Answer: ____________________________________________

Mini challenge

Change the starting player to `"O"`. Did O go first?
____________________________________________________

Change it back after testing.

Commit your work.

```bash
git add .
git commit -m "Add turn taking and switch between players"
```

Part 8: Detect a winner

Add this function.

```python
def check_winner(board, player):
    winning_combinations = [
        [0, 1, 2],
        [3, 4, 5],
        [6, 7, 8],
        [0, 3, 6],
        [1, 4, 7],
        [2, 5, 8],
        [0, 4, 8],
        [2, 4, 6]
    ]

    for combo in winning_combinations:
        if board[combo[0]] == player and board[combo[1]] == player and board[combo[2]] == player:
            return True

    return False
```

Test it with this board.

```python
board = ["X", "X", "X", " ", "O", " ", " ", "O", " "]

print_board(board)
print(check_winner(board, "X"))
print(check_winner(board, "O"))
```

What result did you get for X?
____________________________________________________

What result did you get for O?
____________________________________________________

Now use it in the game loop.

```python
board = [" ", " ", " ", " ", " ", " ", " ", " ", " "]
current_player = "X"

print("Welcome to Tic-Tac-Toe!")
print_positions()

for _ in range(9):
    print_board(board)
    make_move(board, current_player)

    if check_winner(board, current_player):
        print_board(board)
        print(f"Player {current_player} wins!")
        break

    current_player = switch_player(current_player)
```

Checkpoint questions

1. What does `check_winner(board, "X")` mean?
Answer: ____________________________________________

2. Why do we check for a win right after a move?
Answer: ____________________________________________

3. What does `return True` do?
Answer: ____________________________________________

Mini challenge

Create a board where O wins on a diagonal.

Write it here:
____________________________________________________

Did `check_winner(board, "O")` return `True`?
____________________________________________________

Commit your work.

```bash
git add .
git commit -m "Add winner detection"
```

Part 9: Detect a tie

Add this function.

```python
def check_tie(board):
    return " " not in board
```

Add it to the game loop.

```python
board = [" ", " ", " ", " ", " ", " ", " ", " ", " "]
current_player = "X"

print("Welcome to Tic-Tac-Toe!")
print_positions()

for _ in range(9):
    print_board(board)
    make_move(board, current_player)

    if check_winner(board, current_player):
        print_board(board)
        print(f"Player {current_player} wins!")
        break

    if check_tie(board):
        print_board(board)
        print("It's a tie!")
        break

    current_player = switch_player(current_player)
```

Checkpoint questions

1. What does `" " not in board` mean?
Answer: ____________________________________________

2. Why do we check for a winner before a tie?
Answer: ____________________________________________

3. Can the board be full and still have a winner?
Answer: ____________________________________________

Mini challenge

Make a full board with no winner.

Write it here:
____________________________________________________

Did `check_tie(board)` return `True`?
____________________________________________________

Commit your work.

```bash
git add .
git commit -m "Add tie detection"
```

Part 10: Final working game

Replace your file with this full version.

```python
def print_board(board):
    print()
    print(board[0] + " | " + board[1] + " | " + board[2])
    print("--+---+--")
    print(board[3] + " | " + board[4] + " | " + board[5])
    print("--+---+--")
    print(board[6] + " | " + board[7] + " | " + board[8])
    print()

def print_positions():
    print()
    print("1 | 2 | 3")
    print("--+---+--")
    print("4 | 5 | 6")
    print("--+---+--")
    print("7 | 8 | 9")
    print()

def make_move(board, player):
    while True:
        position = input(f"Player {player}, choose a position (1-9): ")

        if not position.isdigit():
            print("Please enter a number.")
            continue

        position = int(position)

        if position < 1 or position > 9:
            print("Please choose a number from 1 to 9.")
            continue

        index = position - 1

        if board[index] != " ":
            print("That spot is already taken.")
            continue

        board[index] = player
        break

def switch_player(player):
    if player == "X":
        return "O"
    return "X"

def check_winner(board, player):
    winning_combinations = [
        [0, 1, 2],
        [3, 4, 5],
        [6, 7, 8],
        [0, 3, 6],
        [1, 4, 7],
        [2, 5, 8],
        [0, 4, 8],
        [2, 4, 6]
    ]

    for combo in winning_combinations:
        if board[combo[0]] == player and board[combo[1]] == player and board[combo[2]] == player:
            return True

    return False

def check_tie(board):
    return " " not in board

def play_game():
    board = [" ", " ", " ", " ", " ", " ", " ", " ", " "]
    current_player = "X"

    print("Welcome to Tic-Tac-Toe!")
    print("Choose positions like this:")
    print_positions()

    while True:
        print_board(board)
        make_move(board, current_player)

        if check_winner(board, current_player):
            print_board(board)
            print(f"Player {current_player} wins!")
            break

        if check_tie(board):
            print_board(board)
            print("It's a tie!")
            break

        current_player = switch_player(current_player)

play_game()
```

Play a full game.

Checkpoint questions

1. Which function runs the whole game?
Answer: ____________________________________________

2. Which function gets a move from the player?
Answer: ____________________________________________

3. Which function switches players?
Answer: ____________________________________________

4. Which functions check whether the game is over?
Answer: ____________________________________________

Mini challenge

Change one small part of the game:
- the welcome message
- the board divider lines
- the starting player

What did you change?
____________________________________________________

Commit your final version.

```bash
git add .
git commit -m "Finish working command line Tic-Tac-Toe game"
```

Git practice summary

Run these commands:

```bash
git status
git log --oneline
git diff
```

Write what each one does.

`git status`
____________________________________________________

`git log --oneline`
____________________________________________________

`git diff`
____________________________________________________

Optional extension: Play again

If you have time, add this feature.

```python
def play_again():
    answer = input("Play again? (y/n): ").lower()
    return answer == "y"

while True:
    play_game()
    if not play_again():
        print("Thanks for playing!")
        break
```

If you add it, commit it.

```bash
git add .
git commit -m "Add play again option"
```

Final reflection

1. What part of the game was easiest for you?
____________________________________________________

2. What part was hardest?
____________________________________________________

3. What did you learn about lists?
____________________________________________________

4. What did you learn about functions?
____________________________________________________

5. What did you learn about loops?
____________________________________________________

6. What did you learn about Git?
____________________________________________________

7. Why is committing often a good habit?
____________________________________________________

8. If you kept working on this project, what would you add next?
____________________________________________________

Challenge ideas for later

- Keep score across multiple games
- Add a computer player
- Improve the board layout
- Let the player quit with `q`
- Save game results to a file
