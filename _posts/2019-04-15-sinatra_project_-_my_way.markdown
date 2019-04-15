---
layout: post
title:      "Sinatra Project - "My Way""
date:       2019-04-15 23:17:13 +0000
permalink:  sinatra_project_-_my_way
---


This one was tough, that's for sure. Learning about the MVC framework was difficult enough, but actually putting it into place was even more of a challenge. However, I did enjoy this project, because it finally gave me the ability to "see" my work in progress. What I mean by that is that I could check my GET and POST routes, see whether my password authentication was working, seed my database with dummy accounts, and edit exercises that I added to my application, "Gym Buddy." Below is the complete list of requirements for the project:

* Used Sinatra to build the app
* Used ActiveRecord for storing information in a database
* Included one User model and one Exercise model
* Included one has_many relationship on my User model (User has_many exercises)
* Included one belongs_to relationship on my Exercise model (Exercise belongs_to User)
* Included user accounts with unique login attribute (username). Used ActiveRecord validation helper uniqueness to ensure that the username and email address has not been used before
* Ensured that the belongs_to resource (exercise) has routes for Creating, Reading, Updating and Destroying
* Ensured that users can’t modify content created by other users by comparing the user id of the currently logged in user with the user id of the record they are trying to modify
* Included user input validations for creating a new user and exercise record to make sure no fields are left blank
* BONUS - not required - Displayed validation failures to user with error message using Rack Flash
* My README.md includes a short description, install instructions, a contributor’s guide and a link to the license for my code

Meeting all of these requirements was certainly a lot of hours and a lot of caffeine. However, I did learn a great deal about the actual functionality of the material that we have been learning. For example, I learned more about how the ActiveRecord authentification system works, especially with regards to the macros, such as **has_secure_password** and **validates :username, :email, presence: true**. Additionally, I enjoyed the Rack::Flash feature, for some odd reason. The idea that I could create an application that communicates with the user was definitely inspiring, and a novel experience.

Another thing that this project did was encouraged me to consider other, functioning websites as templates, with all of the details filled in. Things such as logging into Facebook or searching something on Google made me realize the value of what we are learning; forms, password security, cookies, sessions: all of these seemingly simple building blocks form the foundation for nearly all websites. 

Furthermore, this lab forced me to think about refactoring, and making my code as simple and 'readable' as possible. For instance, I will display the before and after versions of my code for the PATCH method in my Exercises Controller: 

BEFORE 
```
patch '/exercises/:id' do
    if params["exercise"]["name"] == "" || params["exercise"]["muscle_group"] == ""
      redirect to '/exercises/:id/edit'
    else
      @exercise = Exercise.find_by(id: params[:id])
      if @exercise && @exercise.user == current_user
        if @exercise.update(name: params["exercise"]["name"], muscle_group: params["exercise"]["muscle_group"])
          flash[:message] = "Exercise sucessfully updated."
          redirect to '/exercises'
        else
          redirect to '/exercises'
        end
      end    
    end
  end
```


AFTER:
```
patch '/exercises/:id' do
    @exercise = Exercise.find_by_id(params[:id])
    @exercise && @exercise.user == current_user
    @exercise.update(name: params["exercise"]["name"], muscle_group: params["exercise"]["muscle_group"])
      flash[:message] = "Nice job! You have successfully updated this exercise."
      redirect to "/exercises/#{@exercise.id}"
end
 
```

As you can see, my first attempt was a cacophony of nested if/else statements. There was so much going on in that snippet of code that it was difficult to see exactly what was necessary and what was not. Ultimately, removing the conditionals nearly halved the length of the code, whilst also making the final version much more easy to understand. 

Overall, I am happy with the result of this project. It makes me look forward to Rails, when most of the macros and frameworks will be built through metaprogramming, as this was not the case for Sinatra. I even had to write migrations! Oh, the humanity!



