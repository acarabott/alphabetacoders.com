# Processing - Week 1

## Example 2-1

In the editor, type the following:

    ellipse(50, 50, 80, 80);
    
### Tasks:

* Alter the values and watch it change, what does each parameter do?

## Example 2-2

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

## Example 3-1


### Credits

Examples based on *Getting Started with Processing* by Casey Reas and Ben Fry