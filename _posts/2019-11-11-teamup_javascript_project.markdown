---
layout: post
title:      "TeamUp Javascript Project"
date:       2019-11-11 16:43:03 -0500
permalink:  teamup_javascript_project
---

Although I was apprehensive about the complexity of this project, I was very excited about the subject of my application. Essentially, I approached the idea for the project by attempting to attack a problem that I have had in the real world; namely, finding enough people to play a pickup game of soccer. The overaching idea for the application was to have a means for people to organize matches based on the number of players that are required for a game. For example, if a soccer game requires 22 people to play, the match would only be organized upon reaching 22 participants. Naturally, the application that I ended up building was much simpler in its functionality; however, it leaves me hopeful for the day when I can return to this project and build it into something that can be used for everyday life. 

The Javascript portion of this project really challenged me. After finishing up the Rails section of the project, I had newfound appreciation for my fluency in Ruby. This was a happy moment in my coding career. However, for me, Javascript is not as straight-forward as Ruby. For instance, the idea of event listeners and how forms are displayed in JS stands in stark contrast to the methodical way in which Rails sets up views and forms. To expand on this, it was difficult to conceive of an application that was not navigated by changing URLs. Instead, forms and show "views" in this project are handled by wiping the DOM and using Event Listeners to control the data that is displayed to the user. 

On a different note, I do appreciate the idea of asynchronicity in building web applications. As with many things that I have learned throughout the Flatiron curriculum, the method of displaying information on a webpage whilst using an asynchronous callback function is something that we all encounter on a daily basis; yet, it is something that has never crossed my mind. It seems that the more I learn about web development, the more that I realize how little I actually do know. Nevertheless, completing this project has given me a newfound confidence that I CAN build these projects, and, hopefully, solve some real-world problems. 

One of the difficulties that I encounterd when building this project was trying to understand the structure of the HTML code that I was both generating via functions and handling in the index.html file on my frontend. This did present many opportunities to learn about the nature of debugging for JS applications, specifically playing around in the Elements tab in the console. Although I did eventually figure out the HTML styling for most of the things that I wanted to accomplish, there is still a lot more on that front that I would like to conquer. 

Another issue that turned into a major setback was creating a "Home" button to return to the initial page. This was more of a conceptual challenge. As I mentioned above, I grappled with the idea of displaying information on a Single Page Application. This was accomplished by creating two functions, one that wipes the DOM on each refresh, and one that re-renders information on the home page upon the click of the button. 

The final, and most difficult, challenge for me in building this project was trying to build functions that are dependent on each other in a logical and chronological manner. For instance, creating render and fetch methods was difficult. In my TeamsForms.js file, I have a fetchTeams() method, which calls renderTeams() within itself. Furthermore, renderTeams() calls two methods within itself. This "Russian-nesting-doll" approach to building functions gave me a decent amount of trouble, as there was no way of testing the functionality of a given function without completing that specific chain of events. 

I look forward to learning Redux and React and further building my styling skills with HTML and CSS. I hope that my next project will be functional and beautiful!











