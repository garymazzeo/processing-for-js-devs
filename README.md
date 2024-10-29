# Learn Processing: A Course for JavaScript Developers

## Course Overview

This course is designed for JavaScript developers looking to explore creative coding through Processing. You'll learn to create interactive graphics, animations, and visual art while building on your existing programming knowledge.

## Module 1: Getting Started with Processing

### Week 1: Setup and Basics

- Installing Processing IDE vs p5.js
- Understanding the draw loop (setup() and draw())
- Coordinate system differences from browser DOM
- Basic shapes and colors
- JavaScript equivalent comparisons
- Project: Static composition using basic shapes

### Week 2: Animation Fundamentals

- Variables and state management
- Frame rate and timing
- Mouse and keyboard interaction
- Basic motion algorithms
- Project: Interactive bouncing ball animation

## Module 2: Visual Programming Concepts

### Week 3: Color Theory and Implementation

- RGB vs HSB color modes
- Color manipulation and palettes
- Transparency and blending modes
- Creating gradients
- Project: Color-changing interactive pattern

### Week 4: Transformations and Coordinate Systems

- push() and pop() (similar to canvas save/restore)
- translate(), rotate(), scale()
- Understanding the transformation matrix
- Creating compound shapes
- Project: Solar system animation with nested rotations

## Module 3: Advanced Graphics

### Week 5: Generative Art

- Random and noise functions
- Creating organic movement
- Particle systems
- Vector math basics
- Project: Generative nature scene

### Week 6: Images and Pixels

- Loading and displaying images
- Pixel manipulation
- Image filters and effects
- Webcam input
- Project: Interactive webcam filter application

## Module 4: Object-Oriented Programming in Processing

### Week 7: Classes and Objects

- Processing class structure vs JavaScript classes
- Creating reusable visual components
- Object interaction and collision detection
- Project: Interactive particle system

### Week 8: Arrays and Collections

- ArrayList vs JavaScript arrays
- Managing multiple objects
- Complex animations with object collections
- Project: Flocking simulation (Boids)

## Module 5: Advanced Topics

### Week 9: Data and Visualization

- Loading external data (CSV, JSON)
- Creating data visualizations
- Interactive charts and graphs
- Project: Interactive data visualization

### Week 10: 3D Graphics Basics

- 3D coordinate system
- Basic 3D shapes
- Lighting and materials
- Camera controls
- Project: Interactive 3D scene

## Final Project (2 weeks)

Create a substantial interactive artwork or visualization that combines multiple concepts from the course. Example project ideas:

- Interactive music visualizer
- Generative art system with user controls
- Data visualization with animation
- Interactive game with particle effects
- 3D interactive environment

## Learning Resources

### Essential References

- Processing.org official documentation
- Nature of Code by Daniel Shiffman
- Learning Processing by Daniel Shiffman

### Online Communities

- Processing Forum
- OpenProcessing
- Reddit r/processing

### Practice Tips

1. Start each concept with small sketches
2. Modify existing examples
3. Document your code thoroughly
4. Share work with the community
5. Participate in creative coding challenges

## JavaScript to Processing Quick Reference

```processing
// JavaScript Canvas          | Processing
ctx.fillStyle = 'red';       | fill(255, 0, 0);
ctx.strokeStyle = 'blue';    | stroke(0, 0, 255);
ctx.beginPath();             | // Not needed
ctx.rect(x, y, w, h);       | rect(x, y, w, h);
requestAnimationFrame(draw); | // Automatic in draw()
canvas.width;               | width
canvas.height;              | height
```

## Weekly Study Pattern

1. Read concept documentation (2-3 hours)
2. Complete coding exercises (3-4 hours)
3. Experiment with variations (2-3 hours)
4. Work on weekly project (4-5 hours)
5. Review and refactor code (1-2 hours)

Remember to:

- Save all your sketches, even simple experiments
- Comment your code with JavaScript comparisons
- Join the Processing community
- Share your progress
- Focus on understanding visual concepts
