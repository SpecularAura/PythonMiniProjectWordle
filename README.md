# Wordle
## Explanation of Game
- The game of wordle is a popular word guessing game. 
- The game starts with guessing a 5 letter word.
- After each guess the game indicates whether the each letter is in the word, in the correct position or incorrect position.
- This gives hints towards the correct answer.
- The player is given 6 attempts to guess the correct word.

## Implementation Details
### Game Logic
- Terminology:
	- The correct answer of the game is called 'secret word'
	- A list of characters of the secret word is called 'secret word list'
	- The guess by the player is called 'guessed word'
	- A list of characters of the guessed word is called 'guessed word list'
	- A list containing the state of each letter 'state list'
- The secret word will be random chosen word from a list of all English words
- The guessed word will be received from the interface of the game
- If a letter from the guessed word:
	- is in the secret word and in the correct position, Then that position in the state list will receive a state of 2 (letter will be highlighted as green)
	- is in the word but in the incorrect position then that position in the state list will receive a state of 1 (letter will be indicated as yellow)
	- is not in the word , then that position in the state list will receive a state of 0 (letter will be indicated as grey)      

#### Game
- The secret word is chosen
- A list of the characters of the secret word is created
- We receive the guessed word from the interface and create its guessed word list
- We do a first pass through the guess list (guessed word list): 
	- Identify the letters in the correct position
	- Update the state list for the letters in the correct position
- We do a second pass 
### Interface
The interface will


## Implementation Details
-   Instead of resolving all the letter results in one-pass, we now first initialize it as an array and default all guess letters to grey (not in the word).
-   We create an list, which is a copy of the secret. Each element corresponds to the letter in the string. For example `["A", "P", "P", "L", "E"]`.
-   We then do a first pass through the guess, and identify any letters in the correct position. If we find one, then that letter becomes 'green', and the secret list is updated to void out that letter so it can't be used in a subsequent comparison. So if we guess "HELLO", the remaining secret becomes something like this: `["A", "P", "P", "*", "E"]`.
-   We then do another loop this time identify the guessed letters which are in the word (by using a nested loop), but not in position.