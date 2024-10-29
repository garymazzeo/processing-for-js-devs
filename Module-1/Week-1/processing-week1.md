# Processing Week 1: Setup and Basics

## 1. Setting Up Your Environment

### Processing IDE vs p5.js

As a JavaScript developer, you have two main paths for learning Processing:

1. **Native Processing (Java-based)**

   - Download from processing.org
   - Standalone IDE
   - Compiles to native applications
   - Better performance for complex visualizations
   - Access to Java libraries

2. **p5.js (JavaScript-based)**
   - Web-based alternative to Processing
   - Uses familiar JavaScript syntax
   - Easier web integration
   - Extensive browser API access
   - Slightly slower performance for complex operations

For this course, we recommend starting with native Processing to learn the core concepts, as p5.js will be an easy transition later.

## 2. Understanding the Draw Loop

Unlike browser JavaScript where you might use `requestAnimationFrame()` or event loops, Processing uses two main functions that form the backbone of every sketch:

```processing
void setup() {
  // Runs once at the start
  size(800, 600);  // Set canvas size
  background(255); // White background
}

void draw() {
  // Runs continuously in a loop
  // Your animation code goes here
}
```

JavaScript equivalent:

```javascript
function setup() {
  const canvas = document.createElement("canvas")
  canvas.width = 800
  canvas.height = 600
  document.body.appendChild(canvas)
  const ctx = canvas.getContext("2d")
  ctx.fillStyle = "white"
  ctx.fillRect(0, 0, canvas.width, canvas.height)
}

function draw() {
  requestAnimationFrame(draw)
  // Animation code
}
```

## 3. Coordinate System

Processing uses a coordinate system similar to canvas, but with some key differences:

- (0,0) is at the top-left corner
- Positive Y goes down
- Positive X goes right
- Units are in pixels
- No DOM positioning to worry about
- Drawing happens immediately (no need for separate fill/stroke commands)

## 4. Basic Shapes and Colors

### Shapes

```processing
// Rectangle
rect(x, y, width, height);

// Ellipse (circles and ovals)
ellipse(centerX, centerY, width, height);

// Line
line(x1, y1, x2, y2);

// Triangle
triangle(x1, y1, x2, y2, x3, y3);

// Custom shape
beginShape();
vertex(x1, y1);
vertex(x2, y2);
vertex(x3, y3);
endShape(CLOSE);  // CLOSE connects last point to first
```

### Colors

```processing
// Fill and stroke colors
fill(red, green, blue);        // RGB values 0-255
fill(brightness);              // Grayscale 0-255
stroke(red, green, blue);      // RGB for outlines
noFill();                      // Transparent fill
noStroke();                    // No outline

// Color with alpha (transparency)
fill(red, green, blue, alpha); // alpha 0-255
```

## 5. Drawing Order and Layering

- Processing draws elements in order (like painting)
- Later shapes draw on top of earlier shapes
- No z-index or DOM hierarchy to manage
- Use `push()` and `pop()` to save and restore styles

## 6. Basic Animation Concepts

Simple movement example:

```processing
float x = 0;  // Position variable

void setup() {
  size(800, 600);
}

void draw() {
  background(255);  // Clear each frame
  ellipse(x, height/2, 50, 50);  // Draw circle
  x = x + 1;  // Move right
  if (x > width) {  // Reset when off screen
    x = 0;
  }
}
```

## 7. First Project: Static Composition

Your first project will be to create a static composition using basic shapes. Requirements:

- Use at least 3 different types of shapes
- Implement both fill and stroke
- Use at least 4 different colors
- Create a composition that fills the canvas
- Add comments explaining each major element

Example starter code:

```processing
void setup() {
  size(800, 600);
  background(240);  // Light gray background

  // Large background circle
  fill(200, 100, 100);  // Dusty rose
  noStroke();
  ellipse(400, 300, 400, 400);

  // Overlapping rectangles
  fill(100, 100, 200, 180);  // Semi-transparent blue
  stroke(50);
  rect(200, 200, 200, 200);

  // Add more shapes...
}

void draw() {
  // Empty since this is a static composition
}
```

## Practice Exercises

1. **Shape Explorer**

   - Create each basic shape type
   - Experiment with different fill/stroke combinations
   - Try varying sizes and positions

2. **Color Grid**

   - Create a grid of squares
   - Each square should have a different color
   - Experiment with RGB vs grayscale

3. **Concentric Shapes**
   - Draw shapes inside other shapes
   - Experiment with transparency
   - Try different color combinations

## Common Gotchas for JavaScript Developers

1. **Type Declarations**

   - Processing requires type declarations (float, int, etc.)
   - Variables must be declared with their type

2. **Function Declarations**

   - Must include return type (void if none)
   - Parameters must include types

3. **Drawing State**

   - Fill/stroke settings persist until changed
   - No need to set them for each shape unless changing

4. **Loop Structure**
   - No need to manually request animation frames
   - `draw()` runs automatically
   - Use `noLoop()` for static sketches

## Additional Resources for Week 1

- Processing Reference: Basic Shapes
- Processing Reference: Color
- Example sketches in Processing IDE
- Community showcases on OpenProcessing
- Interactive examples on processing.org

## Next Steps

After completing this week:

1. You should understand the basic Processing development environment
2. Be able to create simple static compositions
3. Understand the coordinate system
4. Know how to use basic shapes and colors
5. Be familiar with the setup/draw structure

The next week will build on these fundamentals to create simple animations and interactive elements.
