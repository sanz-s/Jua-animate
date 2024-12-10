
# Jua Animate Documentation

## Overview

**Jua Animate** is a custom JavaScript animation library designed to provide flexible animation utilities. 
It includes easing functions, color handling, transformations, and advanced timeline controls. This document explains the structure and purpose of the library.

---

## Key Features

- **Easing Functions**: Predefined and customizable easing functions for smooth animations.
- **Transformations**: Handles complex CSS transformations with robust support for matrices.
- **Color Manipulation**: Supports multiple color formats (HEX, RGB, HSL) and conversions.
- **Timeline Management**: Provides tools to control animation sequences with delays, loops, and keyframes.

---

## Functions Overview

### Global Setup

1. **`penner`**:  
   A collection of predefined easing functions (e.g., `easeInSine`, `easeOutBounce`).  
   - *Purpose*: Used to control the rate of change for animations.

2. **`steps(step)`**:  
   Generates stepwise progress for animations.  
   - **Arguments**:  
     - `step`: Number of steps in the animation (default: 5).  
   - **Returns**: Function mapping time to steps.

3. **`bezier(mX1, mY1, mX2, mY2)`**:  
   Generates a cubic bezier easing function.  
   - *Purpose*: Allows custom easing curves for animations.

### Color Utilities

1. **`colorTypesToRgba`**:  
   A mapping of color formats (`HEX`, `RGB`, `HSL`) to their equivalent RGBA representation.
   - Supports conversion of color strings to RGBA format for use in animations.

2. **`parseColor(val)`**:  
   Parses a color input into a standard format.  
   - **Arguments**:  
     - `val`: Input color in various formats.  

### Transformation Utilities

1. **`convertToMatrix3d(matrix)`**:  
   Converts a 2D matrix to a 3D transformation matrix.  

2. **`parsetransform(val)`**:  
   Parses a CSS `transform` string into individual transformation components.

3. **`Jua.transform`**:  
   Constructs a transform object for managing 3D transformations.

### Animation Core

1. **`initAnimation(targets, css, duration, easing)`**:  
   The primary function to initialize animations.  
   - **Arguments**:  
     - `targets`: Target elements for animation.
     - `css`: CSS properties to animate.
     - `duration`: Total duration of the animation.
     - `easing`: Easing function.

2. **`Animater(animations, params, css, loop)`**:  
   The core engine that processes animation frames, easing, and timelines.

---

## How to Use

1. **Basic Animation**:  
   ```javascript
   Jua.animate({
       targets: '#element',
       translateX: 100,
       duration: 1000,
       easing: 'easeOutElastic'
   });
   ```

2. **Custom Easing**:  
   Use `bezier` or predefined easing types (`easeInOutQuad`, `easeOutBounce`).

3. **Chaining Animations**:  
   Utilize `loop` and `stagger` for sequential animations.

---

## Notes

- Ensure the global `Jua` object is available before initializing animations.
- The library includes optimizations for document visibility to pause and resume animations.

