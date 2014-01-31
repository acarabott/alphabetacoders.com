# Processing - Week 8 

## Circle follows mouse

This small example will draw a circle wherever your mouse is

    void setup() {
        size(480, 480);
        fill(0, 102);
        smooth();
        noStroke();
    }

    void draw() {
        background(204);
        ellipse(mouseX, mouseY, 9, 9);
    }

If we move the `background(204);` to `setup` we will get a circle everywhere our mouse has *been*, because we are not redrawing the background each animation frame.

void setup() {
    size(480, 480);
    fill(0, 102);
    smooth();
    noStroke();
    background(204);
}

void draw() {
    ellipse(mouseX, mouseY, 9, 9);
}

## Drawing continously

We can draw continuously by drawing lines from where our mouse is now, to where it was in the previous frame, we can know where our mouse was in the previous frame by using the `pmouseX` and `pmouseY` variables.

    void setup() {
        size(480, 480);
        smooth();
        strokeWeight(4);
        stroke(0, 102);
    }

    void draw() {
        line(mouseX, mouseY, pmouseX, pmouseY);
    }

## Velocity

Because we know where the mouse is, and where it was, we can calculate its velocity and use that value. Now as we are dealing with co-ordinates and not single position values, we should use the `dist` function, which takes two sets of coordinates and calculates the distance.

    void setup() {
      size(480, 480);
      smooth();
      stroke(0, 102);
    }

    void draw() {
      float velocity = dist(mouseX, mouseY, pmouseX, pmouseY);
      strokeWeight(velocity);
      line(mouseX, mouseY, pmouseX, pmouseY);
    }

Here ths `strokeWeight` or line thickness changes according to the speed of the mouse.

### Make it your own

Take this example and have the velocity alter a different aspect of the sketch, maybe the colours?

#### Examples

##### Clemens
Line colour changes to different shades of purple/pink

<iframe id='ifr' width='600' height='635' scrolling='no' style='background: url(http://clsb.processingtogether.com/static/img/jun09/pad/connectingbar.gif) no-repeat center 60px;' src='http://clsb.processingtogether.com/sp/pad/iframe/ro.9JG$Yf8bM7SLgY/rev.588?autostart=0'></iframe>

##### Gaoutaman

Random colour for each line

<iframe id='ifr' width='500' height='535' scrolling='no' style='background: url(http://clsb.processingtogether.com/static/img/jun09/pad/connectingbar.gif) no-repeat center 60px;' src='http://clsb.processingtogether.com/sp/pad/iframe/ro.9WxA3an$WWA7cF/rev.235?autostart=0'></iframe>

##### Danny

Trippy triangles

<iframe id='ifr' width='480' height='515' scrolling='no' style='background: url(http://clsb.processingtogether.com/static/img/jun09/pad/connectingbar.gif) no-repeat center 60px;' src='http://clsb.processingtogether.com/sp/pad/iframe/ro.9f6apxCYIht-Sh/rev.240?autostart=0'></iframe>

##### Sensei

Background colour changes with velocity, fades back to normal

<iframe id='ifr' width='450' height='485' scrolling='no' style='background: url(http://clsb.processingtogether.com/static/img/jun09/pad/connectingbar.gif) no-repeat center 60px;' src='http://clsb.processingtogether.com/sp/pad/iframe/ro.9aqfa4C0YDC0Nz/rev.228?autostart=0'></iframe>