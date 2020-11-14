---
layout: post
title: "Map Reduce Functions in Ruby"
date: 2020-11-14 09:04
---

Using map and reduce functions instead of using iteration methods can make for cleaner and easier to maintain code.
In this blog, I'm going to share with you how to use these methods in Ruby since reduce in particular can be confusing to new programmers.
Using map allows you to map a function over an array/list, object/hash, or other data structures and returns a data structure with the items processed.
Reduce, on the other hand, allows you to optionally start with an intial value and then reduce the values of the data stucture with that value according to the anonymous function you pass it.


## Ruby

In Ruby, there are a great many convenience methods (a.k.a., enumerators) which part of the native data type classes. This make Ruby a very enjoyable language to program in and you seldom, if ever, need to use iteration again.
Enumerators in Ruby, including the map and reduce enumerators, take a block which is yieled to the enumeration method. In terms of syntax, one may choose to either use a do end block or a curly brace block.

### .map
Using the do end block, this is how you could multiply an array of numbers by 3 and return the resultant array.

```ruby
[1, 2, 3].map do |num|
  num * 3
end

# [3, 6, 9]
```

The equivalent of this using an inline block with curly braces would be:

```ruby
[1, 2, 3].map { |num| num * 3 }

# [3, 6, 9]
```

Notice we are just passing an anonymous function as a block to map which is a method of the native datatype Array.

### Reduce
Using the do end block, this is how you could multiply an array of numbers and return the resultant value.

```ruby
[1, 2, 3, 4].reduce do |tally, num|
  tally * num
end

# 24
```

The equivalent of this using an inline block with curly braces would be:

```ruby
[1, 2, 3, 4].reduce { |tally, num| tally * num }

# 24
```

Reduce can also optionally take a parameter which serves as the initial value. In this example, if we wanted to start with a value of 8, we would write the following:

```ruby
[1, 2, 3, 4].reduce(8) { |tally, num| tally * num }

# 8 * 1 * 2 * 3 * 4 == 192
``` 

We could have included the parentheses with an empty argument after the reduce method (i.e., .reduce() ), but of course that is the beauty of Ruby that it wants to make it easier for you as a programmer, so we don't need to include it.

I hope this blog will help to make clear the importance and utility of these two enumerator methods which are available to you from the base classes in Ruby.
Looking forward, one should also look at the #each, #select, #tap methods to expand your knowledge of Ruby enumerators.
