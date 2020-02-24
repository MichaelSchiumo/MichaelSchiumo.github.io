---
layout: post
title:      "Understanding Redux Data Flow"
date:       2020-02-24 17:06:05 +0000
permalink:  understanding_redux_data_flow
---


Redux can often seem complicated for one simple reason - there is a lot going on behind the scenes that may not always be obvious to the newly initiated coder. Here, I am going to discuss this topic, and try to foster understanding of the key aspects of how data is controlled and progresses within a Redux application. 

First, it is important to understand some key terminology. The most important thing within React/Redux is the store, which is essentially the container that stores the application-wide state. The state can only be changed via a dispatched action. Additionally, the store is where the root reducer lives, which allows us to create a state object, and call each reducer within the application. Similarly, a reducer is a pure function that combines (or reduces) the current state with the action, and produces the updated state. 

Now, actions are functions that determine exactly how the state will be changed, and send data between the application in the state. Each action must have a 'type' attribute, which determines what the action will be responsible for doing. For example, in a simple blog application, an action called 'ADD_POST' would be responsible for, as the name suggests, adding a blog post. It is important to note that an action is simply a Plain Old JavaScript Object (POJO), and can be structured as we see fit. 

Let's learn about dispatch, and how we actually call these actions. A dispatch is used to trigger state changes in the store, and does this by calling an action. As we discussed above, dispatch is responsible for determining which action must be called. A dispatch function solves two important issues. Firstly, a dispatch in Redux **persists** changes to state. Secondly, it ensures that, each time our state changes, the HTML reflects those changes. On a final note, it is important to understand that a dispatch function can be called from within an event listener. 

The last piece of the puzzle is the view, which can also be thought of as the User Interface (UI). The view reflects the most up-to-date state within the application. 

Now that we have an understanding of all of the components of the Redux Data Flow (no pun intended), we can understand how this flow is actually facilitated. First, the current state is reflected in the view. As noted above, the only way to change the state in the store is via an action; thus, we call an action, which is accomplished by the dispatch function, and trigger this sequence of events. Next, we hit the reducer, which subsequently reduces the current state and the action to build the new state. Once the new state is built, it is sent to the store once again. The final step is updating the state within the view, which is accomplished through the store. 

So, now you should have a better understanding of how Redux's Data Flow operates, and all of the moving parts that comprise the state within a React/Redux application. This is precisely why Redux is so valuable - it allows us to manage the application state from the top down, and to ensure that the application is always up-to-date with the newest state. Often, we leave React to complete these updates, which is a good example of declarative programming. Rather than hyperfocus on each element in the flow and operations of the application, which is called imperative programming, we define smart ways to handle the state, and let React handle the rest.


