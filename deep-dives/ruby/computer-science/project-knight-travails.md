---
description: >-
  Learn how to build a method called "knight_moves" that shows the simplest
  possible way to get from one square to another by outputting all squares the
  knight will stop on along the way.
---

# Project: Knight Travails

## Introduction

Now you're a pro with DFS and BFS. Let's try using our search algorithms on a real problem.

For this project, you'll need to use a data structure that's similar \(but not identical\) to a binary tree. For a summary of a few different examples, reference [this article](https://www.khanacademy.org/computing/computer-science/algorithms/graph-representation/a/describing-graphs).

A knight in chess can move to any square on the standard 8x8 chess board from any other square on the board, given enough turns \(don't believe it? See [this animation](https://upload.wikimedia.org/wikipedia/commons/thumb/d/da/Knight%27s_tour_anim_2.gif/250px-Knight%27s_tour_anim_2.gif)\). Its basic move is two steps forward and one step to the side. It can face any direction.

All the possible places you can end up after one move look like this:

![](https://i.imgur.com/mHQqH08.gif)

## Assignment

Your task is to build a function `knight_moves` that shows the simplest possible way to get from one square to another by outputting all squares the knight will stop on along the way.

You can think of the board as having 2-dimensional coordinates. Your function would therefore look like:

* `knight_moves([0,0],[1,2]) == [[0,0],[1,2]]`
* `knight_moves([0,0],[3,3]) == [[0,0],[1,2],[3,3]]`
* `knight_moves([3,3],[0,0]) == [[3,3],[1,2],[0,0]]`

1. Put together a script that creates a game board and a knight.
2. Treat all possible moves the knight could make as children in a tree.  Don't allow any moves to go off the board.
3. Decide which search algorithm is best to use for this case.  Hint: one of them could be a potentially infinite series.
4. Use the chosen search algorithm to find the shortest path between the starting square \(or node\) and the ending square.  Output what that full path looks like, e.g.:

```bash
  > knight_moves([3,3],[4,3])
  => You made it in 3 moves!  Here's your path:
    [3,3]
    [4,5]
    [2,4]
    [4,3]
```

