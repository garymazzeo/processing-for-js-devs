# Processing Week 3: Color Theory and Implementation

## 1. Understanding Color Modes
- RGB (Red, Green, Blue)
- HSB (Hue, Saturation, Brightness)
- Advantages and use cases for each

Example:
```processing
// RGB mode (default)
background(255, 0, 0);  // Red
fill(0, 255, 0);        // Green
stroke(0, 0, 255);      // Blue

// HSB mode
colorMode(HSB, 360, 100, 100);
background(180, 100, 100);  // Cyan
fill(90, 100, 100);         // Yellow
stroke(270, 100, 100);      // Purple
```

## 2. Color Manipulation
- Adjusting individual RGB/HSB components
- Creating color palettes
- Generating gradients

Example: Gradient
```processing
void draw() {
  for (int x = 0; x < width; x++) {
    float inter = map(x, 0, width, 0, 1);
    color c1 = color(255, 0, 0);
    color c2 = color(0, 0, 255);
    stroke(lerpColor(c1, c2, inter));
    line(x, 0, x, height);
  }
}
```

## 3. Transparency and Blending
- Setting alpha channel for colors
- Blending modes (e.g. normal, multiply, screen)
- Overlaying transparent elements

Example: Transparency
```processing
void setup() {
  size(500, 500);
  colorMode(RGB, 255);
}

void draw() {
  background(255);
  
  // Transparent ellipse
  fill(255, 0, 0, 128);
  ellipse(width/2, height/2, 300, 300);
  
  // Blending modes
  blendMode(MULTIPLY);
  fill(0, 255, 0, 128);
  ellipse(width/2, height/2, 300, 300);
  
  blendMode(SCREEN);
  fill(0, 0, 255, 128);
  ellipse(width/2, height/2, 300, 300);
}
```

## 4. Third Project: Color-Changing Interactive Pattern
For your third project, you'll create an interactive sketch that uses color to create a dynamic, generative pattern. Requirements:
- Generate a repeating pattern of shapes
- Allow the user to interact with the pattern (e.g. mouse hover, click)
- Change the colors of the pattern based on interaction
- Experiment with blending modes and transparency

Example starter code:
```processing
int cellSize = 50;
int cols, rows;

void setup() {
  size(800, 600);
  cols = width / cellSize;
  rows = height / cellSize;
}

void draw() {
  background(255);
  
  for (int x = 0; x < cols; x++) {
    for (int y = 0; y < rows; y++) {
      float hue = map(x, 0, cols, 0, 360);
      float sat = map(y, 0, rows, 0, 100);
      
      pushMatrix();
      translate(x * cellSize, y * cellSize);
      
      // Draw a shape with the calculated color
      fill(hue, sat, 100);
      rect(0, 0, cellSize, cellSize);
      
      popMatrix();
    }
  }
}

void mouseMoved() {
  // Change colors based on mouse position
}

void mousePressed() {
  // Modify the pattern on click
}
```

## Practice Exercises
1. **Color Mixer**
   - Create a sketch that allows the user to adjust RGB or HSB sliders
   - Display the resulting color in a large square
   - Experiment with different UI layouts and control schemes

2. **Animated Gradients**
   - Generate vertical or horizontal gradients
   - Animate the gradients by shifting the color range over time
   - Try combining multiple gradients with different orientations

3. **Transparency Layers**
   - Create a sketch with multiple transparent shapes/objects
   - Experiment with different blending modes
   - Animate the objects to create depth and visual interest

## Next Steps
After completing Week 3, you should have a solid understanding of:
- The differences between RGB and HSB color modes
- Techniques for creating and manipulating colors
- Using transparency and blending modes effectively
- Implementing color-driven generative patterns

In the next module, you'll dive into more advanced visual programming concepts like transformations and coordinate systems.
