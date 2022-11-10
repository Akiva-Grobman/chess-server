# Rust Server

## Web API

- GET /start_game
Return a the player and  game identifier
Response:
```json
{
    "game_id": "7a236d5f-9c25-4bd9-bacb-8508b47976dd",
    "player_id": "b49f42ab-617b-4681-8c43-3186dc403817"
}
```

- GET /board/?game_id=`game_id`&player_id=`player_id`
Return a representation (scheme TBD) of the board state.


- GET /is_current_player/?game_id=`game_id`&player_id=`player_id`
Return true if it's `player_id`'s turn in the game
```json
{
    "is_current_player": true
}
```


- POST /move/?game_id=`game_id`&player_id=`player_id`
Make a move.
Body:
```json
{
    "source": [x_pos, y_pos],
    "destination": [x_pos, y_pos]
}
```

- GET /piece-moves/?game_id=`game_id`&player_id=`player_id`&x_pos=`x`&y_pos`y`
Return a list of the positions the piece in position (`x`,`y`) can legally move to


Response:
```json
[
    [1, 1],
    [2, 2]
    [3, 3]
]
```