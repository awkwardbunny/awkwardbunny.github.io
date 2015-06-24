---
layout: blog
title: "Digital Electronics Week 4"
---
Wow, it's almost been 2 weeks since I last made a post.  
But it's not like anybody reads them :/  
Anyways, during the last 2 weeks, we were working on our final project that we will be writing a paper about and also be presenting. At first, we were going to work on the 4-bit computer, but it didn't seem like we had the time to actually finish it. So instead, we decided to build an enigma machine kind of thing that could take data and encrypt using a certain encryption scheme. After the weekend, when we actually started to think how this is going to work, we decided it was too boring and dull.

So we wanted to build a game called <a title="Neutreeko" href="http://www.neutreeko.net/neutreeko.htm" target="_blank">Neutreeko</a>.  
It's a turn-based 2-player game played on a 5 by 5 gr.... just click the link.  
It was first introduced to us by one of the TA's, who wrote an AI for it and a text-based interface with python.
Oh yeah, we formed groups, and mine has Matthew, Malcolm (he's the guy in one of the pictures of the lab I uploaded), and me in it.
To first plan things out and see how it's gonna go down, I quickly drew up a program in Java that allowed a 2-player game with either a computer or another person. I haven't done the computer AI, so as of now, it does a random move. It can be found <a title="Neutreeko GitHub" href="https://github.com/awkwardbunny/Neutreeko" target="_blank">here</a>. It uses the <a title="LWJGL" href="http://lwjgl.org/index.php" target="_blank">LWJGL</a> library, along with <a title="Slick2D" href="http://slick.ninjacave.com/" target="_blank">Slick2D</a>.
After about two days or so, we changed our plan again, to build Othello the board game. Yesterday, Malcolm or Matthew had this idea of outputting a quote from Shakespeare's Othello every time a player made a move. Ehh.

This past weekend, I've been working on designing the display and trying to test it. The display will be an 8-by-8 matrix of bi-colored LED's. My plan is to multiplex the matrix, row-by-row, to show the pieces on the board.
Here's how multiplexing works:  
Let's say, for example, you have to control numerous LED's, but can only control a single LED at a time. In this case, you would loop through each LED and show its corresponding value (on or off), but here's the catch, we have to do it very quickly, so that they blink at high frequencies and so that, to us, each of the LED's seem constantly on.
I'm also going to be using some RAM chips to store some data, such as the pieces locations and such. We may use a 4-bit ALU to simplify some operations, since we already have that at our disposal.

Meanwhile, Malcolm was coding the game logics and such using <a title="Processing" href="https://www.processing.org/" target="_blank">Processing</a> to first lay out how logics were going to work. I haven't got to see it yet.  
Today, Aug 4th, I had some issues with the LEDs. There were 8 of them wired in parallel, and the output current from the logic ic chip wasn't enough at all to light up all 8 effectively. Couple of hours later, with help of a substitute TA Chris, we were able figure out a way to amplify the current, using 2N222 bjt NPN transistors, by pulling more current from the main power rails.

Oh yeah, on another note, my cousins from Korea went back today, soo... I'll be sleeping on my bed today