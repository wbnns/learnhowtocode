---
description: >-
  Learning how nodes work by writing them, and building a linked list, will give
  you a solid understanding for learning about a more complex subject in the
  next section, trees.
---

# Project: Linked Lists

## Introduction

In our previous lesson, we looked at `Nodes`, `Linked Lists` and `Trees`; the latter two being core `data structures` to add to your repetoire, and `Nodes` being the foundation those `data structures` are built upon.

As stated previously, if your language of choice is `Ruby` or `JavaScript`, in practice you won't have to concern yourself with implementing `Linked Lists` as `Arrays` are not a fixed sized in these languages. However, learning how `Nodes` work by writing them, and building a `Linked List` with them; will give you a working understanding of how `Linked Lists` work, and give you a solid, founding principle for tackling the bigger task ahead...

`Trees.`

## Structure of a Linked List

A _linked list_ is a linear collection of data elements called nodes that "point" to the next node by means of a pointer.

Each node holds a single element of data and a link or pointer to the next node in the list.

A head node is the first node in the list, a tail node is the last node in the list. Below is a basic representation of a linked list:

`[ NODE(head) ] -> [ NODE ] -> [ NODE(tail) ] -> nil`

For a more thorough explanation, use these resources:

1. [Linked Lists in Plain English](https://www.youtube.com/watch?v=oiW79L8VYXk)
2. [Linked Lists, Ruby's Missing Data Structure](https://www.sitepoint.com/rubys-missing-data-structure/)
3. [A more verbose explanation with plenty of diagrams](http://www.cs.cmu.edu/~adamchik/15-121/lectures/Linked%20Lists/linked%20lists.html)

## Assignment

In your language of choice...

You will need two classes:

1. `LinkedList` class, which will represent the full list.
2. `Node` class, containing a `#value` method and a link to the `#next_node`, set both as `nil` by default.

Build the following methods in your linked list class:

1. `#append(value)` adds a new node containing `value` to the end of the list
2. `#prepend(value)` adds a new node containing `value` to the start of the list
3. `#size` returns the total number of nodes in the list
4. `#head` returns the first node in the list
5. `#tail` returns the last node in the list
6. `#at(index)` returns the node at the given `index`
7. `#pop` removes the last element from the list
8. `#contains?(value)` returns true if the passed in value is in the list and otherwise returns false.
9. `#find(value)` returns the index of the node containing value, or nil if not found.
10. `#to_s` represent your LinkedList objects as strings, so you can print them out and preview them in the console.

    The format should be: `( value ) -> ( value ) -> ( value ) -> nil`

## Extra credit

1. `#insert_at(value, index)` that inserts the node with the provided `value` at the given `index`
2. `#remove_at(index)` that removes the node at the given `index`. \(You will need to update the links of your nodes in the list when you remove a node.\)

