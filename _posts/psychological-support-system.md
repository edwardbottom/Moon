---
layout: post
title:  "Moon Jekyll Theme"
date:   2016-04-06
excerpt: "An application made to help psychologists monitor their patients mental health on a daily basis"
project: true
tag:
-project
-arch hacks
-psychology
-java
comments: true
---

This project is a software designed to be used by psychiatrists to send SMS based surveys through a JavaFX interface to their patients
to check on and track their general mental health and alert the psychiatrist by SMS message if  sudden changes in a patient’s mental 
health occur. PSS was designed during Arch Hacks 2017 by myself and Christian Anyanwu. The goal of the project was to help psychologists, 
which there are all too few of in the world, efficently and easily track their patients mental health. 

The back end for the project was done purely in java and used the twilio api. The general idea is that the software reads and writes 
questions to a file. These questions are read into java and send as SMS based messages to patients who respond to the questions with 
numbers. The systems looks for general changes and trends in the patients mental health and if any changes occur, the software will 
alert the psychologist with a message that the patient has had a sharp change in their mental health (either positively or negatively)
and that they should check in on them. The psychologist is given a password protected login with a modifiable series of questions and 
the ability to add and delete patients as needed. 

I enjoyed working on this project and believe that it has the potential to make a big difference in mental health. There is a global shortage
of mental health professionals and an ever growing need for them in the modern world. I have considered further developing this applciation
and potential marketing it to psychologists as a simple means of checking in on patients regularly. 

