---
layout: blog
title: "Digital Electronics Day 9"
---
<h6><del>Monday:</del></h6>
This post was going to be for the whole week, but got too long.  
After finishing the 8-bit adder using the 4008 chips, I realized that there was a problem. I couldn't detect overflows. An adder should have two inputs, and an output, along with a carry out and overflow. The output is the sum/difference of the inputs. The carry and the overflow are set when the output, from two n-bit inputs, is too large to be represented in n-bits. For example, in decimal, if we have a single digit adder and we try to add 7 + 5, we get 12. 12 is not a single digit, so we get a carry.

Overflow is similar, but before I talk about this, I need to explain signed and unsigned numbers. Let's say that we're dealing with 4-bit numbers. The possible range of numbers would be 0000 to 1111 (0 to 15). There are no negative numbers in this range, therefore, no signs. That is unsigned numbering.

In order to be able to represent negative numbers, we split the range into 2 parts. 8 values for negative, 8 values for non-negative (zero to seven). So we now get the range -8 to +7. Numbers 0 to 7 are represented normally, as if unsigned (0000, 0001, 0010, 0011, 0100..) When we get to 1000, or unsigned value of 8, it becomes valued as -8 in signed numbering. So if I were to list the numbers in order with their corresponding unsigned values, we get:  
<pre>
1000, 1001, 1010, 1011, 1100, 1101, 1110, 1111, 0000, 0001, 0010, 0011, 0100, 0101, 0110, 0111
-8    -7    -6    -5    -4    -3    -2    -1    0     1     2     3     4     5     6     7
</pre>

Which sort of makes sense. Imagine that there is an invisible one to the left of 0000 -&gt;(1)0000. If we subtract one, we get (0)1111, which is equivalent to signed -1 if the first zero is disregarded.
We can perform subtraction in that way; instead of actually subtracting, we can add negative numbers because writing 7-2 is equivalent to writing 7+(-2). In order to get negative numbers we use two's complement method.
To convert a positive number to a negative, and vice versa, using two's complement, we first negate all of the bits. Then, we increment the new value by 1 to get the original number's two's complement.  
<pre>For example, 01001101 (77) would become 10110010, then by adding 1, 10110011 (-77)</pre>
Here's another thing about signed operations. When you add a binary value n with -n, you're supposed to get 0, right? Let's see.

<pre>
  01001101 (77)
 +10110011 (-77)
-------------
 100000000 (256)   --- Wait a minute, that can't be right!
</pre>
When we add using a negative number and a positive number, the carry out (if there is one) is ignored.
Back to overflow. So now we know how to add/subtract signed numbers using two's complement. But there is one thing we haven't covered yet-- what do you get when you try to add 0011 (3) and 0111(7)? Go ahead, try it.  
<pre>
  0011 (3)
 +0111 (7)
------------
 1010 (-6)   --WHAT
</pre>

As you see above, there is something wrong with that. You actually, cannot add such numbers as 3+7 would go yield unsigned 10, which goes above the unsigned range that we had before (-8 to +7). This is what is called an overflow. An overflow occurs when two negative numbers yield non-negative or  when two non-neg yield a negative.  
So I need to figure out how I could detect overflows. Thanks for reading :)