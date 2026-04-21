Python Hangman Workshop
Student Worksheet

Name: ______________________

Date: ______________________

Goal

In this workshop, you will:
- build a working Hangman game in Python
- practice variables, strings, lists, functions, loops, conditionals, and user input
- use Git to save your work often with small commits

What you need

- Python
- Git
- A code editor
- A terminal

Files for this project

- `hangman.py`
- `README.md`
- `.gitignore`

Part 1: Project setup and first Git commit

Step 1

Create your project folder and move into it.

```bash
mkdir hangman-python
cd hangman-python
```

Step 2

Start a Git repository.

```bash
git init
```

Step 3

Create your files.

```bash
touch hangman.py README.md .gitignore
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
This is my beginner Python Hangman project.
```

Step 6

Add this to `hangman.py`.

```python
print("Welcome to Hangman!")
```

Step 7

Run your program.

```bash
python hangman.py
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

Write your new line here:

____________________________________________________

Run the program again.

Make a new commit.

```bash
git add .
git commit -m "Update welcome message"
```

Part 2: Create the secret word and hidden display

Add this to `hangman.py`.

```python
secret_word = "python"

print("Welcome to Hangman!")
print("The secret word is:")
print(secret_word)
```

Run it.

What do you see?

____________________________________________________

Now replace it with this version that hides the word.

```python
secret_word = "python"

print("Welcome to Hangman!")
print("The word has", len(secret_word), "letters.")
print("_ " * len(secret_word))
```

Run it again.

Checkpoint questions

1. What kind of value is `"python"`?

Answer: ____________________________________________

2. What does `len(secret_word)` return?

Answer: ____________________________________________

3. If the word is `"cat"`, what will `"_ " * len(secret_word)` print?

Answer: ____________________________________________

Mini challenge

Change the secret word to `"coding"`.

What output do you get now?

____________________________________________________

Commit your work.

```bash
git add .
git commit -m "Add starter Hangman word and hidden display"
```

Part 3: Track guessed letters

Replace your code with this.

```python
secret_word = "python"
guessed_letters = ["p", "o"]

print("Welcome to Hangman!")
print("Secret word:", secret_word)
print("Guessed letters:", guessed_letters)
```

Run it.

What is stored in `guessed_letters`?

____________________________________________________

Now replace your code with this function version.

```python
def display_word(secret_word, guessed_letters):
    display = ""

    for letter in secret_word:
        if letter in guessed_letters:
            display += letter + " "
        else:
            display += "_ "

    return display

secret_word = "python"
guessed_letters = ["p", "o"]

print("Welcome to Hangman!")
print(display_word(secret_word, guessed_letters))
```

Run it.

What did the display look like?

____________________________________________________

Checkpoint questions

1. What is a list?

Answer: ____________________________________________

2. What does `for letter in secret_word` do?

Answer: ____________________________________________

3. What does `if letter in guessed_letters` mean?

Answer: ____________________________________________

4. What does `return` do?

Answer: ____________________________________________

Mini challenge

Change `guessed_letters` to:

```python
["p", "y", "t"]
```

Before running it, predict the output.

Prediction: _________________________________________

Actual output: ______________________________________

Commit your work.

```bash
git add .
git commit -m "Add guessed letters list and display function"
```

Part 4: Let the player guess one letter

Replace your code with this.

```python
def display_word(secret_word, guessed_letters):
    display = ""

    for letter in secret_word:
        if letter in guessed_letters:
            display += letter + " "
        else:
            display += "_ "

    return display

secret_word = "python"
guessed_letters = []

print("Welcome to Hangman!")
print(display_word(secret_word, guessed_letters))

guess = input("Guess a letter: ")
guessed_letters.append(guess)

print("You guessed:", guess)
print(display_word(secret_word, guessed_letters))
```

Run it and enter a letter.

What happened after you guessed?

____________________________________________________

Checkpoint questions

1. What does `input()` return?

Answer: ____________________________________________

2. What does `.append()` do?

Answer: ____________________________________________

3. What happens if the guessed letter is in the word?

Answer: ____________________________________________

4. What happens if the guessed letter is not in the word?

Answer: ____________________________________________

Mini challenge

Guess a letter that is not in the word.

What does the display look like?

____________________________________________________

Why?

____________________________________________________

Commit your work.

```bash
git add .
git commit -m "Accept one guessed letter from the user"
```

Part 5: Validate the guess

Replace your code with this.

```python
def display_word(secret_word, guessed_letters):
    display = ""

    for letter in secret_word:
        if letter in guessed_letters:
            display += letter + " "
        else:
            display += "_ "

    return display

