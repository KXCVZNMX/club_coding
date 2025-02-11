# Lesson 4: Loooooooooops!
Loops are an essential part to any programming language, and C++ is no exception. A loop has a few purposes, including saving you to write ten thousand lines of code for every single condition; iterating through a list; etc.

In this lesson, we will be talking about mainly the `for`, `while`, and an infinite loop. We will also touch on `do-while`, but you would rarely use that.

## "For" loop
In C++, a `for` loop might be the most useful loops. To iterate through a list, to get inputs from `stdin` to lists, and more. To initialise one, use this format:
```cpp
for (int i = starting_value; i < ending_value; i += step_value) {}
```

The three parts in the `for` loop initialisation is `for (starting _value; condition; step value)`

<img src="for_loop_demo.jpeg" width=300>

The starting value is easy to grasp, as it is simply where the loop will start. Say you want to start at the 5<sup>th</sup> element of an array, you will make the starting value 4 (since 0 is the first element).

The condition is where you would want the loop to end. Say you want to stop at the 8th element of the array, make `i < 8`, but as you can see, this doesn't include the 8<sup>th</sup> element. Hence, you could use the `<=` operator as well if you like.

The steps are easy to get as well. If you use `i++` (stepping by one) every iteration would be `1 + the last i`. Similarly, if you want the next to be `2 + the last i`, it would be `i += 2`.

