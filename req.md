## Requirement

- The game board has a size of n x n, where n is a positive integer.
- The number of players in the game is n-1, so if the board size is 3x3, there will be 2 players.
- Players can choose their own symbols (e.g., X, O).
- There can be a bot (computer-controlled player) in the game, but only one bot per game.
- The order of players' turns is randomized at the start of the game.
- The winner is determined when one player's symbols form a complete row, column, or diagonal on the board.
- If all cells on the board are filled, and no player has a winning row, column, or diagonal, the game ends in a draw.
- The game should have a replay feature that allows players to undo their moves using a stack data structure.

## Class Diagram

```java

class Game {
    private Board gameBoard;
    private List<Player> players;
    private int currentPlayerIndex;
    private boolean hasWinner;
    private GameState gameState;

 
}

class Move {
    private Cell cell;
    private Player player;

}

enum GameState {
    IN_PROGRESS,
    ENDED,
    DRAW
}

class Board {
    private int size;
    private List<List<Cell>> cells;
    private int numPlayers;
    private boolean hasBot;

}

class Cell {
    private int row;
    private int col;
    private Player player;
    private CellState state;

}

enum CellState {
    EMPTY,
    FILLED,
    BLOCKED
}

class Player {
    private int id;
    private Symbol symbol;
    private boolean isWinner;
    private PlayerType type;

}

enum PlayerType {
    HUMAN,
    BOT
}

class Symbol {
    private char sym;

}

class Bot extends Player {
    private Difficulty level;

}

enum Difficulty {
    EASY,
    MEDIUM,
    HARD,
    EXTREME
}
