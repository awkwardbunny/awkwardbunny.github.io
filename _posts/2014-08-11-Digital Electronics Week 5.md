---
layout: blog
title: "Digital Electronics Week 5"
---
Although the title says 'Digital Electronics,' it'll be about this past week in general as well.  
So, Othello. We got the LED's on Tuesday. It was hard for them to find and order a 10mm bicolor diffused LED, they got us some 5mm RGB ones from <a title="Sparkfun RGB LED" href="https://www.sparkfun.com/products/10820" target="_blank">Sparkfun</a>. Now, they have common anode, which means that the three colors, red, green, and blue, share an anode, the positive leg. These LEDs have 4 legs in total, and besides the common anode, depending on which of the 3 other pins is/are connected to ground, the corresponding color would light up.

Because they were 3-colored and we only needed 2, we cut off a single leg off of each LED that were going to be used. We decided to use red and green. Also because they were 3-colored, they had 4 legs, and the legs were too close to each other for them to nicely fit on either the breadboard or the perfboard. So I spent all of Tuesday and Wednesday planning how they were going to be laid out and then cutting, folding, placing, and soldering all 64 LEDs. It was tedious labor. But when it worked, it looked pretty nice. I'll have a picture up later.

Later, I've started to figure out how I'm going to be driving the 8x8 LED matrix. Here's what I came up with: the anodes are connected together by rows, and a 8-bit shift register, connected to the rows, will cycle through a single HIGH bit. The two sets of cathodes are connected by columns, and will be connected to a demux(for color) and then to the RAM chip. As the HIGH bit cycles through the rows, 8-bit data will be sent at a time from the RAM to the columns. If we do this quickly enough, it would seem as if the LEDs in every row/column are lit up simultaneously. Multiplexing.

We've realized that we wouldn't be able to finish the whole thing if we just use logic chips for the actual game mechanics, so we agreed to use an <a title="Arduino" href="http://www.arduino.cc/" target="_blank">arduino</a> for whatever we don't finish. We only have two days left to work. On Thursday and Friday, I wrote a function to serially write 8-bit data from the arduino to the RAM, where the data would then be displayed through the matrix. To write the data serially, I had to sync the timer by getting the frequency and then waiting for the first of the 16-cycle loop. I've tested it on a simple circuit, and it seems to work. <span style="line-height: 1.5;">We also designed how the inputs will be handled. That's our progress so far.</span>

Oh, we are going to be presenting at Cooper Union's Great Hall on Aug. 14th, along with all the other students enrolled in the program. The event will start at 9:30AM to some time in the afternoon. I believe there will be demos.

On a side note, one of my friends 'gets messed up for every super moon and messages me every time he does. I was told that there was a supermoon tonight (8/10). He wanted an honorable mention. Here ya go.

Away from school, over the weekend, my family, along with some others, we on an overnight camping trip. It wasn't like a 'real' camping trip, but there were campsites set up in the 'woods' and stuff. We set up out tents and hung around and ate. I was sleeping for the most of the trip. Yeah, there was a lot of sleeping and eating for me. I've just got back a couple of hours ago, watched one of Bruce Willis's Die Hard movies and took a nice shower.

On another note, I'm thinking of re-designing my blog and the website. There wasn't much of actual 'designing' to begin with, but I'll just try to change things up and make things look nicer.

uuhhhh.. signing off...?