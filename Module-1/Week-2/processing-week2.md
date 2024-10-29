# Processing Week 2: Animation Fundamentals

## 1. Working with Variables
- Declaring and initializing variables
- Using variables to store state
- Updating variables over time

## 2. Understanding Frame Rates
- What is frame rate and why is it important?
- Using `frameRate()` to set the desired frame rate
- Calculating time-based motion

JavaScript equivalent:
```javascript
let x = 0;
let y = 0;
let speed = 2;

function setup() {
  createCanvas(800, 600);
  frameRate(30); // 30 FPS
}

function draw() {
  background(255);
  
  // Update position based on time
  x += speed * (deltaTime / 1000); 
  y += speed * (deltaTime / 1000);
  
  // Draw the ball
  circle(x, y, 50);
  
  // Reset when off screen
  if (x > width || x < 0 || y > height || y < 0) {
    x = 0;
    y = 0;
  }
}
```

## 3. Mouse and Keyboard Interaction
- Detecting mouse position with `mouseX`, `mouseY`
- Responding to mouse clicks with `mousePressed()`
- Listening for keyboard input with `keyPressed()`

Example:
```processing
void setup() {
  size(800, 600);
}

void draw() {
  background(255);
  
  // Draw a ball at the mouse position
  fill(0);
  ellipse(mouseX, mouseY, 50, 50);
  
  // Display the mouse coordinates
  fill(0);
  text("Mouse X: " + mouseX + ", Mouse Y: " + mouseY, 20, 20);
}

void mousePressed() {
  println("Mouse was pressed at " + mouseX + ", " + mouseY);
}

void keyPressed() {
  if (key == 'a') {
    println("The 'a' key was pressed!");
  }
}
```

## 4. Basic Motion Algorithms
- Velocity and acceleration
- Linear motion
- Bounce and wrap-around
- Simple steering behaviors

Example: Bouncing Ball
```processing
float x = 400;
float y = 300;
float vx = 3;
float vy = 2;

void setup() {
  size(800, 600);
}

void draw() {
  background(255);
  
  // Move the ball
  x += vx;
  y += vy;
  
  // Bounce off walls
  if (x < 0 || x > width) {
    vx *= -1;
  }
  if (y < 0 || y > height) {
    vy *= -1;
  }
  
  // Draw the ball
  fill(0);
  ellipse(x, y, 50, 50);
}
```

## 5. Second Project: Interactive Bouncing Ball
For your second project, you'll create an interactive bouncing ball animation. Requirements:
- Ball should move and bounce off the walls
- Ball's movement should be affected by mouse position
- Ball's color should change based on position
- Add some additional visual effects (e.g. trails, glow)

Example starter code:
```processing
float x = 400;
float y = 300;
float vx = 3;
float vy = 2;
float ballSize = 50;

void setup() {
  size(800, 600);
}

void draw() {
  background(255);
  
  // Move the ball
  x += vx;
  y += vy;
  
  // Bounce off walls
  if (x < ballSize/2 || x > width - ballSize/2) {
    vx *= -1;
  }
  if (y < ballSize/2 || y > height - ballSize/2) {
    vy *= -1;
  }
  
  // Set ball color based on position
  float hue = map(x, 0, width, 0, 360);
  fill(hue, 100, 100);
  
  // Draw the ball
  noStroke();
  ellipse(x, y, ballSize, ballSize);
  
  // Add glow effect
  fill(hue, 100, 100, 50);
  ellipse(x, y, ballSize * 1.5, ballSize * 1.5);
}
```

## Practice Exercises
1. **Gravity Simulator**
   - Create a ball that falls under the influence of gravity
   - Experiment with different gravity values
   - Add ground and walls that the ball bounces off

2. **Mouse Magnet**
   - Create a ball that is attracted to the mouse cursor
   - Adjust the attraction force based on distance
   - Try multiple balls that are attracted to the mouse

3. **Fireworks**
   - Create an array of balls that shoot up from the bottom of the screen
   - Add parabolic motion and random horizontal forces
   - Experiment with different effects like trails or explosions

## Next Steps
After completing Week 2, you should have a solid understanding of:
- Working with variables to store and update state
- Controlling frame rate and timing for animations
- Responding to mouse and keyboard input
- Implementing basic motion algorithms like bouncing and steering

In the next module, you'll dive deeper into visual programming concepts like color theory and transformations.
