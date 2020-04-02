---
layout: post
title:      "Promises...and Why We Need to Resolve Them"
date:       2020-04-02 21:19:05 +0000
permalink:  promises_and_why_we_need_to_resolve_them
---

Today, we embark on the journey of figuring out promises, and I promise to resolve it (pun indubitably intended). First, let's discuss why they are necessary, and the advantages that they offer in working with asynchronous code and different APIs. 

So, what is a promise, and why do we need to resolve them? Well, the answer begins with a simple fundamental: the JavaScript engine, or the way in which code is processed with JavaScript, is highly structured. JavaScript code goes through several phases, from the initial read of the code, to the execution of functions within the code. The pivotal point is this - two pieces of code within JavaScript cannot run simultaneously. The solution to this problem is - you guessed it - promises. Promises allow us to write asynchronous code. 

Writing asynchronous code allows the JavaScript engine to work on multiple processes at the same time, making progress in multiple directions simultaneously. In essence, it allows for a more streamlined rendering to the DOM; the rendering of the page is not halted by a certain block of code that takes a relatively long time to complete. For example, on complex web pages, where many different types of content is being loaded (images, sounds, information that is pulled from an API or another source), writing asynchronous code allows us to render **something** to the page as the other elements are in progress. Otherwise, we would see a blank page until each bit of code is completed in order. 

Promises are, by definition, binary; they can only be run once, and will be either **resolved** or **unfulfilled**. From here, we add callbacks with the `.then()` syntax. As advertised, `.then()` handles the next step. If the promise is successful, a certain callback is invoked. If the promise is not resolved, then there is another callback function to handle that response. In a fetch request to an API, it is common to see a `.catch` chained onto the promise chain, which is used to `console.log()` errors, or to invoke another callback. Here is an example from my portfolio project, [TeamUp](https://github.com/MichaelSchiumo/teamup-sports-js-rails-api), which allows users to create rosters for their favorite sports teams: 

```
function fetchTeams() {
  return fetch(TEAMS_URL)
      .then(response => response.json())
      .then(json => {
        renderTeams(json)
      })
			.catch(error => {
			console.log(error)
			})
  };
	
```

Here, we have a very simple fetch request. Essentially, we are making a GET request to the API, which uses the TEAMS_URL. Once this request receives data, we chain a `.then()` onto the promise chain to handle the response, which is subsequently parsed as JSON. We add another `.then()` to pass the JSON that we have parsed from the initial GET request to another function, which renders the teams to the page. At the end, we have a `.catch()`, which is responsible for logging out any errors that may occur. 

This serves a simple purpose. Naturally, loading simple text to the DOM will be quicker than a fetch call to an API, which must handle and parse data. Thus, it is fair to say that promises allow certain processes to happen in the *background* without halting all elements from being rendered. This process is so quick that it is invisible to the naked eye. However, without asynchronous code, it would be brazenly apparent. I remember the days of dial-up internet, and how long it took to load a webpage. Do you? 
