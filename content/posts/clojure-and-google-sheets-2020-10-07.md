+++
date = '2020-10-07T11:40:07+02:00'
draft = false
title = 'Clojure and Google Sheets 2020 10 07'
+++


I’ve created a simple example with clojure using java google sheets SDK to integrate with google sheets.

The example read some IBOVESPA stock prices

This is possible because of clojure and Java interop

“With the sheer amount of Java code in production (and more being written every day), no modern programming language can hope to succeed without being able to interoperate with it. Rich Hickey choose well when he picked the JVM to host the Clojure language. Not only does Clojure benefit from state-of-the-art technology (raw performance, HotSpot, just-in-time compilation, adaptive optimization, garbage collection, and more), but also it makes the goal of seamless Java interoperability easier to achieve. The result is that Java interop with Clojure is both elegant and easy to use. “ — Clojure in action (chapter 5)

You can see the repository example here https://github.com/pvgomes/clojure-google-sheets

or can see how to run the read and write using this example by this video


Clojure
Google Sheets Api
