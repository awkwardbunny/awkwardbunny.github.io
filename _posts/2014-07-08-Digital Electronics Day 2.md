---
layout: blog
title: "Digital Electronics Day 2"
---
Short version: Sat through lecture about binary arithmetic, came home, started building a CPU based on a design I made last year. Proof (of the CPU):  
<a href="/wp-content/uploads/2014/07/20140708_214855.jpg"></a>
[caption]CPU[/caption]
<a href="/wp-content/uploads/2014/07/20140708_232154.jpg"></a>
[caption]Update 2[/caption]  
Quick Update: Wired addition up to 6

The long version:
In the morning, we went directly to the lab and continued to work on whatever we were working on yesterday. I had some test/demo circuits working, but I took it apart so I could use the breadboard. It almost hurt to take it apart since the wiring was done so beautifully on that one. Professor walked around and took a look at everyone's circuits and stuff. Sometime later, we got into a conversation and I showed him my unfinished CPU that I drew out in logic simulator--
I think about a year ago, Pawel (<a title="Pawel's Website" href="http://tuffbizz.com" target="_blank">tuffbizz.com</a>), Harsh (<a title="Harsh's Website" href="http://harshbaid.com/" target="_blank">harshbaid.com</a>), and I started working on a CPU design. We were all into programming and computers, and we wanted to see how the computer worked in deeper levels and how we could build one from scratch. I used a logic simulator called <a title="Logisim" href="http://www.cburch.com/logisim/index.html" target="_blank">Logisim</a> to simulate and test everything. I tried many other logic simulators, but Logisim seems to be the best software tool for such purposes and such magnitude of complexity. In logisim, and over a couple of sleepless nights, I drew out much of the CPU using basic gates, the AND, OR, and NOT.
<a href="/wp-content/uploads/2014/07/Logisim.png"></a>
[caption]Logisim simulator[/caption]

The logisim file is uploaded <a title="Logisim file" href="http://brianhong.us/public/CPU-RAM-1.circ" target="_blank">here</a>. There are many different circuits in the file, but most of them won't be too hard to figure out.  
The explanations:
 * The 'main' circuit is the largest of all, and has inputs A and B (both 8-bits) and output is fed to one of the four registers using multiplexers.
 * circuits like 'nx\ 'zx\ or 'add1' takes 8-bit input, a single bit flag input, and 8-bit output. 'nx' will negate the input if the flag is 1. 'zx' will zero the output. 'add1' would increment the output by 1.. etc
 * There are multiple versions of some circuits.
 * RAM. Since this was an 8-bit computer, I wanted to have total of 2^8 addressable bytes for RAM. RAM is made of 16 16-byte RAM (16x16= 2^8). 16-byte RAM has 16 1-byte RAM. For 1-byte RAM, I just basically used the 8-bit register.
 * MUX is a multiplexer, DEMUX is demultiplexer.
 * The last one, 'XOR add' was when I was re-writing the adder to use fewer gates.
--so I showed it to him, and he seemed impressed, or at least I'd like to think he was.

And then after lunch, we had a lecture about <del>boolean</del> binary operations and binary arithmetic. I don't think some kids quite understood, as it took us nearly 30 minutes to solve a practice question, which is pretty impressive amount of time, if you ask me.
When we went back up to the lab, I started to build the CPU, but not before I had to convert the adders to use XOR gates. I had to do so because it would significantly reduce the number of gates I would have to use and slightly the complexity of the circuit.
The two pictures above show the 16 bits of input on the left, consisting of a pair of 8-bit dip switches for input A and B. The three IC's in the center are, 4071(OR), 4081(AND), and 4070(XOR), respectively from top to bottom. On the right, you'll see an LED bar array, which resembles the output of the addition. So that's that...  
I also started on the clock circuit based on 555 timer, but couldn't remember how to wire it at the moment, so I just left it there. (Far right)
