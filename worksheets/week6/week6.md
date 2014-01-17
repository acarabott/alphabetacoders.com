# Processing - Week 6

## Loops and lines

Let's revisit `for` loops, this time to draw sets of lines.

	void setup() {
		size(480, 480);
		strokeWeight(2);
	}

	void draw() {
		for (int i = 20; i < 400; i += 8) {
			line(i, 40, i + 60, 80);
		}
	}

### This loop 

- Uses a counter that starts at 20 `int i = 20;`
- Continues as long as the counter is under 400 `i < 400;`
- Increases by 8 after each loop `i+=8`

### The lines

The arguments for line are the co-ordinates of the two points/ends of the lines: `line(x1, y1, x2, y2)`

- The x1 value uses the counter value: `i`
- The y1 value stays constant at `40`
- The x2 value uses the counter value `+ 60`, so it is always 60 pixels to the right of `x1`.
- The y2 value stays constant at `80`, so 40 pixels lower than where the line started

So we get this



![](/worksheets/week6/images/lines1.png)

## Fanning the lines

Now your goal is to fan the lines out, so they aren't all parallel, like this:

![](/worksheets/week6/images/lines2.png)

Some hints:

- There are four arguments to `line()` only one of them has actually changed.
- It will need to increase by an amount that *increases* for each loop e.g.
	- If it were 10 on the first loop
	- It would be 15 on the second loop (difference of 5)
	- And then 22 on the third loop (difference of 7)
- To achieve this try multiplying the number instead of adding to it (start at 2 and work from there)

## Kinking the lines

Now add a kink to the lines to achieve this:

![](/worksheets/week6/images/lines3.png)

You actually achieve this by drawing a second line, but what should the arguments be?

## Making the lines your own

Now alter the sketch, and use the [processing reference](http://processingjs.org/reference/) to make this sketch *your own*. 

Some ideas:

- Lines be different colours (a gradient would be easy to achieve)
- Lines connected to your mouse position
- Lines change colours when you move the mouse over them
- Different thicknesses of lines

### Other student's examples:

#### Naail - Mouse changes colour

<iframe id='ifr' width='480' height='515' scrolling='no' style='background: url(http://clsb.processingtogether.com/static/img/jun09/pad/connectingbar.gif) no-repeat center 60px;' src='http://clsb.processingtogether.com/sp/pad/iframe/ro.9mwwbtBM2n2eja/rev.463?autostart=0'></iframe>

#### G-Man - Lines follow mouse

<iframe id='ifr' width='480' height='335' scrolling='no' style='background: url(http://clsb.processingtogether.com/static/img/jun09/pad/connectingbar.gif) no-repeat center 60px;' src='http://clsb.processingtogether.com/sp/pad/iframe/ro.9f6GiaNfwM2FEh/rev.163?autostart=0'></iframe>

#### Eesa - Pseudo Shadows

<iframe id='ifr' width='580' height='515' scrolling='no' style='background: url(http://clsb.processingtogether.com/static/img/jun09/pad/connectingbar.gif) no-repeat center 60px;' src='http://clsb.processingtogether.com/sp/pad/iframe/ro.9nWX-TvIM3r8N6/rev.408?autostart=0'></iframe>

## Loops inside loops

Last week we looked at `for` loops, where a block of code could be repeated as many times as we would like. Now we are going to create a `for` loop, which loops another `for` loop. This can be very useful for drawing grids of things.

    void setup() {
        size(480, 480);
        smooth();
        noStroke();
    }

    void draw() {
        background(0);
        for (int i = 0; i < 10; i++) {
            for (int j = 0; j < 10; j++) {
                fill(255, 140);
                ellipse(j * 40, i * 40, 40, 40); 
            }
        }
    }

### Grids

In the previous example we are using the counters `i` and `j` that go from `0` to `9`, incrementing by `1` per loop (so they go `0, 1, 2, 3, 4, 5, 6, 7, 8, 9`, notice that they don't get to `10` because the **condition** for our loop is `i < 10`. The loop will repeat as long as this statement is true, but `10 < 10` is a false statement so it won't run then.

We then use these counter to calculate the `x` and `y` arguments of `ellipse`: `i * 40` and `j * 40`.

An alternative way to do this is to just use the values we want as our counters e.g.

    for (int x = 0; x < 400; x += 40) {
        for (int y = 0; y < 400; y += 40) {
            fill(255, 140);
            ellipse(x, y, 40, 40); 
        }
    }

Notice here I've changed the counter variable names to x and y, as this makes it more comprehendible.

## Pins and Lines

Here's another example of a grid loop

    void setup() {
        size(480, 480);
        smooth();
    }

    void draw() {
        background(0);
        fill(255, 255, 255, 255);
        stroke(102, 102, 102, 255);

        for (int y = 20; y <= height - 20; y += 10) {
            for (int x = 20; x <= width - 20; x += 10) {
                ellipse(x, y, 4, 4);
                // Draw a line to the center of the display
                line(x, y, height / 2, width / 2);
            }
        }
    }

### Task: Make it your own

Edit the previous sketch to make it your own, you could:
    + Change the colours of the `ellipse`s or `line``
    + Make the lines follow the mouse using `mousex`

### Examples of student's work

#### Danny

<iframe id='ifr' width='720' height='515' scrolling='no' style='background: url(http://clsb.processingtogether.com/static/img/jun09/pad/connectingbar.gif) no-repeat center 60px;' src='http://clsb.processingtogether.com/sp/pad/iframe/ro.9kzT6OT2k2fF2R/rev.464?autostart=0'></iframe>