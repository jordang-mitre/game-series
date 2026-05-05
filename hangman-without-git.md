Python Hangman Workshop Student Worksheet No-Git Section

Name: ______________________

Date: ______________________

Goal

In this workshop, you will:

build a working Hangman game in Python
practice variables, strings, lists, functions, loops, conditionals, and user input
learn where programmers would normally save progress with Git
not run Git in this class section because it is banned here and may freeze your computer
What you need

Python
A code editor
A terminal
Files for this project

hangman.py
README.md
Important note for this class section

Git is not allowed in this section. Do not try Git commands here.

Instead:

save your files normally in your code editor
keep your project folder organized
when you reach a save point, read the Git note so you understand what you would do in a normal development environment
Part 1: Project setup

Step 1

Create your project folder and move into it.
mkdir hangman-python
cd hangman-python

Step 2

Create your files.
touch hangman.py README.md

If touch does not work on your computer, create the files in your editor.

Step 3

Add this to README.md.
This is my beginner Python Hangman project.

Step 4

Add this to hangman.py.
print("Welcome to Hangman!")

Step 5

Run your program.
python hangman.py

If needed, use python3 instead.

Checkpoint questions

What file will hold your Python code?
Answer: ____________________________________________

What file will describe your project?
Answer: ____________________________________________

What does python hangman.py do?
Answer: ____________________________________________

Mini challenge

Change the welcome message so it includes your name.

Write your new line here:

Run the program again.

Save point

This is where you should save your work normally in your editor.

If Git were allowed, this is where you would usually create your first project snapshot.

Do not run these commands in this class section.
git init
git add .
git commit -m "Initial project setup"

What those commands would do if Git were allowed:

git init would turn the folder into a Git repository
git add . would prepare all current files to be saved in Git
git commit -m "Initial project setup" would save a snapshot with a message
Part 2: Create the secret word and hidden display

Add this to hangman.py.
secret_word = "python"

print("Welcome to Hangman!")
print("The secret word is:")
print(secret_word)

Run it.

What do you see?

Now replace it with this version that hides the word.
secret_word = "python"

print("Welcome to Hangman!")
print("The word has", len(secret_word), "letters.")
print("_ " * len(secret_word))

Run it again.

Checkpoint questions

What kind of value is "python"?
Answer: ____________________________________________

What does len(secret_word) return?
Answer: ____________________________________________

If the word is "cat", what will "_ " * len(secret_word) print?
Answer: ____________________________________________

Mini challenge

Change the secret word to "coding".

What output do you get now?

Save point

Save your files normally.

If Git were allowed, this is where you would save another snapshot.

Do not run this in this class section.
git add .
git commit -m "Add starter Hangman word and hidden display"

What it would do:

git add . would collect changed files
git commit -m "Add starter Hangman word and hidden display" would save a new version of the project with a clear message
Part 3: Track guessed letters

Replace your code with this.
secret_word = "python"
guessed_letters = ["p", "o"]

print("Welcome to Hangman!")
print("Secret word:", secret_word)
print("Guessed letters:", guessed_letters)

Run it.

What is stored in guessed_letters?

Now replace your code with this function version.
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

Run it.

What did the display look like?

Checkpoint questions

What is a list?
Answer: ____________________________________________

What does for letter in secret_word do?
Answer: ____________________________________________

What does if letter in guessed_letters mean?
Answer: ____________________________________________

What does return do?
Answer: ____________________________________________

Mini challenge

Change guessed_letters to:
["p", "y", "t"]

Before running it, predict the output.

Prediction: _________________________________________

Actual output: ______________________________________

Save point

Save your files normally.

If Git were allowed, this is where you would record your progress.

Do not run this in this class section.
git add .
git commit -m "Add guessed letters list and display function"

What it would do:

save the new version of your program
let you look back later and see when you added the display function
Part 4: Let the player guess one letter

Replace your code with this.
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

Run it and enter a letter.

What happened after you guessed?

Checkpoint questions

What does input() return?
Answer: ____________________________________________

What does .append() do?
Answer: ____________________________________________

What happens if the guessed letter is in the word?
Answer: ____________________________________________

What happens if the guessed letter is not in the word?
Answer: ____________________________________________

Mini challenge

Guess a letter that is not in the word.

What does the display look like?

Why?

Save point

Save your files normally.

If Git were allowed, this is where you would save a milestone.

Do not run this in this class section.
git add .
git commit -m "Accept one guessed letter from the user"

What it would do:

create a checkpoint after adding player input
give you a version you could return to later if needed
Part 5: Validate the guess

Replace your code with this.
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

Test these inputs:

ab
5
!
one valid letter
a repeated letter
What happened in each case?

ab: _______________________________________________

5: ________________________________________________

!: ________________________________________________

valid letter: ________________________________________

repeated letter: ____________________________________

Checkpoint questions

What does while True do?
Answer: ____________________________________________

Why do we use .lower()?
Answer: ____________________________________________

Why do we check len(guess) != 1?
Answer: ____________________________________________

Why do we check guess in guessed_letters?
Answer: ____________________________________________

Mini challenge

Remove .lower() and test uppercase input.

What changes?

Put .lower() back after testing.

Save point

Save your files normally.

If Git were allowed, this is where you would save the version with input validation.

Do not run this in this class section.
git add .
git commit -m "Add guess validation"

What it would do:

save the moment when your program became safer and more user-friendly
make it easy to compare this version to the earlier one
Part 6: Save-progress review

In a normal class section, this is where you would review your saved project history with Git.

Do not run this command in this class section.
git log --oneline

What it would do:

show a short list of saved snapshots
each line would represent one commit
you could read the messages to see the story of your project
Checkpoint questions

