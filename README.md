# CodeEveryDay

Daily coding practice. Goal is to upload a solution to a coding problem every day in at least two programming languages.

## Quick Start

Substitute i with a number.

For C++:

```console
$ cd taski
/taski$ g++ taski.cpp -o taski && ./taski && rm taski
```

For Python:

```console
$ cd taski
/taski$ python3 taski
```

## Task 1

Given a string, return whether or not it forms a palindrome ignoring case and non-alphabetical characters.

Ex: Given the following strings...

    "level", return true
    "algorithm", return false
    "A man, a plan, a canal: Panama.", return true

## Task 2

Implement a function named generateRange(min, max, step), which takes three arguments and generates a range of integers from min to max, with the step. The first integer is the minimum value, the second is the maximum of the range and the third is the step. (min < max)

    generate_range(2, 10, 2) # should return list of [2,4,6,8,10]
    generate_range(1, 10, 3) # should return list of [1,4,7,10]
    generate_range(2, 10, 2) # should return array of [2, 4, 6, 8, 10]
    generate_range(1, 10, 3) # should return array of [1, 4, 7, 10]

## Task 3

Given a string representing the sequence of moves a robot vacuum makes, return whether or not it will return to its original position. The string will only contain L, R, U, and D characters, representing left, right, up, and down respectively.

Ex: Given the following strings...

    "LR", return true
    "URURD", return false
    "RUULLDRD", return true

## Task 4

Write a program that will calculate the number of trailing zeros in a factorial of a given number.

Examples

    zeros(6) = 1
        6! = 1 * 2 * 3 * 4 * 5 * 6 = 720 --> 1 trailing zero

    zeros(12) = 2
        12! = 479001600 --> 2 trailing zeros

You are not meant to calculate the factorial. The number of trailing zeros in *n!* is the number of factors of 5 in *{1,2,....n}*, which is:

![Alt text](./assets/task4_0.png?raw=true "formula")

As an example here's what it'll look like for 127:

![Alt text](./assets/task4_1.png?raw=true "formula")

## Task 5

Create NxN multiplication table, of size provided in parameter.

For example, when given size is 3:

    1 2 3
    2 4 6
    3 6 9

for given example, the return value should be: [[1,2,3],[2,4,6],[3,6,9]]

## Task 6

You get an array of arrays.
If you sort the arrays by their length, you will see, that their length-values are consecutive.
But one array is missing!

Write a method, that returns the length of the missing array.

Example:

    [[1, 2], [4, 5, 1, 1], [1], [5, 6, 7, 8, 9]] --> 3

If the array of arrays is null/nil or empty or an array in the array is null or empty, the method should return 0. There will always be a missing element and its length will be always between the given arrays.

## Task 7

ROT13 is a simple letter substitution cipher that replaces a letter with the letter 13 letters after it in the alphabet. ROT13 is an example of the Caesar cipher.

Create a function that takes a string and returns the string ciphered with Rot13. If there are numbers or special characters included in the string, they should be returned as they are. Only letters from the latin/english alphabet should be shifted (like in the original Rot13 "implementation").

## Task 8

Once upon a time, on a way through the old wild mountainous west,…

… a man was given directions to go from one point to another. The directions were "NORTH", "SOUTH", "WEST", "EAST". Clearly "NORTH" and "SOUTH" are opposite, "WEST" and "EAST" too.

Going to one direction and coming back the opposite direction right away is a needless effort. Since this is the wild west, with dreadfull weather and not much water, it's important to save yourself some energy, otherwise you might die of thirst!
How I crossed a mountainous desert the smart way.

The directions given to the man are, for example, the following (depending on the language):

    [ "NORTH", "SOUTH", "SOUTH", "EAST", "WEST", "NORTH", "WEST" ]

Going "NORTH" and immediately "SOUTH" is not reasonable, better stay to the same place! So the task is to give to the man a simplified version of the plan. A better plan in this case is simply:

    [ "WEST" ]

Other examples:

    In ["NORTH", "SOUTH", "EAST", "WEST"], the direction "NORTH" + "SOUTH" is going north and coming back right away. The path becomes ["EAST", "WEST"], now "EAST" and "WEST" annihilate each other, therefore, the final result is [].

    In ["NORTH", "EAST", "WEST", "SOUTH", "WEST", "WEST"], "NORTH" and "SOUTH" are not directly opposite but they become directly opposite after the reduction of "EAST" and "WEST" so the whole path is reducible to ["WEST", "WEST"].

Write a function which will take an array of strings and returns an array of strings with the needless directions removed.

Note:

    Not all paths can be made simpler. The path ["NORTH", "WEST", "SOUTH", "EAST"] is not reducible. "NORTH" and "WEST", "WEST" and "SOUTH", "SOUTH" and "EAST" are not directly opposite of each other and can't become such. Hence the result path is itself : ["NORTH", "WEST", "SOUTH", "EAST"].

## Task 9

Inspired from real-world Brainf**k, we want to create an interpreter of that language which will support the following instructions:

    > increment the data pointer (to point to the next cell to the right).
    < decrement the data pointer (to point to the next cell to the left).
    + increment (increase by one, truncate overflow: 255 + 1 = 0) the byte at the data pointer.
    - decrement (decrease by one, treat as unsigned byte: 0 - 1 = 255 ) the byte at the data pointer.
    . output the byte at the data pointer.
    , accept one byte of input, storing its value in the byte at the data pointer.
    [ if the byte at the data pointer is zero, then instead of moving the instruction pointer forward to the next command, jump it forward to the command after the matching ] command.
    ] if the byte at the data pointer is nonzero, then instead of moving the instruction pointer forward to the next command, jump it back to the command after the matching [ command.

The function will take in input...

    the program code, a string with the sequence of machine instructions,
    the program input, a string, eventually empty, that will be interpreted as an array of bytes using each character's ASCII code and will be consumed by the , instruction

... and will return ...

    the output of the interpreted code (always as a string), produced by the . instruction.
