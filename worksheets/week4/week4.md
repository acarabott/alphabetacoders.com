# Processing - Week 4

## Multiple Pizzas

We now have a `pizza` function that lets us draw a pizza slice just by typing something like `pizza(200, 300, 400, 400);`

This means we can draw two pizzas just by doing

	pizza(200, 400, 400, 400);
	pizza(100, 200, 100, 100);

This is fine, but what if we want to draw bigger number of pizzas? With our current approach it would be a lot of copy pasting....

Fortunately computers are vey good at relentlessly doing things over and over, so good that there are specific commands to get them to do so.

## For Loops

One of these structures is the *for loop* which looks like this

	for(int i = 0; i < 10; i++) {
		// code to be repeated
	}

The code that will be repeated, or *looped* goes in the *block*, i.e. between the curly braces `{ }`.
The first bit `for(int i = 0; i < 10; i++)` determines how many times the code should be run.

This `for()` statement has three parts within the brackets: 

### 1. Counter / Iterator
	int i = 0;

Is our counter or *iterator*, starting at 0, so that we can keep track of our loops. The first time our code loops `i` will be `0`, the second time it will be `1`, the third time `2` etc.

### 2. Looping Condition

	i < 10;

This part is the condition that decides whether to keep looping. If the statement is true, we keep looping, if it is false, then we will stop looping.

In this case, the condition is that `i` is **less than** `10`. When our loop starts, `i` is `0`, so we continue looping, in the second loop `i` will be `1`, which is also less than `10`, so we keep looping. 

#### Questions:

- At which value of `i` will statement be false, and the loop stop? i.e. what is the first number after `0` that is **not** less than 10?
- How many loops will have been performed?

### 3. Increment

	i++

The final part of our for loop is used to increment our counter. In this case we are doing this by saying `i++` which means "increase `i` by `1`". This could also be written `i += 1` or `i = i + 1`.

## Row of Pizzas

Write a `for` loop and put your `pizza` function call inside it, run your code and see what happens.

### Nothing!

Nothing changed right? Well that's because all of your pizza slices are being drawn in the same place, at the same size. We need to make each pizza slice have at least a different position for it to be visible. Fortunately we have our counter `i` to help us with this.

### Changing `x` values
To make a row of pizza slices, you want each slice to have a different `x` value. To work out how to do this, write out a vertical list (maybe even on *PAPER*, with a *PENCIL!*) of `i` values, and next to it a vertical list of *desired* `x` values, e.g.

<table border="1" style="text-align:center; margin:50px auto;">
	<col width="100">
	<col width="100">
	<tr>
		<th>i</th>
		<th>x</th>
	</tr>
	<tr>
		<td>0</td>
		<td>0</td>
	</tr>
	<tr>
		<td>1</td>
		<td>?</td>
	</tr>
	<tr>
		<td>2</td>
		<td>?</td>
	</tr>
	<tr>
		<td>3</td>
		<td>?</td>
	</tr>
	<tr>
		<td>4</td>
		<td>?</td>
	</tr>
</table>

Once you have written this out, look at the `i` and `x` values and work out what arithmetic you need to do to map the values from the first column to the second.

Now use this mapping or *transfer function* in your `pizza` call's `x` argument, you should get a row of pizza slices!

## Challenges

### Changing other values

Can you make your pizza slices get bigger or smaller as the row progresses?

### Starting position

What if you don't want your pizza row to start with an `x` value of `0`, but `100`, but keeping the same distances between the slices? What do you have to do to your previous transfer function to achieve this?