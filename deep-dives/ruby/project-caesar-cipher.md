---
description: >-
  Learn how to build a simple command-line application that takes in a string
  and the shift factor and then outputs an "encrypted" string.
---

# Project: Caesar cipher

## Assignment

From Wikipedia:

> In cryptography, a Caesar cipher, also known as Caesar's cipher, the shift cipher, Caesar's code or Caesar shift, is one of the simplest and most widely known encryption techniques. It is a type of substitution cipher in which each letter in the plaintext is replaced by a letter some fixed number of positions down the alphabet. For example, with a left shift of 3, D would be replaced by A, E would become B, and so on. The method is named after Julius Caesar, who used it in his private correspondence.

There's a video about it [from Harvard's CS50 class](https://www.youtube.com/watch?v=36xNpbosfTY).

Implement a caesar cipher that takes in a string and the shift factor and then outputs the modified string:

```ruby
  > caesar_cipher("What a string!", 5)
  => "Bmfy f xywnsl!"
```

### **Quick tips**

* You will need to remember how to convert a string into a number.
* Don't forget to wrap from `z` to `a`.
* Don't forget to keep the same case.

