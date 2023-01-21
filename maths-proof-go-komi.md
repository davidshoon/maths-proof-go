# Maths proof: The reason for Komi in Go

by David Shoon 2023-01-21


As you know, the area vs perimeter formula in mathematics is this:

Number of stones per side = S

Area = S^2

Perimeter = 4 * S (square, optimal shape), or 2 * S + 2 * S + S + S for a rectangular area...

i.e. the optimal (minima) area:perimeter ratio is 4:1 (i.e. a square).

You'll see this in a Go game, where if you try to surround one stone, it takes 4 stones.


  O
O x O
  O
  
  
Therefore, it will always be a 1st player win game, because the first player has the advantage of 4 stones to 1. 

Which is why, if the average area being capture is just 1 stone, then the Komi should be 4.5 stones.

However, the average Komi is either: 5.5, 6.5, or 7.5.
 
This means justifying the Komi depends on the average area of stones captured.

## The two eyes.

Given two eyes is the minimal secured area:

O O O O O 
O X O X O   
O O O O O

Therefore, the Komi is 13:2 = 6.5.

i.e. a longer term strategy (i.e. a rectangular area instead of a square) is less optimal than the simplest secured area (i.e. two eyes), so therefore, 6.5 is the optimal Komi.

QED.