def get_guess(guessed_letters):
    while True:
        guess = input("Guess a letter: ").lower()

        if len(guess) != 1:
            print("Please enter exactly one letter.")
            continue

        if not guess.isalpha():
            print("Please enter a letter.")
            continue

        if guess in guessed_letters:
            print("You already guessed that letter.")
            continue

        return guess

secret_word = "python"
guessed_letters = []

print("Welcome to Hangman!")
print(display_word(secret_word, guessed_letters))

guess = get_guess(guessed_letters)
guessed_letters.append(guess)

print("You guessed:", guess)
print(display_word(secret_word, guessed_letters))
```

Test these inputs:
- `ab`
- `5`
- `!`
- one valid letter
- a repeated letter

What happened in each case?

`ab`: _______________________________________________

`5`: ________________________________________________

`!`: ________________________________________________

valid letter: ________________________________________

repeated letter: ____________________________________

Checkpoint questions

1. What does `while True` do?

Answer: ____________________________________________

2. Why do we use `.lower()`?

Answer: ____________________________________________

3. Why do we check `len(guess) != 1`?

Answer: ____________________________________________

4. Why do we check `guess in guessed_letters`?

Answer: ____________________________________________

Mini challenge

Remove `.lower()` and test uppercase input.

What changes?

____________________________________________________

Put `.lower()` back after testing.

Commit your work.

```bash
git add .
git commit -m "Add guess validation"
```

Part 6: Git review

Run this command.

```bash
git log --oneline
```

Checkpoint questions

1. How many commits do you have so far?

Answer: ____________________________________________

2. What is your most recent commit message?

Answer: ____________________________________________

3. Why is it useful to commit often?

Answer: ____________________________________________

Mini challenge

Run this command.

```bash
git status
```

If Git says your working tree is clean, what does that mean?

Answer: ____________________________________________

Part 7: Repeat guessing in a loop

Replace your code with this.

```python
def display_word(secret_word, guessed_letters):
    display = ""

    for letter in secret_word:
        if letter in guessed_letters:
            display += letter + " "
        else:
            display += "_ "

    return display

def get_guess(guessed_letters):
    while True:
        guess = input("Guess a letter: ").lower()

        if len(guess) != 1:
            print("Please enter exactly one letter.")
            continue

        if not guess.isalpha():
            print("Please enter a letter.")
            continue

        if guess in guessed_letters:
            print("You already guessed that letter.")
            continue

        return guess

secret_word = "python"
guessed_letters = []

print("Welcome to Hangman!")

for _ in range(6):
    print()
    print("Word:", display_word(secret_word, guessed_letters))
    guess = get_guess(guessed_letters)
    guessed_letters.append(guess)
    print("Guessed letters:", guessed_letters)
```

Run it.

What changes each time through the loop?

____________________________________________________

Now replace your code with this version that tracks wrong guesses.

```python
def display_word(secret_word, guessed_letters):
    display = ""

    for letter in secret_word:
        if letter in guessed_letters:
            display += letter + " "
        else:
            display += "_ "

    return display

def get_guess(guessed_letters):
    while True:
        guess = input("Guess a letter: ").lower()

        if len(guess) != 1:
            print("Please enter exactly one letter.")
            continue

        if not guess.isalpha():
            print("Please enter a letter.")
            continue

        if guess in guessed_letters:
            print("You already guessed that letter.")
            continue

        return guess

secret_word = "python"
guessed_letters = []
wrong_guesses = 0
max_wrong_guesses = 6

print("Welcome to Hangman!")

while wrong_guesses < max_wrong_guesses:
    print()
    print("Word:", display_word(secret_word, guessed_letters))
    print("Wrong guesses left:", max_wrong_guesses - wrong_guesses)

    guess = get_guess(guessed_letters)
    guessed_letters.append(guess)

    if guess not in secret_word:
        wrong_guesses += 1
        print("That letter is not in the word.")
    else:
        print("Good guess!")
```

Checkpoint questions

1. What is the difference between the `for` loop and the `while` loop here?

Answer: ____________________________________________

2. What does `if guess not in secret_word` mean?

Answer: ____________________________________________

3. When does `wrong_guesses` increase?

Answer: ____________________________________________

4. Why do we need both `wrong_guesses` and `max_wrong_guesses`?

Answer: ____________________________________________

Mini challenge

Change `max_wrong_guesses` from `6` to `8`.

What changed when you ran the game?

____________________________________________________

Commit your work.

```bash
git add .
git commit -m "Add game loop and wrong guess counter"
```

Part 8: Detect a win or loss

Add this function.

```python
def is_word_guessed(secret_word, guessed_letters):
    for letter in secret_word:
        if letter not in guessed_letters:
            return False
    return True
