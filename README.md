# Tic-tac-toe
Self-learning tic-tac-toe game

Progress note: 
This note will summerise the progress made on this project. The game code has been adapted from an open source Notebook.
The SGD learning rate and momentum parameters were not changed, although they could be further optimised.
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
and 70% on "Hard" mode will give a better performance against a real opponent after hindrets of thousands of iterations.

The machine used to train the program was a 2015 laptop, which likely results in a slow training process (100000 games took approximately 20 hours).
With this, it was difficult to experiment and optimise the learning rate and momentum parameters, as well as experimenting with training the game 
only on "Hard" mode.










