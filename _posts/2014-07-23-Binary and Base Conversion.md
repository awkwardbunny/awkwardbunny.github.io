---
layout: blog
title: "Binar and Base Conversion"
---
I'm finally writing this thing.  
Usually, when we see numbers, we use the decimal system. In the decimal system, there are 10 digits: 0, 1, 2, 3, 4, 5, 6, 7, 8, 9. To count, we start at 0, then 1, all the way up to 9. After nine, we go back to zero, but we increase the next digit, giving us 10. If we have a decimal number 18457, it can be broken down to  
<pre>
18457<sub>10</sub> = 1 x 10<sup>4</sup> + 8 x 10<sup>3</sup> + 4 x 10<sup>2</sup> + 5 x 10<sup>1</sup> + 7 x 10<sup>0</sup>
</pre>

Unlike the decimal system, binary numbering system has 2 digits: 0 and 1. Like the decimal system, we start counting at 0, and then 1. After 1, we return to zero (since we only have two digits) and increase the next digit, giving us 10<sub>2</sub>. The subscript 2 tells us that the number is in binary, or base two. A single binary digit is usually called a <span style="color: #000000;"><em>'bit'</em></span> for short. Similarly to the decimal system, if we have a binary number 10010110<sub>2</sub>, it can be broken down to  
<pre>
10010110<sub>2</sub> = 1 x 10<sup>7</sup> + 0 x 10<sup>6</sup> + 0 x 10<sup>5</sup> + 1 x 10<sup>4</sup> + 0 x 10<sup>3</sup> + 1 x 10<sup>2</sup> + 1 x 10<sup>1</sup> + 0 x 10<sup>0</sup> =150<sub>10</sub>
</pre>

Back to counting, if I were to count in binary, I would write down  
<pre>
                        0 (0)
                        1 (1)
                       10 (2)--back to zero, but add a 1 on the left
                       11 (3)
                      100 (4) --back to zero, add 1 to the second,which also goes back to zero
                      101 (5)
                      110 (6)
                      111 (7)
                     1000 (8) -and so on...
</pre>

The first, or the digit all the way on the right is the ones digit. The second from right is the twos. The third, fours digit. I hope you can see the correlation. n<sup>th</sup> digit = 2<sup>(n-1)</sup>.
So a one in the fifth digit (10000) would mean... 2<sup>(5-1)</sup> = 16.
Now that we know what binary is and how to read them, we need to know how we can get the binary representation of a number from the decimal number. We start by dividing the number by 2. For example, I chose the number 218. We divide 218 by 2. We get 109 with remainder of zero. We repeat this until the quotient, the result of a division, is 0. Here it goes:  
<pre>
218 / 2 = 109 remainder 0
109 / 2 = 54  remainder 1
54  / 2 = 27  remainder 0
27  / 2 = 13  remainder 1
13  / 2 = 6   remainder 1
6   / 2 = 3   remainder 0
3   / 2 = 1   remainder 1
1   / 2 = <span style="color: #ff0000;">0</span>   remainder 1  --quotient is 0, so we stop
</pre>

No we read all the remainders from bottom to top, and we get: 11011010. Breaking it down and checking the maths, 11011010<sub>2</sub> = 218<sub>10</sub>.

These base conversions can also convert bases to ones other than 2 or 10. One of the commonly used system in programming is the hexadecimal, 16-base system. Hexadecimal has 16 digits, of which are: regular numbers 0-9, and A (equal to decimal 10), B (decimal 11), C (12), D (13), E (14), and F (15).
When converting binary to hex or hex to binary, there is an easy trick that can make things easier. Since 4 binary digits has 16 possible values, we can group 4bits to a single hex digit. By that, I mean as so:  
<pre>
101011001010 =&gt; 1010 1100 1010 -which can be converted to hex easily
                   (10) (12) (10) -decimal, but you can skip this
                     A    C    A   -single hex digit per 4 bits
       SO, 101011001010<sub>2</sub> = ACA<sub>16</sub>
</pre>