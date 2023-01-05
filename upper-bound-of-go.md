# The upper bound of go

The problem of "Go" (the board game) can be reduced:

1. One can note that you can reduce the problem set into quadrants, where you solve each quadrant "optimally", because the Go board is "symmetrical" across four quadrants.
2. Thus, you can recursively reduce the search space to a quarter of the board size.
3. Recursively applying this rule, you can reduce the size from 19x19, to 9x9, to 5x5, to 3x3.
4. You then have to "merge" the smaller board quadrants (3x3) back into a bigger board (5x5, 9x9 and 19x19). 
5. When you "merge" you have to ensure the optimal solution for the reduced search space (3x3) is still optimal when applied to the "bigger" board -- this means you have to ensure the edges of the 3x3 search space are "connectable" to other 3x3 quadrants, such that it still remains optimal in the bigger board (5x5).

Thus, the calculation is:

3^(number of grids) + edges of quadrant that connects to other quadrants (i.e. 1/2 the perimeter, or the two connecting edges of the quadrant).

e.g.

smallest quadrant: 3^(3x3) * (3 + 3) = 118098

next biggest quadrant: 3^(5x5) * (5 + 5) = 8472886094430

our final quadrants: 3^(9x9) * (9 + 9) = 7981676788374679859068493351144698070454 = 7.9817×10³⁹

The sum of these numbers is the number of upper bound of Go positions required to be calculated, such that an "optimal God algorithm" can exist.

The approach given here is the same as "merge sort" (in computer science), or Fast Fourier Transform, or any other "divide and conquer" algorithm where you need to "recursively divide, calculate, and then merge back". This is often typically O(nlog(n)).

In our case, the big-Oh notation for the upper bound is: O(7.9817×10³⁹) or O(2^132) or 132 bits.

This upper bound is significantly smaller than the simpler calculation of the upper bound: 3^(19x19) = 1.7409×10¹⁷², by a factor of 10^133.

So, it's not as big as the number of atoms in the universe, but it's bigger than 128-bit encryption.

I would have published this as a "white paper" back in 2009, but the idea of "divide and conquer" (aka merge sort), and its application on what is "obviously" a symmetric board, is so trivial, I felt too ashamed. In fact, I still don't want to be associated with discovering a new upper bound for a God's algorithm on Go.

But given Alpha Go made its debut in 2015, I guess I can publish this now and have the last laugh. However, it shouldn't distract from the fact that they did achieve the feat of beating a human player with AI, but it isn't as hard as it appears to be.

- David Shoon
