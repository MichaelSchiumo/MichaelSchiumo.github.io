---
layout: post
title:      "Chunked: 1 Approach to This Common Problem"
date:       2020-04-14 19:53:16 +0000
permalink:  chunked_1_approach_to_this_common_problem
---


Continuing in the quest to pass a technical interview, here is another sample problem. Today, we are going to take on a common challenge called "Chunked." Essentially, we need to take in an array and a size, and create subarrays, which we will then push into the master array, chunked. Below is the full problem statement:

 Given an array and chunk size, divide the array into many subarrays where each subarray is of length size.

Examples:

`chunk([1, 2, 3, 4], 2) --> [[ 1, 2], [3, 4]];`

`chunk([1, 2, 3, 4, 5], 2) --> [[ 1, 2], [3, 4], [5]];`

If you're a novice programmer like myself, then this problem will throw you for a loop. One of the biggest issues that I have with solving technical challenges like this is the wave of panic upon seeing the directions and the desired outcome, and the "imposter syndrome" that follows. However, the goal is for saner minds to prevail. So, let's figure out our strategy.

Initial Function:

```
function chunked(array, size){

//our code

}
```

So, let's take a minute to review what we have above. Our function takes in two inputs:

1. An array, which will be broken into subarrays and pushed into a master array (chunked).

2. A size, which represents the number of elements in each subarray of chunked.

The goal is to return an array that contains many subarrays, each with the size (number of elements) given in the inputs. However, there are two caveats here:

1. If the size is greater than the number of elements in the given array, then the chunked array will only contain one subarray with all of the elements in the given array.

For example:

`chunk([1, 2, 3, 4, 5], 10) --> [[ 1, 2, 3, 4, 5]]`

Here, the size of 10 is given, but the chunked array only contains one subarray with 5 elements, because size is greater than the number of elements in the original array.

2. If the given array is not divisible by the size, then there will be subarrays that do not match the size requirement.

For Example:

`chunk([1, 2, 3, 4, 5, 6, 7, 8], 3) --> [[ 1, 2, 3], [4, 5, 6], [7, 8]]`

Here, the last subarray only contains 2 elements, despite the fact that the size input given is 3.

**Solution #1 - For Loop**

Step 1:

The first thing that we need to consider here is what our return value should be. In this case, the return value will be the chunked array, which contains subarray(s). So, the first thing that we must do is set up this chunked array.

```
function chunked(array, size){

  const chunked = [];

  //our code
    
}
```

**Step 2:**

Now, we must consider how we will determine how many elements are in the given array. Naturally, we will iterate over the array. In this first solution, we will implement a for loop. We will iterate over each element (ele) in the given array. The beginning of our loop likes like so.

```
function chunked(array, size){

  const chunked = [];

  for(let ele of array){

   //our code
  
  }
}
```

**Step 3:**

In this step, we must define a way to determine the existence and size of each subarray within chunked. This can be accomplished by setting a variable equal to the last element (subarray) within chunked. We will rely on our traditional method of finding the last element in an array with bracket notation, measuring the length of the chunked array, and subtracting 1 from this value. It will look something like this:

```
function chunked(array, size){

  const chunked = [];

  for(let ele of array){

   let last = chunked[chunked.length - 1];
  
  }
}
```

**Step 4:**

Alright, now that we have a way of keeping track of the last subarray within chunked, we can move on to conditional statements that will be responsible for what will be pushed into chunked from our original array. It stands to reason that:

1. If there are currently no subarrays within chunked, we will want to create a new subarray, and push this into chunked.

2. If the last variable is of length size, we must create a new subarray.

3. If either of these conditions returns a truthy value, then we will create a new subarray.

```
function chunked(array, size){

  const chunked = [];

  for(let ele of array){

   let last = chunked[chunked.length - 1];

   if(!last || last.length === size) {

    chunked.push([ele]);

   }
    
  }
}
```

As you can see from the above, we use the bang operator to determine whether the value of last is truthy, or whether it is present. As stated above, if last does not exist, meaning that there are no subarrays within chunked, then we want to push a new subarray, which we do with the line of code within the if conditional. Likewise, if the last variable does exist, and is already at capacity with the number of elements equal to size, then we also want to create a new subarray. Finally, notice that we push the element (ele) into chunked as an array.

**Step 5:**

Now that we have the logic for how to handle pushing subarrays into chunked, we can move onto the second component of the conditional, which is: populating the subarray with the correct number of elements. This piece is relatively simple: if the above conditions in Step 4 are not met, then we will push the element on which we are currently iterating into the last subarray of chunked, represented by our variable, last.

```
function chunked(array, size){

  const chunked = [];

  for(let ele of array){

   let last = chunked[chunked.length - 1];

   if(!last || last.length === size) {

    chunked.push([ele]);

   } else {

    last.push(ele);

   }
    
  }
}
```

**Step 6:**

Well, we have the means to correctly create and push our subarrays into chunked! Hooray! Now, the most important piece of this entire problem: returning chunked.

```

function chunked(array, size){

  const chunked = [];

  for(let ele of array){

   let last = chunked[chunked.length - 1];

   if(!last || last.length === size) {

    chunked.push([ele]);

   } else {

    last.push(ele);

   }
    
  }

  return chunked;

}
```


For me, this solution makes sense, as it is relatively straightforward, and does not use any *magic*. However, this problem can be approached differently, and solved more concisely. I will code out the second solution in another post. Happy coding!


