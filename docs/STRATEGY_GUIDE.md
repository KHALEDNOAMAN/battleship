# Battleship - Strategy & Algorithm Guide

## Ship Sizes
| Ship | Size | Count |
|------|------|-------|
| Carrier | 5 | 1 |
| Battleship | 4 | 1 |
| Cruiser | 3 | 1 |
| Submarine | 3 | 1 |
| Destroyer | 2 | 1 |

## AI Strategies

### Hunt Mode (Searching)
- Use checkerboard pattern (hit every other cell)
- Start from center (higher probability)
- Skip cells smaller than smallest remaining ship

### Target Mode (After a Hit)
- Check all 4 adjacent cells
- After 2 hits, follow the line
- Track sunk ships to avoid wasted shots

### Probability Density
```
For each empty cell:
  For each remaining ship:
    Count valid placements passing through cell
  Cell score = sum of all valid placements
Fire at highest-scoring cell
```

## Optimal Play
- Average game: 42 shots to win
- Probability-based AI: ~38 shots
- Perfect play (theoretical): ~35 shots