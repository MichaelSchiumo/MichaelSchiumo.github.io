---
layout: post
title:      "Reverse String"
date:       2020-04-08 16:07:15 -0400
permalink:  reverse_string
---

I don't know about you, but the idea of going through software-engineering interviews is daunting and nerve-wracking. In fact, it has been since day one. Flatiron School did a great job with introducing some of the key concepts that seem to come up in most of the problems that I have encountered, i.e. reduce method, forEach, for, and while loops, as well as some basic manipulation of data - split, join, count, etc. Nevertheless, I have just started in on a course with UDEMY that focuses on the interview process, specifically Data Structures and Algorithms. Here, I will demonstrate and explain one of the simplest problems that someone might encounter on an interview: reversing a string with JavaScript. 

There are many ways to approach this problem, so I will give my version, as well as a second version that makes use of a more-complex method (reduce) and ES6 syntax. Naturally, the second option would be the best to use during the interview, as it demonstrates that you have a good understanding of the use of the reduce method, as well as the newest syntax, which arguably cleans up the code nicely. 

To set up the problem, we are given a string, which is passed as an argument to the reverse function. 

```
function reverse(str) {

//our code

}
```

We expect the following result: 

```
//str = "test"

//console.log(reverse(str)) => "tset"
```

Let's get started. 

My solution (which I am sure has been used before, but I'm proud of it regardless) follows the steps below:

1. Declare a variable that is set equal to the str argument that we are passed split into its individual elements. 

```
**let letters = str.split('');**
```

 This should look something like this:
 
 `console.log(letters) = ['t', 'e', 's', 't'];`
 
2. Create a variable reversedStr, which we will return at the end of the function, and set it equal to an empty array. 

```
**let reversedStr = [];**
```

3. Now, we are going to use a forEach loop to iterate over each element in our letters array, which represents each character/letter in our str argument from above.

```
letters.forEach(letter => {
//our code here 
})
```

4. Within this iteration, we are going to make use of the `unshift()` method, which moves elements onto the front of an array. In this case, each letter is added to the beginning, which gives us the desired result. First, we would add 't' to the beginning of the array on the first iteration; next, we would add 'e' to the beginning of the array, and would have` ['e', 't']`, and so on. 

```
letters.forEach(letter => {
**reversedStr.unshift(letter);**
})
``` 

5. Finally, we are going to return the reversedStr variable, and convert it from an array into a string by using the `join()` method. 

```
return reversedStr.join(''); 
```

**Solution #1:** 

```
function reverse(str) {
   let letters = str.split('');
   let reversedStr = [];
   letters.forEach(letter => {
     reversedStr.unshift(letter)
   })
  return reversedStr.join('');
}
```

Easy enough to understand, but not always obvious in the beginning. As I have said many times to people who ask how coding is going, "With coding, nothing is ever as simple as it sounds." 

Let's move onto the next solution using the reduce method. I am going to go step-by-step, and write out the entire function in the solution, as this function can be written as a one-liner. 

1. Split the string that is passed in as an argument.

```
str.split('');
```

2. Chain on the reduce method. This needs a bit of context first. 

* The reduce method takes in several arguments. First, it takes the *total value*, or the result that we will have when reduce is called on the value that we pass to it. In this case, our total value will be **reversedStr**, which is what we will return. Next, reduce takes in the *current value*, which is each character in the array that was created when we split the initial string argument. Finally, we need to pass in the *initial value*, which, in this case, we will set to an empty string, because our result will be a string. Here we go. 

```
str.split('').reduce((reversedStr, character) => character + reversedStr, '');
```

* Note that the reduce function can be written differently. The above uses ES6, but can alternatively be written as such:

```
function reverse(str) {
   return str.split('').reduce((reversedStr, character) => {
     return character + reversedStr
   }, '')
}
```

3. We return the result, like so: 

**Solution #2:**

```
function reverse(str) {
  return str.split('').reduce((reversedStr, character) => character + reversedStr, '');
}
```

Naturally, this solution is cleaner, as it can be written on one line, makes use of the ES6 syntax, and offers a bit more of a "complex" result by using the reduce method, which is notoriously tricky. 

As noted above, the idea of coding interviews still terrifies me. However, the only path forward with programming is to bang your head against the wall until, one day, you have a breakthrough; then, rinse and repeat. I enjoyed writing this, and will most likely write some more posts like this, but on more complex problems and algorithms. Until next time, stay calm, code on. 
