# Autonomous_vehicle_AlphaZero

You should understand the basis of reinforcement learning before dive into this project. After that, a quick view about AlphaZero (what is the input, output and how can it learn from its own experience...)

In chess, the input of AlphaZero is a 'stack of planes' that each plane has a size of 8x8 which represent for the chessboard. Each plane consists information of each type of pieces (pawns, knights, bishops, rooks, queen and king). However, to help the agent understand more about the game state, GoogleDeepmind (author of AlphaZero) proposed to use T time-step right before the current state. So that the stack of planes is 'thicker' T times. Moreover, to track informations such as castling, piece color, repetition,... they add L more planes to the input and each of these L planes consists constant value (all 1 or all 0). 

The output of the neural network is a policy $\pi(s|a)$ has the size of 8x8x73. They assumed that every pieces can move like a queen and knight and also promote like a pawn. Let's make a quick calculation: 8 direction of queen multiply with 7 possible range (8 except the current position) and also 8 square of a 'knight move'. That is 8x7+8=64. What are the other 9 moves? Those are 9 underpromotion for pawns (left, right, straight) for 3 kind of piece except the queen.

So in the autonomous driving task, how can we modeling the state?
