---
description: >-
  Big O a kind of asymptotic notation that describes how an algorithm grows in
  time or space in relation to the size of it's input.
---

# Big O

## Introduction

In our last lesson, we looked at the problems of sorting and searching an array, and briefly discussed some algorithms concerned with tackling these problems, both 'good' and 'bad'. We've even discussed which ones are efficient and which ones are inefficient; but we never really discussed by what metric we define an algorithm as efficient or inefficient. This is where `Big-O` notation, and other notations, come in!

As a disclaimer, do not be disheartened or discouraged if this is a little tricky to grasp on your first try. You will not often be expected to work out precisely how efficient your code is. This lesson will help you to get a general understanding and appreciation for what `Big-O` is.

## Learning outcomes

Look through these now and then use them to test yourself after doing the assignment:

* How do we communicate the expected performance of an algorithm?
* How do we quantify this expectation?
* What do we know if we're told an algorithm is O\(n\)? O\(n^2\)? O\(log\(n\)\)?

## What is Big O?

Big O a kind of `asymptotic notation` that describes how an algorithm grows in `time` or `space` in relation to the `size` of it's `input`. This is call it's `Time` or `Space Complexity` That may sound like a load of waffle, but what it means if _"If I make n so many times larger, how long or big does the algorithm get?"_ On some sites where you train your coding skill against challenges; you may find people commenting on other people's solution and throwing `O(n^2)` or some other `O` terminology about, that's what Big O is. In our previous lesson, if you did a bit of reading on the mentioned algorithms, you'll more than likely find this kind of notation.

## How does it work?

First, lets get into a bit of math \(let `joy` be `unconfined`\). Say you written some function and at worst it takes very specific number of operations to tackle a problem of size n, for example:

operations for input n : 6n^2 + 300n + 7

If we were to make n _**very big**_, our 6n^2 grows _**much**_ larger than our 300n or our 7. So for really big n...

operations for input for very big n ~ 6n^2

This means that our operations is approximately 6n^2. But we're not quite done yet. Say we grow n by 10 times as much; we only grow the number of operations by 100. The 6 in our little equation above is irrelevant. So we also ignore the six, and we're left with what we call our `Big O`, our worst-case growth with input n:

`O(n^2)`

## Is proficiency in math required?

Thankfully, no. There are ways of getting a rough idea of what your algorithm's `Big O` just by looking at the \(pseudo\)code you've written. We shall walk through a few examples of different `Big O` sizes as far as `time` is concerned, how to recognise them, and what they mean:

### **O\(1\)**

The absolute ideal. This means that the algorithm's magnitude does not change, regardless of how big or small your input is. That your performance is `constant`. Let's write a bit of `pseudocode` to demonstrate this:

```text
  define function head(n)
    return n[0]
```

This seems simple enough. You take in an array n, and you return the first element of it. If we take an array of length 3; `all we need to do is return the first` element. If we take an array of length 3,000,000; `all we need to do is return the first element`. Notice how our process of getting the answer has not changed at all? That means the algorithm's size has not changed, making it constant.

We call this `constant time` or `constant space`; depending on which metric you're measuring.

### **O\(n\)**

Another fairly simple concept, this means that our algorithm's magnitude changes similarly to n. So if our input doubles in size, our algorithm is expected to double in `time`. Take this simple example:

```text
  define function find(array, desired)
    for each element in array :
      check if element equals desired. If so, return element
      if not, move onto next element

    if looked through all elements, return false
```

So, we look through each element in our array to see if it matches what we want, if so, we return that element; otherwise we say "false" to say we cannot find the desired value. So if we were to walk through function step by step, we'd do something like this:

`Does this element match?: No` -&gt; `next` -&gt; `Does this element match?: No` -&gt; `next` -&gt; ...

Through all `n` array elements. So what's our `Big O`? We think about the worst case. What is the worst case? Our value is either sitting on the very end of the array or doesn't exist. Here, if we have an array size `n`; the function does `n` checks before it gives us an answer. So our function grows at the same rate that `n` grows, which gives us `O(n)`.

We call this a `linear time`. Algorithm

### **O\(n^2\)**

Although in a lot of algorithmic cases this is considered a good result, in sorting and search cases this is inefficient. This means that should our input grow by 10, for example, our algorithm grows by 100! So if our input _grows by 1,000,000_... yeah. That's big. What could something like this look like in pseudocode?

```text
  define function has_duplicate(array)
    for each element in array :
      for each other_element in array :
        unless other_element and element have the same index
        compare the two elements, return true if they are equal value

    return false if no duplicates found
```

