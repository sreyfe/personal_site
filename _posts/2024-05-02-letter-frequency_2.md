---
layout: post
title: Letter Frequency II -- Visualizations
date: 2024-05-02 10:50:00
description: My second look at letter frequency, this time in Rust and with cool visualizations
tags: 
categories: 
---
In order to better procrastinate on my master's thesis (an analysis of [my database of translations into Yiddish](https://iberz.org/)), I've been getting into Rust and cellular automata. I have been thinking vaguely about how automata could be used to model literary production. Maybe a big bimodal graph of translators and publishers, with rules governing when publishers are born/die/survive? More to be seen...

But I think I just like how cellular automata look. I used to throw text data into .bmp's and see what would come out, and these representations of one dimensional cellular automata, with their strange periodicities, have a similar feel.
{% include figure.liquid path="assets/img/cell_1.png" class="img-fluid rounded z-depth-1"%} 

Remembering, this I thought to myself: why not use these methods to take a look at the Hebrew Bible? My first idea was to convert each Hebrew letter to a numerical, then binary representation. א, as the first letter, would be 0 or 00000 as expressed in five bit binary. ב would then be 00001, ג would be 00010, all the way up through ת (10101). Final letters are encoded as their normal forms. I would then write all these binary representations to an image in the wonderful [.pbm format](https://en.wikipedia.org/wiki/Netpbm). 

In case you're not familiar, .pbm, .pgm, and .ppm have ASCII formats, which makes them very human readable and fun to manipulate. A file that looks like this:
```
P1
# This is an example bitmap of the letter "J"
6 10
0 0 0 0 1 0
0 0 0 0 1 0
0 0 0 0 1 0
0 0 0 0 1 0
0 0 0 0 1 0
0 0 0 0 1 0
1 0 0 0 1 0
0 1 1 1 0 0
0 0 0 0 0 0
0 0 0 0 0 0
```
Will end up looking like this:
<br><br>
<img src="https://upload.wikimedia.org/wikipedia/commons/a/ad/Example_of_ASCII-art_turned_into_a_bitmap_scale20.pbm.png">

Pretty cool, right? A five-bit, square representation of Genesis 1 encoded this way looks like this:
{% include figure.liquid path="assets/img/genesis_1_bw.png" class=" z-depth-1" zoomable=true%}
From left to right it reads:

|00001|10011|00000|10100|01001|10101|...|
|ב|ר|א|ש|י|ת|...|

Cool as this looks (to me anyway...), our eyes are really quite ill-equipped to read any of it. If you want you can sit there and decode byte by byte, but its very difficult to find patterns. But if we introduce color, patterns start to emerge.

So I decided to do the same basic thing but represent each of the 22 letters of the Hebrew alphabet with a different color. As luck would have it, [in 1965 one Kenneth Kelly defined a 22-color palette designed for maximum contrast](https://gist.github.com/Myndex/997244b95d84788df96f4aab8b9edeb1). I modified my code to use the colorful .ppm format, and began producing representations like this (read right to left):
{% include figure.liquid path="assets/img/genesis_1.png" class="img-fluid z-depth-1" zoomable=true%} 
Genesis 1

The letter/color key is as follows:

<h2 style="direction: rtl; text-align: right">
<span style="background-color:#FDFDFD; border: solid; border-width: 1px;">א</span>
<span style="background-color:#1d1d1d; color:white;  border: solid">ב</span>
<span style="background-color:#ebce2b; color:white" >ג</span>
<span style="background-color:#702c8c; color:white">ד</span>
<span style="background-color:#db6917; color:white">ה</span>
<span style="background-color:#96cde6; color:white">ו</span>
<span style="background-color:#ba1c30; color:white">ז</span>
<span style="background-color:#c0bd7f; color:white">ח</span>
<span style="background-color:#7f7e80; color:white">ת</span>
<span style="background-color:#5fa641; color:white">י</span>
<span style="background-color:#d485b2; color:white">כך</span>
<span style="background-color:#4277b6; color:white">ל</span>
<span style="background-color:#df8461; color:white">מם</span>
<span style="background-color:#463397; color:white">נן</span>
<span style="background-color:#e1a11a; color:white">ס</span>
<span style="background-color:#91218c; color:white">ע</span>
<span style="background-color:#e8e948; color:white">פף</span>
<span style="background-color:#7e1510; color:white">צץ</span>
<span style="background-color:#92ae31; color:white">ק</span>
<span style="background-color:#6f340d; color:white">ר</span>
<span style="background-color:#d32b1e; color:white">ש</span>
<span style="background-color:#2b3514; color:white">ת</span>
</h2>
<br>
It's still not the easiest thing to read, but some interesting patterns emerge. As mentioned in the [previous blog post](/blog/2024/letter-frequency/), there are a lot of yuds in Genesis 1, and accordingly the above representation is marbled thoroughly with a <span style="background-color:#5fa641;">nice green</span>. Due to its consecutive use, vav, which is represented with <span style="background-color:#96cde6;">light blue</span>, tends to form nice, evenly spaced, diagonal striations. It also tends to be the first color in most chapters, as in Genesis 11 and 19:
{% include figure.liquid path="assets/img/genesis_11.png" class="img-fluid z-depth-1" zoomable=true%}
Genesis 11
{% include figure.liquid path="assets/img/genesis_19.png" class="img-fluid z-depth-1" zoomable=true%} 
Genesis 19

ה, in <span style="background-color:#db6917; color:white">orange</span>, is also sprinkled evenly throughout, as are <span style="background-color:#FDFDFD; border: solid; border-width: 1px;">aleph</span> and <span style="background-color:#2b3514; color:white">tav</span>. When you look at these diagrams for long enough, you can start to pick out all the את's, which are represented by a white square followed by a dark gray-green square.

I also decided to make representations of individual verses, in order to take a look at some of the conclusions I made last time. And, as expected, Gen 10:28 is white with <span style="border: solid; border-width: 1px;">alephs</span>:
{% include figure.liquid path="assets/img/10-28.png" class="img-fluid z-depth-1" zoomable=true%}

Gen 1:23 is green with <span style="background-color:#5fa641; color:white">yuds</span>: 
{% include figure.liquid path="assets/img/1-23.png" class="img-fluid z-depth-1" zoomable=true%} 
Gen 49:19, the prophecy of Gad, has sort of a jester/Lakers look, due to the high occurence of <span style="background-color:#ebce2b; color:white">gimel</span> and
<span style="background-color:#702c8c; color:white">daled</span>.
{% include figure.liquid path="assets/img/49-19.png" class="img-fluid z-depth-1" zoomable=true%}

This approach enables an interesting mix of very close and very distant reading. It highlights the smallest unit of Hebrew (the letter), and makes it visible over large swathes of text. 

Can it help us learn anything? I'm not sure... But it sure does look cool. If you're interested, the code and all the images are available on my [GitHub](https://github.com/sreyfe/hebrew_bible_frequencies/tree/main/visualizations).