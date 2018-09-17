# p5 Basics Workshop

## Sequence

1. [Shapes & colors](#shapes-&-colors)
2. [Animating with Built-in Properties](#animating-with-built-in-properties)
3. [Drawing](#drawing)

## Shapes & Colors

Students can access a Glitch workspace with a lot of the setup done ahead of time at [upperlinecode.com/p5](https://www.upperlinecode.com/p5).

Students can also use git to clone the [basic template](https://github.com/upperlinecode/p5-basic-template) if they're using a full development environment like Cloud9. 

#### Stroke, noFill, and Ellipse

Slowly build out the following

```javascript
function draw() {
  background(220)
  stroke(0,0,0)
  noFill()
  ellipse(50, 50, 25, 25)
}
```

#### Playtime 1

What do each of the numerical arguments of the word "ellipse" do? Try swapping each one with the value 200 and see if you can deduce what each one does.


#### Fill, noStroke
* What will happen if we try fill and noStroke instead?

```javascript
function draw() {
  background(220)
  fill(0,0,0)
  noStroke()
  ellipse(50, 50, 25, 25)
}
```

#### Quick Color Theory

Functions like fill and stroke take three numerical arguments that represent amount of red, green, and blue. This is called RGB, and these colors are always in that order. 255 is maximum, 0 is minimum.

Have students try this:

```javascript
function draw() {
  background(220)
  stroke(255,0,0)
  noFill()
  ellipse(50, 50, 25, 25)
}
```

#### Playtime 2

* Make the circle green.
* Make the circle blue.
* Make the circle white.
* Make the circle yellow with a teal filling.
* Test out two other colors.

#### Documentation

This is great, but you'll want more than just ellipses.

Look these 2D-primitives up in the [documentation](https://p5js.org/reference/) and try to implement at least ONE on your page:
* rect()
* triangle()
* arc()
* line()
* point()
* quad()


#### Playtime 3

Challenge students to do any/all of the following:
* Build out the olympic rings
* Build out a lego person

#### Takeaways

* p5 - Render p5 primitives on screen
* p5 - Manipulate stroke and fill color and stroke weight (including noFill() and noStroke() methods)

## Animating with Built-in Properties

#### mouseX and mouseY

If the general format for an ellipse is ellipse(x, y, width, height) then what happens here?

```javascript
function draw() {
  background(220)
  stroke(255,0,0)
  noFill()
  ellipse(mouseX, mouseY, 25, 25)
}
```

How could we use these built-in variables in some really cool ways?

#### Conditionals

What about this one?

```javascript
function draw() {
  background(220)
  let myGreen = color(0, 255, 0)
  let myRed = color(255, 0, 0)
  if (mouseIsPressed) {
    stroke(myGreen)
  } else {
    stroke(myRed)
  }
  noFill()
  ellipse(mouseX, mouseY, 25, 25)
}
```

#### Events v. Booleans

Boolean values (true/false values) like we used above run continuously, and we can use them right in the draw function. You can also write events as completely separate functions. Here's an example:

```javascript
// Declare the variable outside the function so that BOTH functions can access the variable.
var value = 0;

// The draw function runs continuously
function draw() {
  fill(value);
  rect(25, 25, 50, 50);
}

// The mousePressed function only runs when you press the mouse
function mousePressed() {
  value += 25; // increase by 25
  value = value % 255; // If it's over 255, reset it to the remainder
}
```

#### Playtime

Challenge students to do any/all of the following:
* Add a new variable called radius that starts at 25. Then have the radius double to 50 when the mouse is pressed, and go back down to 25 when the mouse is released.
* Have the circle radius continuously increase by 1 when the button is pressed.
* Have the circle include a fill if the mouse is pressed while the mouse is also at the bottom of the canvas.
* Add a function that changes the color more randomly. Call that function any time the mouse is pressed.

#### Takeaways

* p5 - Access built-in variables like mouseX, mouseY, width, and height
* p5 - Create and manipulate custom variables
* p5 - Refactor primitives to respond to dynamic (built-in or custom) variables
* p5 - Write event functions to respond to events like mouseMoved() and mouseClicked()
* GENERAL - Read documentation to understand implementation of specific events & system variables

## Drawing

Cut out the background(220) line of code. have students rerun the program. Ask them to explain what the background was doing. This moment is magical, as it **illuminates what has been happening the whole time**: p5 hasn't been animating, it's been drawing, and then repainting everything instantaneously over and over on a loop.


# Mini-labs & Labs

* Recreate the Olympic Rings:
![Olympic Rings](https://static01.nyt.com/images/2012/07/15/magazine/15wmt/15wmt-jumbo.jpg)
* Recreate famous Logos:
![Logos](logos.png)
* Animate an object with the [DVD Logo Code-along](https://github.com/upperlinecode/dvd-codealong)
* [Tron Bike Lab](https://github.com/upperlinecode/tron-bike-lab.git)
* Utilize p5.js environment variables with the [built-in variables code-along](https://github.com/upperlinecode/p5-built-in-variables-mini-lab)