Why is it helpful to save your work often?
Answer: ____________________________________________

If Git were allowed, what would git log --oneline show you?
Answer: ____________________________________________

Why are clear save messages useful?
Answer: ____________________________________________

Mini challenge

Explain in your own words what a project snapshot is.

Answer: ____________________________________________

Part 7: Repeat guessing in a loop

Replace your code with this.
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

Run it.

What changes each time through the loop?

Now replace your code with this version that tracks wrong guesses.
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

Checkpoint questions

What is the difference between the for loop and the while loop here?
Answer: ____________________________________________

What does if guess not in secret_word mean?
Answer: ____________________________________________

When does wrong_guesses increase?
Answer: ____________________________________________

Why do we need both wrong_guesses and max_wrong_guesses?
Answer: ____________________________________________

Mini challenge

Change max_wrong_guesses from 6 to 8.

What changed when you ran the game?

Save point

Save your files normally.

If Git were allowed, this is where you would save the version with the game loop.

Do not run this in this class section.
git add .
git commit -m "Add game loop and wrong guess counter"

What it would do:

save a version where the game now repeats guesses
help you go back to this milestone if later changes caused problems
Part 8: Detect a win or loss

Add this function.
def is_word_guessed(secret_word, guessed_letters):
    for letter in secret_word:
        if letter not in guessed_letters:
            return False
    return True

Test it with this code.
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

What did is_word_guessed() return?

Now replace your code with this full version.
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

Checkpoint questions

What does is_word_guessed() check?
Answer: ____________________________________________

Why do we check for a win after a guess?
Answer: ____________________________________________

What happens if the player runs out of guesses?
Answer: ____________________________________________

Why do we show the secret word when the player loses?
Answer: ____________________________________________

Mini challenge

Change the secret word to "git" and win the game.

What happened?

Save point

Save your files normally.

If Git were allowed, this is where you would save the version with win and loss conditions.

Do not run this in this class section.
git add .
git commit -m "Add win and lose conditions"

What it would do:

save the version where the game can now end correctly
give you a clear milestone in the project timeline
Part 9: Choose a random word from a list

Replace your code with this.
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

Run the game a few times.

Checkpoint questions

What is words?
Answer: ____________________________________________

What does random.choice(words) do?
Answer: ____________________________________________

Why is a list useful here?
Answer: ____________________________________________

What happens if you add more words?
Answer: ____________________________________________

Mini challenge

Add 3 new words to the list.

Write them here:

Did one of your new words appear when you played?

Save point

Save your files normally.

If Git were allowed, this is where you would save the version with random word selection.

Do not run this in this class section.
git add .
git commit -m "Choose a random word from a list"

What it would do:

save the point where the game became different each time you play
help document how the game improved
Part 10: Final working game

Replace your file with this full version.
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

Play a full game.

Checkpoint questions

Which function runs the whole game?
Answer: ____________________________________________

Which function gets input from the player?
Answer: ____________________________________________

Which function checks if the word is complete?
Answer: ____________________________________________

Which function chooses the word?
Answer: ____________________________________________

Mini challenge

Change one small part of the game:

the welcome message
the number of wrong guesses allowed
the word list
What did you change?

Final save point

Save your files normally.

If Git were allowed, this is where you would save your finished project.

Do not run this in this class section.
git add .
git commit -m "Finish working command line Hangman game"

What it would do:

save the completed working version of your project
give you a final snapshot to return to later
If Git were allowed: useful commands to know

You are not allowed to run these here, but these are the commands programmers often use.

Check what changed:
git status

What it would do:

show which files changed
show which files are ready to be committed
show which files are not being tracked yet
Save changed files for the next snapshot:
git add .

What it would do:

prepare all changed files to be included in the next commit
Create a snapshot with a message:
git commit -m "Your message here"

What it would do:

save a named checkpoint of your project
View past snapshots:
git log --oneline

What it would do:

show a short history of earlier commits
See exact changes before saving:
git diff

What it would do:

show the lines that changed since the last saved version
Checkpoint questions

If Git were allowed, what command would show the current state of your files?
Answer: ____________________________________________

If Git were allowed, what command would create a snapshot?
Answer: ____________________________________________

If Git were allowed, what command would show your history?
Answer: ____________________________________________

Why do programmers save work in small steps?
Answer: ____________________________________________

Optional extension: Play again

If you have time, add this feature.
def play_again():
    answer = input("Play again? (y/n): ").lower()
    return answer == "y"

while True:
    play_game()
    if not play_again():
        print("Thanks for playing!")
        break

Optional extension: Show a simple hangman stage

You can also add a text drawing that changes as the player makes wrong guesses.
def show_hangman(wrong_guesses):
    stages = [
        """
```  +---+
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
 /|\\ |
      |
      |
=========
""",
        """
  +---+
  |   |
  O   |
 /|\\ |
 /    |
      |
=========
""",
        """
  +---+
  |   |
  O   |
 /|\\ |
 / \\ |
      |
=========
"""
    ]
```
    print(stages[wrong_guesses])

Try calling it inside your game loop.

Write where you added it:

Final reflection

What part of the game was easiest for you?
What part was hardest?
What did you learn about strings?
What did you learn about lists?
What did you learn about loops?
What did you learn about functions?
Even though you could not use Git here, what did you learn about how it would help save progress?
Why is saving often a good habit, even without Git?
If you kept working on this project, what would you add next?
Challenge ideas for later

Add score tracking
Add difficulty levels with easy and hard word lists
Load words from a file
Draw the full hangman figure as the player makes mistakes
Let the player quit with q
Show correctly guessed letters in alphabetical order