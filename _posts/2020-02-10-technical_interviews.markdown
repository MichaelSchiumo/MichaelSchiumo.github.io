---
layout: post
title:      "Technical Interviews"
date:       2020-02-10 14:44:50 -0500
permalink:  technical_interviews
---


Well, I recently had my first practice technical interview. To say that it was difficult is a gross understatement. I always was apprehensive about this process, as I do not feel that thinking on my feet in coding situations is my strongsuit. However, the experience did leave me with a few lasting impressions, and ideas of what I need to do to improve in this area. 

The first item on my agenda is to revisit some of the fundamentals of JavaScript. The question that I was asked in the interview involved creating a nested forEach loop, which is something on which I haven't actively focused since beginning the JavaScript curriculum. Therefore, my syntax was wrong, and it was difficult for me to conceptualize the approach needed to solve the problem. The person conducting the interview was exceedingly kind, and not only guided me through the solution, but deep-dived into the reasoning behind this approach. 

Secondly, I breached a new topic that I have not encountered at Flatiron: Big-O. This refers to the amount of computing time when a system runs a sequence of code. Naturally, for applications that are in charge of managing large amounts of data, interacting with users, and otherwise working to execute seamlessly as users navigate the program, the time that it takes for a computer to comprehend the processes that have been laid out in the code is something that may sink the overall user experience. I will outline the four basic concepts in Big-O programming below.

O(1) refers to an algorithm that will execute in the same time, every time. If it is fair to make this comparison, it is an analog to a pure function, which is a function that, given the same input, will always produce the same result. Naturally, this is the optimal type of notation, as it is predictable, and takes the least amount of computing effort. However, with the complexities of programming, this is not always possible. 

O(N) refers to an algorithm, the time of which will increase in a linear fashion with an increase in the size of the dataset. This is what I encountered during my mock technical interview, in which I was asked to loop over an array and track the difference between the values of a second array and the corresponding elements in the first array using a forEach loop. The second iteration of this problem (pun absolutely intended) demanded that I create a nested loop, which falls under the category of Big-O below.

O(N^2) represents an algorithm, the processing time of which increases at the rate of the square of the size of the dataset. In a nested forEach loop, the processing time can be thought of as N x N; the first N is the processing time of the first iteration of the loop, and the second is, subsequently, the processing time of the second loop. 

Finally, O(2N) is an algorithm, the processing time of which increases exponentially with the size of the dataset. It is common to see this type of algorithm in scenarios in which recursion is utilized. 

Naturally, this information was overwhelming when I first encountered it. However, it inspired the realization of what I must do now. In response, I invested in a book on the theory of JavaScript, which will become my Bible of Coding in the coming weeks and months. Secondly, I have begun to utilize online resources, such as CodeWars, that give example questions that mimic those that may be encountered in interviews. It is safe to say that I have my work cut out for me. Cheers to many more long days!

