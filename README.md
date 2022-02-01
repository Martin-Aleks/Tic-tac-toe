# Tic-tac-toe
Self-learning tic-tac-toe game

Progress note: 
This note will summerise the progress made on this project. The task was to create a tic-tac-toe game that can play against itself and thus learn what moves are more or less favourable. The ultimate criteria for success is a game that can play against a real opponent and win or draw consistently.
The game code has been adapted from an open source Notebook which used a Neural Network model that updates its weights after each game. After each game, a score of +1 is assigned if the program one, a score of 0 is assigned if the result is a draw and a score of -1 is assigned if the program lost. It is expected that after a large number of itterations, the program will make more favourable moves based on these scores. A Stochastic Gradient Descent (SGD) was used as an optimiser. The SGD learning rate and momentum parameters were adapted from the open source Notebook, although they could be further optimised. 
The following 3 Figures show the count of wins, losses and draws for 100000, 60000 and 40000 games respectively. 
These were the first runs of the training loop to total 200000 iterations of training with both "Easy" and "Hard" mode being randomly chosen 
with a 50/50 chance. 

![](Images/Figure%201.png)

![](Images/Figure%202.png)

![](Images/Figure%203.png)


The program was tested agains a real opponent approximately 15-20 times to observe the performance and consistency of the 
program. The game could draw agains a real opponent, but winning was not a common occurrence. It is likely the program has 
not played enough "Hard" mode games to adjust the model weights appropriately. After all, approximately 50% of the games played 
were "Easy" mode which might become irrelevant after a large number of itterations. Perhaps, letting the game train 30% on "Easy" mode
and 70% on "Hard" mode will give a better performance against a real opponent after hindrets of thousands of iterations. A question that remains to be addressed is that of the coded opponent. The use of a coded opponent is relevant in the context of avoiding the program and the opponent program from falling in synch and play the game the same way over and over as noted by the author of the open source Notebook. One potential problem could then be how advanced the coded opponent should be. The opponent used in the training code tries to block the program from winning, tries to make 2 marks in a row/column/diagonal and tries to win by having 3 marks in a row/column/diagonal. However, human strategy can go beyond that train of thought when playing tic-tac-toe. It is not uncommon for real opponents to try to set up a situation on the board where they have 2 opportunities to win at the same time, at which point the game is decided despite the efforts of the losing side. This is how real opponents are expected to play if they put in effort into the game and it is likely the coded opponent does not go to this advanced level of action. Therefore, it can be expected that the program is potentially weak against such strategies, as the number of times it has encountered those "board states" is likely low.

The machine used to train the program was a 2015 laptop, which likely results in a slow training process (100000 games took approximately 20 hours).
With this, it was difficult to experiment and optimise the learning rate and momentum parameters, as well as experimenting with training the game 
only on "Hard" mode.










