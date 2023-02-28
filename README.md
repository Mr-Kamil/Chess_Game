![Zrzut ekranu_20230228_212157](https://user-images.githubusercontent.com/116226497/221972131-69fa768b-7090-446f-a583-f319c6eecc5e.png)

This project is a simple chess game player vs computer with a graphic interface. I created all the rules and engine myself; there are no imported versions.
It includes almost all the chess rules, except the threefold repetition rule. 

The AI engine uses the negamax algorythm with alpha-beta pruning for finding best moves. It explores all possible moves, then explores their
possible moves and so on. Currently the depth of searching is set on 3. The best move is decided by evaluating the score of the board (pieces points, 
positions points)  The graphical representation of the board is rendered  with a log panel, which displays chess notations of all made moves. 

The program only allows you to make valid moves according to the rules of chess, and also includes the special moves: castling, en_passant and pawn promotion.
There is still a lot to do, especially to improve and optimize the AI engine.

It`s my first project in Python. I used a lot of knowledge from youtube tutorials and stock overflow during writing this game.

USAGE: 

'''
git copy https://github.com/Kamil-Kam/Chess_Game
cd python-chess
pip install pygame
'''

The game was created and tested on Python 3.9.13 with Pygame 2.1.3 on Windows 11.

Player (white) vs Computer (black)
Use mouse to move your pieces.
r - reset
Backspace - undo move
p - pause
c - continue


DONE:
- Move ordering. Some moves are likely to be better than others. Currently, the code considers move in the order: from the most promising.
As a result the search algorithm can potentially find the best move faster.

- Game responsiveness. The responsiveness is provided by using two processes during the game. One of them runs the main game functions, 
the other is responsible for the AI engine.

- Chess rules. All essential chess rules, and special moves are implemented.

- Log panel with chess notation.

- Pause and endgame statements.

- AI calculations multiprocessing. AI engine calculations were run by 2 or 4 processes, but it didn`t make calculations much faster, 
in same cases even slower so it isn`t finally added to code and is waiting for further development.


TODO:
- improve get_valid_moves function to check only these moves which are possible invalid, now it`s iterating through all the moves

- use transposition tables: When the same position is encountered multiple times during the search, the program
can store the best move and score found so far in a hash table. This can speed up the search significantly, especially for deeper searches.

- implement chess openings book: the AI engine during the first few rounds can make moves due to an algorythm with most common chess openings.
It can make the AI faster, the AI engine may choose moves without time-consuming calculating

- implement iterative deepening: Instead of searching to a fixed depth, the program can perform multiple searches
 with increasing depths.

 - improve the evaluation function: The score_material() function only considers the material balance on the board.
 A better evaluation function would consider other factors such as piece mobility, king safety, pawn structure, and
 control of key squares.

- use multiprocessing in the AI engine to make the calculations faster: The search algorithm can be parallelized by searching 
different branches of the game tree concurrently.

- add main menu

- enable to choose by user, in which figure a pawn is promoted. Now it`s always the queen.

- add the threefold repetition rule