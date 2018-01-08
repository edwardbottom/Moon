---
layout: post
title:  "Tinder Bots"
excerpt: "Bots made in Tinder using both Python and Java. "
project: true
comments: false
---

This project came out of a desire to learn more about using open source software and external libraries. The original plan for the project 
was to use python from the start, but a friend that I began the project with prefered to use Java. The intial setup in Java proved problematic
as I had trouble integrating the external library from GitHub with my own files. After some struggling, and a few messages to friends, 
this problem was solved using Maven. 

The code in Java was not hard to write. I considered sending an email with the results of the bot, but decided against it. I did however 
abruptly start running into null pointer exceptions in Java and at the time thought the project had bugs in it. It actually turned out 
to be that I had sent the api too many requests and I was nolonger able to get data from the api. Additionally, some of the features in 
the external library had not been finished by the creator, and the python library pynder appeared to have more functionality. 

Needless to say, I was still able to use the same account in python as it initialized the session differently than the Java library. I did
eventually run into the same problem, but I managed to build another functional bot using the available get requests for the account. 

I did incorperate filters based on user input of the gender, distance, and age of the user. I was going to incorperate horoscopes, bio 
descriptions, and messaging features into the bot, but decided that I had done almost everything I wanted to do with this project and did
not want to wait for more get requests on the api. 

If I were to return to this project in the future, I would consider adding in the messaging features and more specific filters, but as it 
stands, I have no desire to do so. The link to the two codes on my GitHub page is listed below. 

[Tinder Bot](https://github.com/edwardbottom/tinder-bot)
