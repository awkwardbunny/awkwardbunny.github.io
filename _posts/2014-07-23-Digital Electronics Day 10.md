---
layout: blog
title: "Digital Electronics Day 10"
---
So I did figure out how I could detect the overflows.
I have looked up how overflow is normally detected. <a title="Overflow Detection" href="http://www.cs.umd.edu/class/sum2003/cmsc311/Notes/Comb/overflow.html" target="_blank">This</a> page shows how (the second diagram towards the bottom of the page for signed numbers), but I cannot use that since it requires the carry in for the last bit. I cannot get the last bit adder since I am using the 4008 chip which has 4 full adders linked internally. But here's what I figured.  
If you haven't noticed by now, the most significant bit in signed numbers denotes whether the number is negative or not. One if negative, zero if non-negative. Go back and check it out. Now we can use this property to check if the result is of the same sign as the two inputs. I did some quick boolean maths and got this.  

<pre>
A7 = 7th bit of input A
B7 = 7th bit of input B
S7 = 7th bit of output (sum)
O  = overflow
I drew the truth table for when the overflow is true:
<span style="text-decoration: underline;">A7 | B7 | S7 || O</span>
0  | 0  | 0  || 0
0  | 0  | 1  || 1        Using minterm expression of this table, I got
0  | 1  | 0  || 0
0  | 1  | 1  || 0

<span style="text-decoration: overline;">A7</span> <span style="text-decoration: overline;">B7</span> S7 + A7 B7 <span style="text-decoration: overline;">S7</span> = Overflow
1  | 0  | 0  || 0
1  | 0  | 1  || 0
1  | 1  | 0  || 1
1  | 1  | 1  || 0
</pre>

So I drew that up in logisim.  
<a href="/wp-content/uploads/2014/07/Overflow.png"></a>   
[caption]The 3 gates on the left is the expression to detect overflow[/caption]

The two chips in the middle are the 4008 4-bit adders. Next step is to design rest of the ALU. But before, I'm going to first determine what operations my ALU would be able to perform.