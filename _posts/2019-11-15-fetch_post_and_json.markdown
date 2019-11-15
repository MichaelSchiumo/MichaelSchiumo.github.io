---
layout: post
title:      "FETCH POST AND JSON"
date:       2019-11-15 15:15:34 -0500
permalink:  fetch_post_and_json
---


```
Yesterday, I had my assessment for the JavaScript and Rails project. Although I had a solid understanding of the way in which my code was working, I did have several gaps in clarity concerning the use of fetch, and how the fetch function takes in, manipulates, and processes JSON. 

During the live coding session, I was challenged to build a prototype function that processed a fetch POST request, and created an object with the returned JSON data. This function, called simply render(), was built in the Team class of my application. Essentially, this render function encapsulated the process of generating the dynamic HTML for each Team object to be created, as well as the “click” event listener that converts each name element generated to an 'a' tag, with a corresponding 'href' attribute. Once this function was created, the next task became calling this function within the fetch POST that was mentioned earlier. 

Originally, my fetch POST request was a function called saveTeam(), which only handled the POST request, and did not generate any new objects. We know that when we send a fetch GET request, we receive back data, convert the data into JSON, and then use this JSON to render information to the page. Naturally, we build on this function with further functions that handle how, when, and whether it is displayed to the DOM. In the case of the fetch POST, we take in two arguments: the fetch URL, and the configObj. The configObj consists of the method type (POST), the corresponding headers, and, finally, the body, which is the stringified JSON data. 

Once we receive the response from the fetch POST request, we convert the response into JSON using Javascript’s .then syntax. Once we have accomplished this, we once again call .then, and use the JSON to create new objects. Naturally, JSON comes back in the form of a nested object. Therefore, when we use the new Team() syntax, what we put into the parentheses cannot simply be JSON. We need to access specifically what the new object’s attributes will be. Thus, when we open up the JSON object, we see that its attributes live within the data object. So, when we create this new object, what we pass into the new Team() is JSON.data.attributes. We set this new object as a variable, like so: let newTeam = new Team(json.data.attributes). Finally, we call the render() method on the newTeam object. 

```

