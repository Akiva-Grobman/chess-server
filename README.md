# Rust Server

## Web API

- GET /
Return a UUID that represents the player+game identifier

- GET /board/`UUID`
Return a representation (scheme TBD) of the board state.
The client will send a request to see if the other player has made their move

- POST /move/`UUID`
Make a move.
Body:
```json
{
    "source": [x_pos, y_pos],
    "destination": [x_pos, y_pos]
}
```


- GET /piece-moves/`UUID`/?x_pos=`x`&y_pos`y`
Return a list of the positions the piece in position (`x`,`y`) can legally move to