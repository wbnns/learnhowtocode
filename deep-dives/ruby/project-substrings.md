---
description: >-
  Learn how to build a simple command-line application that returns a hash
  listing of substrings.
---

# Project: Substrings

## Assignment

Implement a method `#substrings` that takes a word as the first argument and then an array of valid substrings \(your dictionary\) as the second argument. It should return a hash listing each substring \(case insensitive\) that was found in the original string and how many times it was found.

```ruby
  > dictionary = ["below","down","go","going","horn","how","howdy","it","i","low","own","part","partner","sit"]
  => ["below","down","go","going","horn","how","howdy","it","i","low","own","part","partner","sit"]
  > substrings("below", dictionary)
  => { "below" => 1, "low" => 1 }
```

Next, make sure your method can handle multiple words:

```ruby
  > substrings("Howdy partner, sit down! How's it going?", dictionary)
  => { "down" => 1, "go" => 1, "going" => 1, "how" => 2, "howdy" => 1, "it" => 2, "i" => 3, "own" => 1, "part" => 1, "partner" => 1, "sit" => 1 }
```

Please note the order of your keys might be different.

### **Quick tips**

* Recall how to turn strings into arrays and arrays into strings.

