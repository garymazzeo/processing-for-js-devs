# Processing Week 4: Transformations and Coordinate Systems

## 1. Understanding Coordinate Transformations
- Working with the global coordinate system
- Translating, rotating, and scaling shapes
- Pushing and popping the transformation state

Example:
```processing
void setup() {
  size(800, 600);
}

void draw() {
  background(255);
  
  // Draw a grid of rotated squares
  for (int x = 0; x < 10; x++) {
    for (int y = 0; y < 10; y++) {
      pushMatrix();
      translate(x * 80 + 40, y * 80 + 40);
      rotate(radians(frameCount + (x + y) * 10));
      rect(-20, -20, 40, 40);
      popMatrix();
    }
  }
}
```

## 2. Nested Transformations
- Transforming within transformed spaces
- Creating hierarchical structures
- Animating complex systems

Example: Solar System
```processing
float sunX, sunY, sunSize = 100;
float earthX, earthY, earthSize = 50, earthOrbitRadius = 200, earthAngle = 0;
float moonX, moonY, moonSize = 20, moonOrbitRadius = 50, moonAngle = 0;

void setup() {
  size(800, 600);
}

void draw() {
  background(0);
  
  // Draw the sun
  fill(255, 255, 0);
  ellipse(width/2, height/2, sunSize, sunSize);
  
  // Draw the earth's orbit
  noFill();
  stroke(200);
  ellipse(width/2, height/2, earthOrbitRadius*2, earthOrbitRadius*2);
  
  // Draw the earth
  pushMatrix();
  translate(width/2, height/2);
  earthAngle += 0.01;
  earthX = cos(earthAngle) * earthOrbitRadius;
  earthY = sin(earthAngle) * earthOrbitRadius;
  translate(earthX, earthY);
  fill(0, 0, 255);
  ellipse(0, 0, earthSize, earthSize);
  
  // Draw the moon
  pushMatrix();
  moonAngle += 0.03;
  moonX = cos(moonAngle) * moonOrbitRadius;
  moonY = sin(moonAngle) * moonOrbitRadius;
  translate(moonX, moonY);
  fill(200);
  ellipse(0, 0, moonSize, moonSize);
  popMatrix();
  
  popMatrix();
}
```

## 3. Fourth Project: Solar System Animation
For your fourth project, you'll create an animated solar system sketch that demonstrates your understanding of coordinate transformations and hierarchical structures. Requirements:
- Implement a sun, earth, and moon
- The earth should orbit the sun, and the moon should orbit the earth
- Allow the user to control the speed of the animation
- Add additional visual elements (e.g. stars, clouds, other planets)

Example starter code:
```processing
// Global variables for positions and sizes
float sunX, sunY, sunSize = 100;
float earthX, earthY, earthSize = 50, earthOrbitRadius = 200, earthAngle = 0;
float moonX, moonY, moonSize = 20, moonOrbitRadius = 50, moonAngle = 0;
float animationSpeed = 1.0;

void setup() {
  size(800, 600);
}

void draw() {
  background(0);
  
  // Draw the sun
  fill(255, 255, 0);
  ellipse(width/2, height/2, sunSize, sunSize);
  
  // Draw the earth's orbit
  noFill();
  stroke(200);
  ellipse(width/2, height/2, earthOrbitRadius*2, earthOrbitRadius*2);
  
  // Draw the earth
  pushMatrix();
  translate(width/2, height/2);
  earthAngle += 0.01 * animationSpeed;
  earthX = cos(earthAngle) * earthOrbitRadius;
  earthY = sin(earthAngle) * earthOrbitRadius;
  translate(earthX, earthY);
  fill(0, 0, 255);
  ellipse(0, 0, earthSize, earthSize);
  
  // Draw the moon
  pushMatrix();
  moonAngle += 0.03 * animationSpeed;
  moonX = cos(moonAngle) * moonOrbitRadius;
  moonY = sin(moonAngle) * moonOrbitRadius;
  translate(moonX, moonY);
  fill(200);
  ellipse(0, 0, moonSize, moonSize);
  popMatrix();
  
  popMatrix();
  
  // Add user controls
  fill(255);
  text("Animation Speed: " + animationSpeed, 20, 20);
  
  if (keyPressed) {
    if (key == '+') {
      animationSpeed += 0.1;
    } else if (key == '-') {
      animationSpeed = max(animationSpeed - 0.1, 0.1);
    }
  }
}
```

## Practice Exercises
1. **Nested Transformations**
   - Create a hierarchical structure of shapes (e.g. a robot with moving parts)
   - Experiment with different translation, rotation, and scaling combinations
   - Animate the shapes to demonstrate the transformations

2. **Camera Controls**
   - Implement a camera system that can pan, zoom, and rotate
   - Allow the user to control the camera using the mouse or keyboard
   - Use the camera to explore a complex 3D scene

3. **Dynamic Composition**
   - Create a sketch that dynamically arranges shapes based on the window size
   - Use transformations to scale, position, and rotate the shapes
   - Respond to window resizing events to maintain the composition

## Next Steps
After completing Week 4, you should have a solid understanding of:
- How to use the `push()` and `pop()` functions to manage the transformation state
- Applying transformations like translation, rotation, and scaling to shapes
- Creating hierarchical structures and nested transformations
- Implementing camera controls and dynamic composition techniques

In the next module, you'll dive into more advanced visual programming concepts like generative art and pixel manipulation.