```

Test it with this code.

```python
def display_word(secret_word, guessed_letters):
    display = ""

    for letter in secret_word:
        if letter in guessed_letters:
            display += letter + " "
        else:
            display += "_ "

    return display

def is_word_guessed(secret_word, guessed_letters):
    for letter in secret_word:
        if letter not in guessed_letters:
            return False
    return True

secret_word = "python"
guessed_letters = ["p", "y", "t", "h", "o", "n"]

print(display_word(secret_word, guessed_letters))
print(is_word_guessed(secret_word, guessed_letters))
```

What did `is_word_guessed()` return?

____________________________________________________

Now replace your code with this full version.

```python
def display_word(secret_word, guessed_letters):
    display = ""

    for letter in secret_word:
        if letter in guessed_letters:
            display += letter + " "
        else:
            display += "_ "

    return display

def get_guess(guessed_letters):
    while True:
        guess = input("Guess a letter: ").lower()

        if len(guess) != 1:
            print("Please enter exactly one letter.")
            continue

        if not guess.isalpha():
            print("Please enter a letter.")
            continue

        if guess in guessed_letters:
            print("You already guessed that letter.")
            continue

        return guess

def is_word_guessed(secret_word, guessed_letters):
    for letter in secret_word:
        if letter not in guessed_letters:
            return False
    return True

secret_word = "python"
guessed_letters = []
wrong_guesses = 0
max_wrong_guesses = 6

print("Welcome to Hangman!")

while wrong_guesses < max_wrong_guesses:
    print()
    print("Word:", display_word(secret_word, guessed_letters))
    print("Wrong guesses left:", max_wrong_guesses - wrong_guesses)

    guess = get_guess(guessed_letters)
    guessed_letters.append(guess)

    if guess not in secret_word:
        wrong_guesses += 1
        print("That letter is not in the word.")
    else:
        print("Good guess!")

    if is_word_guessed(secret_word, guessed_letters):
        print()
        print("Word:", display_word(secret_word, guessed_letters))
        print("You win!")
        break

if not is_word_guessed(secret_word, guessed_letters):
    print()
    print("You lose!")
    print("The word was:", secret_word)
```

Checkpoint questions

1. What does `is_word_guessed()` check?

Answer: ____________________________________________

2. Why do we check for a win after a guess?

Answer: ____________________________________________

3. What happens if the player runs out of guesses?

Answer: ____________________________________________

4. Why do we show the secret word when the player loses?

Answer: ____________________________________________

Mini challenge

Change the secret word to `"git"` and win the game.

What happened?

____________________________________________________

Commit your work.

```bash
git add .
git commit -m "Add win and lose conditions"
```

Part 9: Choose a random word from a list

Replace your code with this.

```python
import random

def display_word(secret_word, guessed_letters):
    display = ""

    for letter in secret_word:
        if letter in guessed_letters:
            display += letter + " "
        else:
            display += "_ "

    return display

def get_guess(guessed_letters):
    while True:
        guess = input("Guess a letter: ").lower()

        if len(guess) != 1:
            print("Please enter exactly one letter.")
            continue

        if not guess.isalpha():
            print("Please enter a letter.")
            continue

        if guess in guessed_letters:
            print("You already guessed that letter.")
            continue

        return guess

def is_word_guessed(secret_word, guessed_letters):
    for letter in secret_word:
        if letter not in guessed_letters:
            return False
    return True

words = ["python", "coding", "git", "function", "loop", "string", "variable"]
secret_word = random.choice(words)

guessed_letters = []
wrong_guesses = 0
max_wrong_guesses = 6

print("Welcome to Hangman!")

while wrong_guesses < max_wrong_guesses:
    print()
    print("Word:", display_word(secret_word, guessed_letters))
    print("Wrong guesses left:", max_wrong_guesses - wrong_guesses)

    guess = get_guess(guessed_letters)
    guessed_letters.append(guess)

    if guess not in secret_word:
        wrong_guesses += 1
        print("That letter is not in the word.")
    else:
        print("Good guess!")

    if is_word_guessed(secret_word, guessed_letters):
        print()
        print("Word:", display_word(secret_word, guessed_letters))
        print("You win!")
        break

if not is_word_guessed(secret_word, guessed_letters):
    print()
    print("You lose!")
    print("The word was:", secret_word)
