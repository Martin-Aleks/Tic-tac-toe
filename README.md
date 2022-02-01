# Tic-tac-toe
Self-learning tic-tac-toe game

Progress note: 
This note will summerise the progress made on this project. The task was to create a tic-tac-toe game that can play against itself and thus learn what moves are more or less favourable. The ultimate criteria for success is a game that can play against a real opponent and win or draw consistently.
The game code has been adapted from an open source Notebook which used a Neural Network model that updates its weights after each game. After each game, a score of +1 is assigned if the program one, a score of 0 is assigned if the result is a draw and a score of -1 is assigned if the program lost. It is expected that after a large number of itterations, the program will make more favourable moves based on these scores. A Stochastic Gradient Descent (SGD) was used as an optimiser. The SGD learning rate and momentum parameters were adapted from the open source Notebook, although they could be further optimised. 
The following 3 Figures show the count of wins, losses and draws for 100000, 60000 and 40000 games respectively. 
These were the first runs of the training loop to total 200000 iterations of training with both "Easy" and "Hard" mode being randomly chosen 
with a 50/50 chance. To elaborate, "Easy" mode makes the coded opponent choose a random available position on the board and "Hard" mode attempts to block the program from winning and to build rows, collumns or diagonals with 2 and 3 marks (thus winning the game).

![](Images/Figure%201.png)

![](Images/Figure%202.png)

![](Images/Figure%203.png)
As seen by the images, the program over many iterations became better at losing less, which is the ultimate goal of the task. 

The program was tested agains a real opponent approximately 15-20 times to observe the performance and consistency of the 
program. The game could draw agains a real opponent, but winning was not a common occurrence. It is likely the program has 
not played enough "Hard" mode games to adjust the model weights appropriately. After all, approximately 50% of the games played 
were "Easy" mode which might become irrelevant after a large number of itterations. Perhaps, letting the game train 30% on "Easy" mode
and 70% on "Hard" mode will give a better performance against a real opponent after hindrets of thousands of iterations. 

The game mode ("Easy" or "Hard") and the SGD learning rate and momentum parameters are an optimisation problem which is not explicitly stated as a priority of this task. It is no question that we would like to have an optimised training for the program. However, it is difficult to determine the current performance due to the hardware the code is being run on (a 2015 laptop) and the slow training process (with 100000 games taking approximately 20 hours). With this limitation, it is difficult to compare changes to the game modes or parameters without investing sufficient time, which might not be available when working on a deadline. If optimisation is not considered, the current game modes and SGD parameters used should continue to improve the model with a larger number of training iterations as Figures 1, 2 and 3 suggest. For this reason, the game code contains the 200000 training iterations used to make the same number of games as the figures shown and contains separate code with 2000000 (10 times more) iterations. It is expected that after two million iterations, the program should perform better than after two hundred thousand iterations. Due to technological limitations in speed, two million iterations could not be tested and it is not known if this number of iterations is enough to train the model to consistently win or draw against a real opponent. This is only an assumption based on the data from the figures shown.

A question that remains to be addressed is that of the coded opponent. The use of a coded opponent is relevant in the context of avoiding the program and the opponent program from falling in synch and playing the game the same way over and over as noted by the author of the open source Notebook. One potential problem could then be how advanced the coded opponent should be. The opponent used in the training code tries to block the program from winning, tries to make 2 marks in a row/column/diagonal and tries to win by having 3 marks in a row/column/diagonal. However, human strategy can go beyond that train of thought when playing tic-tac-toe. It is not uncommon for real opponents to try to set up a situation on the board where they have 2 opportunities to win at the same time, at which point the game is decided despite the efforts of the losing side. This is how real opponents are expected to play if they put in effort into the game and it is likely the coded opponent does not go to this advanced level of action. Therefore, it can be expected that the program is potentially weak against such strategies, as the number of times it has encountered those "board states" is likely low.

One experiment was to train the model for 200000 iterations and then only train it on "Hard" mode for approximately 200000 iterations. However, the number of games lost appeared to increase. The resulting plots are unavailable due to a computer restart that occured before saving the figures. Ultimately, neither the plots nor the games played against a real opponent showed an improvement. It is possible switching the game mode to only "Hard" had a negative effect and it might be possible that only using "Hard" mode from the start could have been the appropriate action. Other optimisers such as Adam were explored in theory only, due to the limited time. However, it is possible for other optimisers to be a better fit with this project. I decided not to try them due to limited understanding, since further literature exploration would be required.

In conclusion, the presented game code successfully implements a Neural Network model with a Stochastic Gradient Descent optimiser to train a program to play tic-tac-toe. The program was tested against a real opponent after 200000 training iterations with mixed results, likely due to the low number of games played or due to not sufficiently optimised game modes and SGD parameters. If presented with time or an improved technical setup, I would let the training process run for a longer time, for example two million iterations, and test the program against a real opponent again. A reasonable prediction based on current knowledge would be that the program should play without losing to a real opponent after 2-10 million training iterations with 50/50 "Easy" and "Hard" modes using the current SGD parameters.










