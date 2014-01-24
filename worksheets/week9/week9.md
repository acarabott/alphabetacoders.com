# Processing - Week 9

## Easing

When easing is applied to a moving object it means that rather than moving directly to a location, it *eases* into that position, it lags behind the instruction, creating a more fluid motion.

Here's an example

    float x;
    float easing = 0.01;

    void setup() {
        size(480, 480);
        smooth();  
    }

    void draw() {
        float targetX = mouseX;
        x += (targetX - x) * easing;
        ellipse(x, 40, 12, 12);
        println(targetX + " : " + x);
    }

Notice how the circle doesn't follow the mouse exactly, and slows down as it gets closer to it. Also notice that it never actually reaches the targetX, but gets so close that it doesn't really matter.

### Understanding easing

To understand this, lets write out the results of a few animation frames, using simple numbers.

Let's take these starting values
    
    x = 0;
    targetX = 10;

The line that determines our x position is
    
    x += (targetX - x) * easing;

So let's translate that

#### Animation Frame 1
    x = 0 + ((10 - 0) * 0.01);
    x = 0 + (10 * 0.01)
    x = 0 + 0.1
    x = 0.1

#### Animation Frame 2
    // x is now 0.1
    // targetX still 10

    x = 0.1 + ((10 - 0.1) * 0.01);
    x = 0.1 + (9.9 * 0.01)
    x = 0.1 + 0.099
    x = 0.199

#### Animation Frame 3
    x = 0.199 + ((10 - 0.199) * 0.01);
    x = 0.199 + (9.801 * 0.01)
    x = 0.199 + 0.09801
    x = 0.29701

As you can see, the x value is getting closer to the target of 10, but at a slower and slower rate. The first frame it moves by 0.1, the second by 0.99, the third by 0.09801.

### Adjust the Easing

Change the `easing` variable to see how this affects the movement of the circle. At what value will it make no difference?

## Smooth Lines

Let's apply easing to our previous line drawing sketch

    float x;
    float y;
    float px;
    float py;
    float easing = 0.05;

    void setup() {
        size(480, 480);
        smooth();
        stroke(0, 102);
    }

    void draw() {
        float targetX = mouseX;
        x += (targetX - x) * easing;
        float targetY = mouseY;
        y += (targetY - y) * easing;
        float weight = dist(x, y, px, py);
        strokeWeight(weight);
        line(x, y, px, py);
        py = y;
        px = x;
    }

### Make it your own

Ideas:

+ Multiple lines
+ Varying colours
+ Easing based on target position