So here, we ignore comparisons of values at the same point in the array; but for each value, we're otherwise looking through the _entire_ array to see if there is a duplicate. For example, if we use the array: _\[ 1,3,4,5,7,8 \]_, we do the following:

_1: 3 -&gt; 4 -&gt; 5 -&gt; 7 -&gt; 8 -&gt; false_

_3: 1 -&gt; 4 -&gt; 5 -&gt; 7 -&gt; 8 -&gt; false_

_4: 1 -&gt; 3 -&gt; 5 -&gt; 7 -&gt; 8 -&gt; false_ ...

With this algorithm, we're going through `n-1` comparisons for each element in our input array. And the array has `n` elements. So we can say:

_number of comparisons = n\_\(n-1\) = n^2 - n\*

With our demonstration in the `So how does it work?` section, we can ignore the `- n`, and we're left with `O(n^2)`.

This is called a `quadratic time` algorithm. It belongs in a larger family of algorithms, `O(n^k)`, which are known as `polynomial time` algorithms.

### **O\(log\(n\)\)**

Spotting these can be a little bit tricky; as their behaviour may not immediately be obvious from code. However, these are more efficient at a larger scale than their `O(n)` and `O(n^2)` counter parts. What `O(log(n))` means is that for the algorithm to grow in `multiples`, the input needs to grow in `powers`. So the input will grow _**much**_ faster. Could we find an example of this? Let's give it a try:

```text
  define function find_in_sorted_array(array, desired)
    let left_index = 0
    let right_index = array.length-1
    let mid_index = (right_index - left_index)/2
    until left_index equals right_index do
      if array[mid_index] equals desired, return desired
      else, if desired < array[mid_index], set right_index = mid_index
      else set left_index = mid_index
      set mid_index = (right_index - left_index)/2

    return false if desired not found
```

This algorithm is a bit more sophisticated, so let's discuss, on a high level, what it's doing. We set a `point` at each end of the array. and one point in the `middle`. If our `middle point` doesn't have the desired value, we check if the `desired value` is `greater than` or `less than` our middle value. Depending on this answer, we `shift` one of our `end points` to our `middle point`, then find a new middle point. Here is an example of our code in action, with the array: _\[ 1,4,7,8,9,14,17,32,69 \]_, and we're searching for 32:

left\_point = 1; right\_point = 69; mid\_point = 9. 9 != 32; 32 &gt; 9; so... left\_point = 9; right\_point = 69; mid\_point = 17. 17 != 32; 32 &gt; 9; so... left\_point = 17; right\_point = 60; mid\_point = 32 32 == 32. We have our winner!

Notice how through each iteration, we essentially `half` our problem space, and only make one comparison in that problem space? This allows us to quickly look through vast quantities of data by `ignoring` comparisons that we _**know**_ will not be successful. With our array above, at worst; we could do 4 searches before we either find or fail. So how would this perform in a space of say... `1,000,000` values?

Well, how many times would you need to half 1,000,000 before you get to 1? _**20**_ times. You could reasonably expect this function to go through _**one million**_ values in about the same time our `Linear time` function would take to go through _**twenty**_

This is the power of a `logarithmic time` or `O(log(n))` function.

## Conclusion and remarks

We have delved somewhat deep into how we can quantify how long an algorithm can take to perform it's task; we have explored the basic mathematical principle of measuring performance of an algorithm, and we have looked at some classic examples to easily identify standard case algorithms of different complexities. We have also gathered a particularly profound appreciation to just how advantageous one algorithm can be over another, given the right circumstances.

However, it should be noted that for _most_ cases, `Big O notation` is an accurate quantifier for performance on a large scale. There exists some cases where although an algorithm _has_ a more efficient `Big O`, in reality that efficiency might only come in for `impossibly big` data sets. So care should still be made to properly research an algorithm if you intend on employing it.

It should also be noted that `Big O` is theoretical. Again, it should mostly hold in the real world; but there are other tricks you will learn throughout your career to further optimise your code if necessary.

## Assignment

1. Have another look at the algorithms mentioned in [our previous lesson](https://www.learnhowtocodebook.com/deep-dives/computer-science/recursion-and-algorithms/more-on-algorithms). What are their Big O notations? What do these notations mean?
2. The above functions aren't the only examples of Big O complexity. Find other examples of complexity; and play around with the numbers. Which are more efficient?
3. What other means of quantifying asymptotic performance are there? [Khan Academy discusses Asymptotic notation is more maths-y detail](https://www.khanacademy.org/computing/computer-science/algorithms/asymptotic-notation/a/asymptotic-notation).

