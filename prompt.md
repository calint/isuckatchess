## greeting
Let's build a super simple one page web app.

Make the code as simple as possible and keep the design simple yet polished.

## data source
Retreive the games from https://api.chess.com/pub/player/calint/games/archives
then select year and month to get the games from
https://api.chess.com/pub/player/calint/games/2026/03

## intention
To find blind spots in user evaluation of chess positions.

## method
Evaluate each move in selected game and if the user (input box to specify) misses
a move that results an evaluation difference higher than a specified margin
(input box to specify) then make a chess problem that is saved in local
javascript storage.

To further improve the user chess vision also find the position which give the 
opponent an opportunity to change the evaluation by the specified threshold
whether it was made or not. Call that "blunder"

The problem should be presented with a chess board showing that position. As an 
hint the app should tell user something similar to: "find white/black move to
gain 3.2" then display the board.

A button or link named "solution" with the moves that gets that evaluation
should be displayed when clicked.

## pitch
```
improving chess for non expert players is mainly
  improving tactical vision
         by
  solving chess puzzles
         and
       playing ... slow games
          thus
    free chess trainer helps you
      spot missed tactical opportunity
          in your own games

       get better
  in an easy entertaining way

    apply in your regular chess games
         upgrade your rating
```