apc-seminar
===========

Here you can find our seminar lecture and the program that solves our problem set (skyline).

Problem:
A skyline is the outline formed by a group of buildings against the sky. A certain city has a beautiful
skyline that's visible to everybody as they approach it by car. You have bought the rights to place an
advertisement over it, and you would like to do so while preserving the shape of the city. The skyline is
formed by n buildings, all with a width of 1 and each with a different height. You will place your ad on
a rectangle of maximum area that is fully contained within the interior of the skyline.
To keep the input small, it will be codified in the following way. You will be given a int[] h. Use the
following pseudo-code on h to generate an array R. The x-th building has height R[x], which means its
lower left corner is at (x, 0) and its upper right corner is at (x+1, R[x]). The total width of the skyline
is n. All array indices are 0-based:

//input array : h
//output array : R (of size n)
j := 0
m := size of h
for i := 0 to n -1
    R[i] := h[j]
    s := (j+1) % m
    h[j] := ( ( h[j] ^ h[s] ) + 13 ) % 835454957
    j := s

This code, along with the constraints, ensures that the height of each building is between 0 and 835454956,
inclusive. In the above code, % is the modulo operator and ^ is the bitwise XOR binary operator. Return
the area of the rectangle on which you will place your ad.
