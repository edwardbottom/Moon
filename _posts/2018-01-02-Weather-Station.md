---
layout: post
title:  "Weather Station"
excerpt: "An Arduino powered weather station that displays the current weather on an LED matrix using multiplexing for
a variety of locations read into Java with the help of WireShark and the DarkSky API."
project: true
comments: true
---

This project was created as a culmination of a number of skills. The use of WireShark stemmed from an understanding of protocols 
and exchange on the internet. The code itself uses both Arduino C and Java, where Java is used to collect and process data, and Arduino 
is used to display the data. 

[Weather Station](https://github.com/edwardbottom/weatherstation)

This project was effective in integrating both higher level use of externa libraries and lower level use of bit manipulation in protocols 
between C and Java. Going between the two languages always creates room for error, and converting the bits tends to cause problems. I found these 
this to be neglable in the end as long as I remembered the correct conversions between data types and correctly set up the Serial Comm 
in Java.

Overall, I was pleased with the results and do not see alot of room for improving the project outside of increasing the complexity of data
brought in and displayed by the weather station. However, the LED matrix that I own is too simplistic for this, and I do not have a desire 
to spend more money to buy a nicer one. It would not be hard to do though, seeing as the general protocols for bringing in the data from
the Dark Sky Api and processing it already exist. 

