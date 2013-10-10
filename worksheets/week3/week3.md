# Processing - Week 3

## Functions

We have used many of Processing's built in functions, such as `ellipse`, `rect` and `fill`.

You can recognise a function *call* or *execution* because it is an word followied by parentheses (round brackets). There can be values inside the parentheses (called arguments) or no values at all e.g.
	
	// The value of 20 is passed to the function
	strokeWeight(20);

	// No values are passed
	noStroke();


We can write our own functions, this is useful for many reasons which we will see. Here is a function that does nothing called doNothing.

	void doNothing() {
		// This is where code would go
	}

Let's make a function that actually does something....

## Task: Pizza Function

We are going to write a function that will draw our slice of pizza from last week, to do this we can copy paste our pizza code into a new function. Our code should now look like this:

	void setup() {
		size(480, 480);
	}

	void draw() {
		// Pizza code removed from here
	}

	void pizza() {
		// Pizza code pasted here
		fill(243, 240, 35);
	    
	    stroke(212, 125, 49);
	    strokeWeight(20);
	    
	    arc(240, 240, 400, 400, radians(250), radians(320));
	    fill(200, 40, 40);
	    
	    noStroke();
	    strokeWeight(2);
	    ellipse(270, 80, 40, 40);
	    ellipse(270, 130, 30, 30);
	    ellipse(220, 100, 30, 30);
	}

Now to draw our pizza we need to call our `pizza` function, we do this just as we would draw any other shape; in our draw function.

	void draw() {
		pizza();
	}

### Why?

> "Sensei, why is this useful? It looks the same as before, you have taught us nothing."

### Because many

Now that we can draw a slice of pizza just by typing `pizza()` we can draw ALL THE PIZZAS! Try typing `pizza();` twice, just as you would with two `ellipse`s

	pizza();
	pizza();

### Still same

> "Sensei, it is still the same, you have still taught us nothing"

### Because same

> All anyone can teach you is nothing, they can only show you the way, you must learn for yourself

It looks the same because our two slices of pizza are in exactly the same position, what we need to do is be able to make pizza slices with different `x` and `y` values, just like we do with other shapes.

## Parameters

When we draw an `ellipse` we pass it four values: `x`, `y`, `width`, `height` 

	ellipse(50, 100, 150, 150);

We need to change our `pizza` function so that it accepts `x` and `y` values, we do this by adding parameters.

	pizza() {
		// code...
	}

**Becomes**
	
	pizza(int x, int y) {
		// code
	}

The word `int` before `x` and `y` is the *type* of the value that will be passed to the function.

We are going to be passing Integers (whole numbers) because we are dealing with pixels, so we use the type `int`. 

Our pizza function now has two parameters: `x` and `y`. The values that are passed in are called *arguments*, so we would say "Use the `x` argument for the `x` position of our arc"

### Using parameters

We now need to use this in our pizza code, start by replacing the `x` and `y` values used in `arc` with the arguments `x` and `y`.

	arc(x, y, 400, 400, radians(250), radians(320));


## Many Pizzas

Now call your pizza function twice, passing in different values for `x` and `y`

	void draw() {
		pizza(50, 200);
		pizza(200, 200);
	}

TWO (badly teleported) PIZZAS!

### Moving the pepperoni

If we want our pepperoni to move with our pizza (and we do) we are going to have to use our `x` and `y` arguments on our pepperoni `ellipse`s as well. Try this and see what goes wrong....

Now fix it!

## Task: Width and Height

Add `w` and `h` parameters to your `pizza` function, which influence the width and height of your pizza slice AND pepperoni.

*Protip:* Your pepperoni need to be proportional to your pizza slice, a percentage of its size. The easiest way to do this is to multiply by a decimal:

	w * 0.5; // 50%

> Sensei, why not divide by 2?
	
	w / 2; // also 50%

Well, sure, everyone knows that to make something 50% of the size you can divide by 2, but what if you want it to be 7.25% of the size? Then you need to divide by 13.79310345

It is much easier (for your poor brain) to do
	
	w * 0.0725;

### Bonus Tasks: strokeWeight

Make the stroke weight of your crust adjust according to the surface area of your pizza slice (oooh, fancy).

