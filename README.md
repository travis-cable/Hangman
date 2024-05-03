# Hangman
Attempt to train a Reinforcement Learning model to beat the child's game Hangman in 6 attempts or less.

This attempt was a coding interview in which you are given a dictionary of ~250K words (not provided herein for copyright purposes) and asked to train a model which could beat Hangman on a disjoint dictionary. I attempted both both pure statistical and Machine Learning approaches, but wasn't able to get either model to better than 30% success rate.

# Action, State & Reward

action_space ---> Discrete(26) ----> ['a','b',...,'y','z'] = [0,1,...,24,25]

state_space ---> Discrete(31, 27) ---> The example below shows "dad" encoded in this way

                a,  b, c,  d,............, x, y,  z, blank
Blank 1        |0,  0, 0,  1,............, 0, 0,  0, 0 |
Blank 2        |1,  0, 0,  0,............, 0, 0,  0, 0 |
Blank 3        |0,  0, 0,  1,............, 0, 0,  0, 0 |
.......        |0,  0, 0,  0,............, 0, 0,  0, 0 |
Blank 30       |0,  0, 0,  0,............, 0, 0,  0, 0 |
Guessed Letters|-1, 0, 0, -1,............, 0, 0,  0, -1|

Reward:
Step Reward = correct_blanks_guessed_per_guess / word length
Complete Episode Reward = lives_remaining

Anyone that wants to adapt will need a dictionary of words (between 1 and 30 letters) in a text file with each word in a separate line. If anyone does figure out how to properly train the model PLEASE let me know!
