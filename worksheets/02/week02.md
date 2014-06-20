# Processing - Week 2

## Task: Make a pizza slice

![Pizza](/worksheets/02/images/pizza.png)

Using the `arc` function, draw a slice of pizza

Here's a reminder of the `arc` function and a diagram showing useful values for start and stop, which are in *radians*

	arc(x, y, width, height, start, stop);

e.g.

	arc(240, 240, 100, 100, HALF_PI, PI + HALF_PI);

Instead of using radians, you can use the `radians` function which will convert a value in degrees (0-360) into radians, e.g.

	// this is the same value as PI
	radians(180);

![Radians](/worksheets/01/images/radians.png)


### Colour

Make your pizza slice yellow, by using the `fill` function before your `arc` function.

`fill` has three parameters: *(red, green, blue)* which are values from 0-255. Try these examples to understand how these values work, then set your pizza slice to yellow.

	fill(0, 0, 0);

	fill(255, 255, 255);

	fill(255, 0, 0);

	fill(0, 255, 0);

	fill(0, 0, 255);

	fill(160, 0, 130);

You can also use a colour picker to find the right values, which is visual way of finding the colour you want

A free online one: [http://www.colorpicker.com/](http://www.colorpicker.com/)

### Pepperoni

Add some red slices of pepperoni to your pizza using the `ellipse` command (don't remember it? look it up in the [Week 1 Worksheet](/worksheets/01/)) or the [Processing Reference](http://processing.org/reference/)

Your pizza should remain yellow, but your pepperoni slices should be red. The order of your functions is very important!

### Crust

Let's add a crust to our pizza using the `strokeWeight` function, which adds a border to shapes. This needs to go BEFORE we call our `arc` function, otherwise it will have no effect.

`strokeWeight` takes one argument, which is the width of the stroke in pixels, so should be a number.

	strokeWeight(weight);

#### Crust Colour

Set the colour of your crust using the `stroke` function, which has three parameters: `red, green, blue` just like `fill`. Pick a nice colour for your crust

#### Crusty Pepperoni

Does your pepperoni now have a nasty crust? That's because the `stroke` and `strokeWeight` commands apply to all shapes drawn after it. To turn the stroke off we use the `noStroke();` function AFTER our pizza slice, but BEFORE our pepperoni.

#### Crust Ends

If our pizza slice has been *sliced* then how come there are these round ends to our crusts?!

We can change this using the `strokeCap()` function which can take the values `SQUARE` `PROJECT` or `ROUND`.

Try each to see which looks best.

## Now make your pizza crazy colours and shapes :)