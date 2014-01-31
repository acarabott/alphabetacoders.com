# Processing - Week 10

## Mapping values

`map` is a really useful function that lets us map one range of values to another, e.g. convert the `mouseX` position (`0 - width`) to a colour range (`0-255`).

`map` takes 5 arguments:

    map(valueToMap, inputMin, inputMax, outputMin, outputMax)

so our `mouseX` colour example would look like
    
    map(mouseX, 0, width, 0, 255)

## Ellipse Buddies

Lets start with a basic mouse following `ellipse` but with the fill colour mapped to our `mouseX`

    void setup() {  // this is run once.   
        size(500, 500);    
    } 
     
    void draw() {
        background(0);
        noStroke();
        fill(map(mouseX, 0, width, 0, 255));
        ellipse(mouseX, mouseY, 20, 20);
    }

Now lets add a second ellipse, with its `x` position mapped to our `mouseY`, it will spread to the left by a maximum of half the `width`

    void draw() {
        background(0);
        noStroke();
        fill(map(mouseX, 0, width, 0, 255));
        
        ellipse(mouseX, mouseY, 20, 20);
        float x2 = map(mouseY, 0, height, mouseX, mouseX - (width / 2));
        ellipse(x2, mouseY, 20, 20);
    }

### Task: Many Buddies

Have your sketch draw an arbitray number of ellipses (use an `int num` variable so that you can quickly alter it on the fly). 

When your mouse is at the top of the screen they should all be on top of each other.
When your mouse is at the bottom of the screen, in the middle, they should all be fanned out from the left to right

![](/worksheets/week10/images/fan.png)

#### Make it your own

Add another use of `map` to your sketch, you could create a gradient of colours across your `ellipse`s, have the number of `ellipse`s depend on the mouse position etc...


#### Student's work

##### G-Man
<iframe id='ifr' width='480' height='515' scrolling='no' style='background: url(http://clsb.processingtogether.com/static/img/jun09/pad/connectingbar.gif) no-repeat center 60px;' src='http://clsb.processingtogether.com/sp/pad/iframe/ro.92hQdCceyGiipB/rev.541?autostart=0'></iframe>

##### Naail
<iframe id='ifr' width='480' height='515' scrolling='no' style='background: url(http://clsb.processingtogether.com/static/img/jun09/pad/connectingbar.gif) no-repeat center 60px;' src='http://clsb.processingtogether.com/sp/pad/iframe/ro.9xS3ac3fIcey3O/rev.498?autostart=0'></iframe>