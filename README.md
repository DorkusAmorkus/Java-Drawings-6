# Java-Drawings-6

/* 
Your name: Elias Han

Date: 9/28/18

Project/assignment name: Java Sketch

Description: A sketch

Credits for code referenced: 
https://processing.org/tutorials/color/ 
https://processing.org/tutorials/pshape/
https://processing.org/reference/quad_.html
https://processing.org/tutorials/drawing/


uses:
pshape
color
quadrilateral
triangle
mouse input
draw

note: for proper quad. coordinates, I had to find the slope and create entirely new linear equations from 1 or 2 points just to get the cursor angle to look right. took 2 hours

*/

PShape arrow, tip, shaft;

void setup() {
  size(500, 500);

  // Create the shape group
  arrow = createShape(GROUP);

  // Make two shapes
  shapeMode(CORNER);
  tip = createShape(TRIANGLE, mouseX, mouseY, mouseX+5, mouseY+50, mouseX+40, mouseY+30);
 
  tip.setFill(color(0));
  tip.setStroke(color(255));
  tip.setStrokeWeight(2);
   shaft = createShape(QUAD,mouseX+20.372,mouseY+41.216, 24.628, 38.784, 41.503, 68.784, 37.247, 71.216);
  shaft.setFill(color(0));
  shaft.setStroke(color(255));
  shaft.setStrokeWeight(2);
  // Add the two "child" shapes to the parent group
  arrow.addChild(shaft);
  arrow.addChild(tip);
}

void draw() {
background(150);
  translate(mouseX, mouseY);
  shape(arrow); 
  if (mousePressed == true) {
    tip.setFill(color(0,0,255)); // White
    shaft.setFill(color(0,0,255)); // White
  } else {
    tip.setFill(color(255,0,0)); // Black
    shaft.setFill(color(255,0,0)); // Black
 
}
  
}

