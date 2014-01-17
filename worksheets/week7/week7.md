# Processing - Week 7

## Robot with variables

We have used variables before, they are "buckets" with names that we can store values in. They are useful for two reasons: 

+ words make more sense than numbers - if you see `bodyHeight` you know what it is likely to mean
+ Repeatability - if you are using the same radius everywhere, just assign a variable `radius` with the value and the variable, then if you want to change all radiuses, just change the value of the `radius` variable

Here's some code that uses variables to draw a robot's head

    int x = 60;
    int y = 420;
    int bodyHeight = 110;
    int neckHeight = 140;
    int radius = 45;
    int ny = y - bodyHeight - neckHeight - radius;
     
    void setup() {  // this is run once.   
        size(170, 480);
        strokeWeight(2);
        background(204);
        ellipseMode(RADIUS);
    } 
     
    void draw() {  // this is run repeatedly.  
        stroke(102);
        fill(0);
        ellipse(x + 12, ny, radius, radius);
        fill(255);
        ellipse(x + 24, ny - 6, 14, 14);
        fill(0);
        ellipse(x + 24, ny - 6, 3, 3);
        fill(153);
        ellipse(x, ny-8, 5, 5);
        ellipse(x + 30, ny - 26, 4, 4);
        ellipse(x + 41, ny + 6, 3, 3);
    }
     

![](images/robot.png)

## Make it your own

Modify this code to make it your own! See if you can make the whole head follow the mouse

### Student's work

#### Conrad

<iframe id='ifr' width='170' height='515' scrolling='no' style='background: url(http://clsb.processingtogether.com/static/img/jun09/pad/connectingbar.gif) no-repeat center 60px;' src='http://clsb.processingtogether.com/sp/pad/iframe/ro.91VzRQjbcdUQv-/rev.911?autostart=0'></iframe>

#### Adam

<iframe id='ifr' width='500' height='435' scrolling='no' style='background: url(http://clsb.processingtogether.com/static/img/jun09/pad/connectingbar.gif) no-repeat center 60px;' src='http://clsb.processingtogether.com/sp/pad/iframe/ro.9WxJbJKli0nGSF/rev.596?autostart=0'></iframe>