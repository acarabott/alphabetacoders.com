# Processing - Week 5

## Custom Shapes - Vertex

As well as using predefined shape functions such as `elipse` and `rect`, we can draw shapes using a series of points with `beginShape`, `vertex` and `endShape`.

	void setup() {
		size(480, 480);
	}

	void draw() {
		beginShape();
		vertex(180, 82);
		vertex(207, 36);
		vertex(214, 63);
		vertex(407, 11);
		vertex(412, 30);
		vertex(219, 83);
		vertex(226, 109);
		endShape();
	}

Notice that the first and last points are not connected, to do this we change `endShape();` to `endShape(CLOSE);`

### Your own shape

Pick a simple shape and try to draw it using `vertex`, things with straight lines will be the easiest.

Ideas
	* A robot head, in profile
	* Tetris blocks
	* Witches Hat

### Creature Example

	void setup() {
		size(480, 120);
	}

	void draw() {
		// Left creature
		fill(255);
		beginShape();
		vertex(50, 120);
		vertex(100, 90);
		vertex(110, 60);
		vertex(80, 20);
		vertex(210, 60);
		vertex(160, 80);
		vertex(200, 90);
		vertex(140, 100);
		vertex(130, 120);
		endShape();
		fill(0);
		ellipse(155, 60, 8, 8);

		// Right creature
		fill(255);
		beginShape();
		vertex(370, 120);
		vertex(360, 90);
		vertex(290, 80);
		vertex(340, 70);
		vertex(280, 50);
		vertex(420, 10);
		vertex(390, 50);
		vertex(410, 90);
		vertex(460, 120);
		endShape();
		fill(0);
		ellipse(345, 50, 10, 10);
	}

## Robot

Here's an example of a more involved drawing

![Robot](/worksheets/05/images/robot.png)

	void setup() {  // this is run once.
	    size(720, 480);
	    smooth();
	    strokeWeight(2);
	    ellipseMode(RADIUS);
	}

	void draw() {  // this is run repeatedly.

	    // Neck
	    stroke(102);                    // Set stroke to gray
	    line(266, 257, 266, 162);        // Left
	    line(276, 257, 276, 162);       // Middle
	    line(286, 257, 286, 162);       // Right

	    // Antennae
	    line(276, 155, 246, 112);
	    line(276, 155, 306, 56);
	    line(276, 155, 342, 170);

	    // Body
	    noStroke();
	    fill(102);
	    ellipse(264, 377, 33, 33);
	    fill(0);
	    rect(219, 257, 90, 120);
	    fill(102);
	    rect(219, 274, 90, 6);

	    // Head
	    fill(0);
	    ellipse(276, 155, 45, 45);
	    fill(255);
	    ellipse(288, 150, 14, 14);
	    fill(0);
	    ellipse(288, 150, 3, 3);
	    fill(153);
	    ellipse(263, 148, 5, 5);
	    ellipse(296, 130, 4, 4);
	    ellipse(305, 162, 3, 3);
	}

### Make it your own

Now alter this sketch to make it your own.

Ideas:
* Make the robot move left and right with the mouse
* Make the robot's colours change over time
* Make the robot grow and shrink according to the mouse position