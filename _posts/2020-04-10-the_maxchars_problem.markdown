---
layout: post
title:      "The "MaxChars" Problem"
date:       2020-04-10 16:10:36 -0400
permalink:  the_maxchars_problem
---


The interview preparation continues. Today, I am going to go through a short example of a common problem that is used in technical interviews, and how to use both a for...in loop, and a for...of loop, and the inherent differences between the two.

**Problem Statement**

Given a string, determine which character is used the most.

**Step 1:**

On the surface, this problem appears relatively easy. However, it did successfully trip me up, and took a while to figure out how to approach it. Disclaimer: the solution to this problem contains two loops! They are not nested loops, so the function will still have a Big-O run-time of O(N), meaning that the processing time for the algorithm will increase in a linear fashion with the increasing size of the dataset. Now, let's work through the starting point.

The data structure that makes sense here is an object. Within an object, we can assign key-value pairs; for the purpose of this problem, the key will be the character(s) within the string, and the value will be the number of occurrences within the string. So, it stands to reason that the first thing that we should do is set a variable equal to an empty object, which we will then use to do the initial count of the characters.

Note: in a coming step, we will also create another variable to track the count of each character. I will leave that out for now.

```
function maxChars(str){
 
 let charMap = {};

}
```

**Step 2:**

Now, we will attempt (and succeed!) in creating our key-value pairs within the charMap object that is defined at the top of our function. Due to the fact that we are iterating over individual characters within the given string, we will use a for...of loop. We can use this type of loop because a string is an iterable object. Later in this solution, we will see why we use the for...in loop to iterate over an object, which has enumerable properties. So, let's see how that loop will look.

```
function maxChars(str){
 
 let charMap = {};

 for(let char of str){

  //our code here

 } 

}
```

We can set the key values within the charMap using bracket notation; the object name along with the character in the string on which we are currently iterating, like so:

`charMap[char]`

Now, we want to set a value for each key that we are creating. To do this, we have to consider two things:

1.  Does the character key already exist in the charMap object?
2. If so, how do we count each additional occurrence?

We are going to rely on good ol' JS logic for this one. For the first question, if the key does not exist in the charMap, then we want to set the key for this character as itself, i.e. letter Z will become a key of "z". The value will be set to 1, because this is the first occurrence that we have encountered in our iteration. However, if the answer to the first question is that we already have the key for a given character, then we must somehow increment (*hint hint*) the count of that character. We can achieve this with the || operator, also know as "pipes." This gives us the following:

1. If the character key does exist, increase/increment the count value.
2. If the character key does not exist, set the key to that character, and set the count value to 1.

```
function maxChars(str){
 
 let charMap = {};

 for(let char of str){

  charMap[char] = charMap[char]++ || 1;

 } 

}
```

**Step 3:**

Alright, it is time to dive into the second part of this problem. First, let's create some new variables. We will create a variable called max, which will essentially keep a tab on the most commonly used character as it iterates over the string; this variable will be set to an initial value of 0. Secondly, we will create a variable called maxChar, which will be the character that is most commonly used, and will be the return value of this function. maxChar will have an initial value of an empty string.

```
function maxChars(str){
 
 let charMap = {};

 let max = 0;

 let maxChar = '';

 for(let char of str){

  charMap[char] = charMap[char]++ || 1;

 } 

}
```

**Step 4:**

As mentioned above, an object in JavaScript has enumerable properties. This simply means that, when we iterate over the object, the properties are available to us. In this case, we will use a for...in loop. Translated into English: for each character in the charMap, do something. In this case, the something is keeping track of the max number of occurrences (up until another character exceeds the max, in which case that character count will become the new max), and maxChar, which, just like max, will be replaced by the character in the string that exceeds the max count (until the iteration has concluded).

All of the above can be simplified into a simple conditional statement:

* If the current character occurs more than all previous characters, the current character count (number of occurrences) will be set to the new max, and the current character will be set to the maxChar, which will be returned at the end of the function.

```

function maxChars(str){
 
 let charMap = {};

 let max = 0;

 let maxChar = '';

 for(let char of str){

  charMap[char] = charMap[char]++ || 1;

 } 

 for(let char in charMap){
  
  if(charMap[char] > max) {

   max = charMap[char];

   maxChar = char;

  }

 }

 return maxChar

}
```

All done! Now, if we use an example string, this is what the function output would look like.

```
let str = "aaabb";

function maxChars(str){
 
 let charMap = {};

 let max = 0;

 let maxChar = '';

 for(let char of str){

  charMap[char] = charMap[char]++ || 1;

 } 

 for(let char in charMap){
  
  if(charMap[char] > max) {

   max = charMap[char];

   maxChar = char;

  }

 }

 return maxChar

}

console.log(maxChars(str)) => "a";
```

I hope that you found this helpful! Stay tuned for more.
