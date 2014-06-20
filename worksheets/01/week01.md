# Processing - Week 1


## 1 - Drawing an Ellipse

In the editor, type the following:

    ellipse(50, 50, 80, 80);

### Tasks:

* Alter the values and watch it change, what does each parameter do?

## 2 - Make Circles

Delete the text from the last example, and try this one:

    void setup() {
        size(480, 120);
        smooth();
    }

    void draw() {
        if (mousePressed) {
            fill(0);
        } else {
            fill(255);
        }
        ellipse(mouseX, mouseY, 80, 80);
    }

### Tasks:

* Make the canvas bigger
* Have it draw two circles, side by side
* What about 4 circles?

## 3 - Setting the window size

The `size()` function sets the size of our canvas, the parameters, or arguments are in pixels

    size(480, 480);

## 4 - More Shapes

After you `size(480, 480);` function try some of these other functions

### Point

Arguments: *(x, y)*

    point(240, 240);

### Line

Arguments: *(x1, y1, x2, y2)*

The x and y position of the two ends of the line

    line(20, 50, 400, 400);

![line](/worksheets/01/images/line.png)

### Triangle

Arguments: *(x1, y1, x2, y2, x3, y3)*

The x and y positions of each of the triangle's points

    triangle(240, 0, 0, 240, 240, 240);

![triangle](/worksheets/01/images/triangle.png)

### Quad

Arguments: *(x1, y1, x2, y2, x3, y3, x4, y4)*

The x and y positions of each corner of the quad

    quad(20, 20, 460, 20, 460, 460, 20, 360);

![quad](/worksheets/01/images/quad.png)

### Rect

Arguments: *(x, y, width, height)*

    rect(20, 20, 440, 440);

![rect](/worksheets/01/images/rect.png)

### Ellipse

Arguments: *(x, y, width, height)*

    ellipse(240, 240, 100, 100);

![ellipse](/worksheets/01/images/ellipse.png)

### Arc

Arguments: *(x, y, width, height, start, stop)*

    arc(240, 240, 100, 100, HALF_PI, PI + HALF_PI);

*Start and Stop* are the degrees in *Radians* (angle measurements based on pi (3.14159) rather than degrees). Processing comes with some constant values (words that are all uppercase) to make life easier.

If you think of it like a clock:

- 0 = 3 o'clock
- HALF_PI = 6 o'clock
- PI = 9 o'clock
- PI + HALF_PI = 12 o'clock
- TWO_PI = 3 o'clock (again)

These constants are just numbers, so you can do PI * 2, or HALF_PI / 2

![Radians](/worksheets/01/images/radians.png)

## Play time

Combine some shape functions, along with the `mouseX` and `mouseY` values to make something strange, or a monster, or an abstract piece of art.

#### Credits

Examples based on *Getting Started with Processing* by Casey Reas and Ben Fry