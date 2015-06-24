---
layout: blog
title: "Digital Electronics Day 1"
---
So this is where the fun stuff begins. I'm going to be talking about electronics and stuff. Yay. I didn't really like writing "Dear journal..." kind of things.
On the first day, the program I enrolled in gave me a kit of parts and tools and components, which I was really happy with. They supplied everyone with pairs of wire clippers, wire strippers and pliers. The component box had resistors, LED's, some IC's and some other switches and such. Other than those were 2 breadboards and a battery pack we were to use.  
<a href="/wp-content/uploads/2014/07/20140707_234652.jpg"></a>
[caption] Electronic components in the kit[/caption]

ALSO, I have a fantastic and awesome professor, Professor Risbud, and two wonderful TA's, Jen and Ahuva. So during the lecture, the students learned about number systems in different number bases. Working with computers and electronics for couple of years, I've had this lesson dozens of times. You know, I might start my own computer/electronics tutorials. What the hell, for info on base conversion and binary and all the other cool stuff, check out my 'lecture' <a title="Binary and Base Conversion" href="http://blog.brianhong.us/2014/binary-and-base-conversion/" target="_blank">here</a>.  
So that happened. In the kit were mostly 4000 series logic chips, so I decided to hook some of them up and try them with some LED's. I've done lots on logics before so I'll make another lecture kinda thing uh...
<a href="#" target="_blank">HERE</a>. But basically, a logic gate, or binary operation, takes input and produces output depending on the input. Sounds logical. Here, I've powered the 4081(left) and the 4071(right) chips to perform AND and OR operations based on switches 1, 2 (AND) and 3, 4 (OR).
<a href="/wp-content/uploads/2014/07/20140707_234532.jpg"></a>
[caption]Logic Gates[/caption]

These two gates, the AND and the OR are two of the three most basic gates. The third is an unary, which means it had one input, operator called NOT. You can probably assume what it does. It negates, or NOTs the input. Using these gates, one can link together these operations or gates to form larger and more complex functions. One example being a calculator. That is the basic concept of digital electronics. (ehh not really) (yes kinda really) When I got home, I had some time left, so I wanted to test out a different chip. Of the components I have, the 7-segmented display seemed the coolest, and after looking through the pile of IC's, I found the 4511. The 4511 is a BCD to 7-segment decoder and driver. BCD stands for Binary-Coded Decimal, which means a number in binary. The 7-segment display looks like this:
<img src="http://www.andremiller.net/wp-content/uploads/2006/03/7seg_pinouts.png" alt="" width="163" height="239" />
[caption]7-Segment Display[/caption]

Chances are, you probably have seen one before. I chose this picture because it had the same pinout configuration as mine did. Each red section is a segment, and will light up if wired correctly. The two center pins on the top and bottom are the common ground. Then, you should see each pin labeled. Applying 3v-5v to each of these labeled pins will light up the corresponding segment. The 4511 takes in 4 bit binary input, which would resemble a number, and decodes it into the 7 output values to be used for 7-segment display. So I wired them up properly and added a 4-bit dip switch for the binary input.

[gallery ids="61,62,63"]

TA-DA! Well, that's all I did for today.