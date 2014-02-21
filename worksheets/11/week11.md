# Processing - Week 11

## Detecting the mouse over a circle

To check whether our mouse is within a circle we can use the `dist` function to check whether the distance of the mouse from the center of the circle is less than the radius.

    int x = 120;
    int y = 60;
    int radius = 12;
     
    void setup() {  
        size(480, 480);
        smooth();
        ellipseMode(RADIUS);
    } 
     
    void draw() {
        background(204);
        float d = dist(mouseX, mouseY, x, y);
        
        if (d < radius) {
            radius++;
            fill(0);
        } else {
            fill(255);
        }
        
        ellipse(x, y, radius, radius);
    }

In this example the ellipse will turn black and grow when the mouse is within its bounds.

## Detecting the mouse over a rectangle

To check if the mouse is within the bounds of a rectangle we need to make **four** checks, one for each side:
- Is the mouse to the right of the left edge?
- Is the mouse to the left of the right edge?
- Is the mouse below the top edge?
- Is this mouse above the bottom edge?

    int x = 80;
    int y = 30;
    int w = 80;
    int h = 60;
     
    void setup() { 
        size(469, 469);
    } 
     
    void draw() {
        background(204);
        
        if ((mouseX > x) && (mouseX < x + w) &&
            (mouseY > y) && (mouseY < y + h)) {
            fill(0);
        } else {
            fill(255);
        }
        
        rect(x, y, w, h);
    }
     