```

Run the game a few times.

Checkpoint questions

1. What is `words`?

Answer: ____________________________________________

2. What does `random.choice(words)` do?

Answer: ____________________________________________

3. Why is a list useful here?

Answer: ____________________________________________

4. What happens if you add more words?

Answer: ____________________________________________

Mini challenge

Add 3 new words to the list.

Write them here:

1. _________________________________________________

2. _________________________________________________

3. _________________________________________________

Did one of your new words appear when you played?

____________________________________________________

Commit your work.

```bash
git add .
git commit -m "Choose a random word from a list"
```

Part 10: Final working game

Replace your file with this full version.

```python
import random

def display_word(secret_word, guessed_letters):
    display = ""

    for letter in secret_word:
        if letter in guessed_letters:
            display += letter + " "
        else:
            display += "_ "

    return display

def get_guess(guessed_letters):
    while True:
        guess = input("Guess a letter: ").lower()

        if len(guess) != 1:
            print("Please enter exactly one letter.")
            continue

        if not guess.isalpha():
            print("Please enter a letter.")
            continue

        if guess in guessed_letters:
            print("You already guessed that letter.")
            continue

        return guess

def is_word_guessed(secret_word, guessed_letters):
    for letter in secret_word:
        if letter not in guessed_letters:
            return False
    return True

def choose_word():
    words = ["python", "coding", "git", "function", "loop", "string", "variable"]
    return random.choice(words)

def play_game():
    secret_word = choose_word()
    guessed_letters = []
    wrong_guesses = 0
    max_wrong_guesses = 6

    print("Welcome to Hangman!")

    while wrong_guesses < max_wrong_guesses:
        print()
        print("Word:", display_word(secret_word, guessed_letters))
        print("Guessed letters:", guessed_letters)
        print("Wrong guesses left:", max_wrong_guesses - wrong_guesses)

        guess = get_guess(guessed_letters)
        guessed_letters.append(guess)

        if guess not in secret_word:
            wrong_guesses += 1
            print("That letter is not in the word.")
        else:
            print("Good guess!")

        if is_word_guessed(secret_word, guessed_letters):
            print()
            print("Word:", display_word(secret_word, guessed_letters))
            print("You win!")
            return

    print()
    print("You lose!")
    print("The word was:", secret_word)

play_game()
```

Play a full game.

Checkpoint questions

1. Which function runs the whole game?

Answer: ____________________________________________

2. Which function gets input from the player?

Answer: ____________________________________________

3. Which function checks if the word is complete?

Answer: ____________________________________________

4. Which function chooses the word?

Answer: ____________________________________________

Mini challenge

Change one small part of the game:
- the welcome message
- the number of wrong guesses allowed
- the word list

What did you change?

____________________________________________________

Commit your final version.

```bash
git add .
git commit -m "Finish working command line Hangman game"
```

Git practice summary

Run these commands.

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

Optional extension: Show a simple hangman stage

You can also add a text drawing that changes as the player makes wrong guesses.

```python
def show_hangman(wrong_guesses):
    stages = [
        """
  +---+
  |   |
      |
      |
      |
      |
=========
""",
        """
  +---+
  |   |
  O   |
      |
      |
      |
=========
""",
        """
  +---+
  |   |
  O   |
  |   |
      |
      |
=========
""",
        """
  +---+
  |   |
  O   |
 /|   |
      |
      |
=========
""",
        """
  +---+
  |   |
  O   |
 /|\\  |
      |
      |
=========
""",
        """
  +---+
  |   |
  O   |
 /|\\  |
 /    |
      |
=========
""",
        """
  +---+
  |   |
  O   |
 /|\\  |
 / \\  |
      |
=========
"""
    ]

    print(stages[wrong_guesses])
```

Try calling it inside your game loop.

Write where you added it:

____________________________________________________

Final reflection

1. What part of the game was easiest for you?

____________________________________________________

2. What part was hardest?

____________________________________________________

3. What did you learn about strings?

____________________________________________________

4. What did you learn about lists?

____________________________________________________

5. What did you learn about loops?

____________________________________________________

6. What did you learn about functions?

____________________________________________________

7. What did you learn about Git?

____________________________________________________

8. Why is committing often a good habit?

____________________________________________________

9. If you kept working on this project, what would you add next?

____________________________________________________

Challenge ideas for later

- Add score tracking
- Add difficulty levels with easy and hard word lists
- Load words from a file
- Draw the full hangman figure as the player makes mistakes
- Let the player quit with `q`
- Show correctly guessed letters in alphabetical order

