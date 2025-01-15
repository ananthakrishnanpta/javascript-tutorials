# **JavaScript Animations Tutorial**
---
  ### Go back to [JavaScript Tutorial](README.md)
---
### **1. Project Setup**

Let’s start by structuring our project with the following files:

```
animation-project/
├── index.html
├── styles.css
└── script.js
```

---

### **2. HTML Structure (index.html)**

We’ll create a simple webpage with some basic elements that we can animate. In this case, we will animate a box element and a button for triggering animations.

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>JavaScript Animations</title>
  <!-- Link to External CSS -->
  <link rel="stylesheet" href="styles.css">
</head>
<body>
  <div class="container">
    <h2>JavaScript Animation Tutorial</h2>

    <!-- Animated Box -->
    <div id="animated-box" class="box"></div>

    <!-- Button to Trigger Animation -->
    <button id="animate-btn" class="btn">Animate Box</button>
  </div>

  <script src="script.js"></script>
</body>
</html>
```

### **Explanation:**
- The `#animated-box` is a simple **div** that we will animate.
- The **button** (`#animate-btn`) will trigger the animation when clicked.
- **Linking external files**: We’ve linked **styles.css** for styling and **script.js** for adding the JavaScript logic to handle the animations.

---

### **3. CSS Styling (styles.css)**

We’ll use **CSS** to style our box and button, as well as set up the initial state of our animated elements.

```css
/* Global Styles */
body {
  font-family: Arial, sans-serif;
  background-color: #f0f0f0;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  margin: 0;
}

/* Container Style */
.container {
  text-align: center;
}

/* Box Style */
.box {
  width: 100px;
  height: 100px;
  background-color: #3498db;
  margin: 20px auto;
  transition: all 0.5s ease;
}

/* Button Style */
.btn {
  padding: 10px 20px;
  background-color: #2ecc71;
  color: white;
  border: none;
  font-size: 16px;
  cursor: pointer;
}

.btn:hover {
  background-color: #27ae60;
}
```

### **Explanation:**
- The `.box` class sets the size, background color, and a **transition** property for smooth animations.
- The `.btn` class is used to style the button and give it hover effects.

---

### **4. JavaScript-based Animations (script.js)**

Now, let’s add some JavaScript logic to control the animation and trigger it using the button.

```javascript
// Select the elements
const box = document.getElementById('animated-box');
const btn = document.getElementById('animate-btn');

// Function to animate the box
function animateBox() {
  // Apply CSS animation by changing the properties
  box.style.transform = 'translateX(300px)';  // Move box to the right
  box.style.backgroundColor = '#e74c3c';  // Change color to red

  // After animation ends, reset the box
  setTimeout(() => {
    box.style.transform = 'translateX(0px)';  // Move box back to original position
    box.style.backgroundColor = '#3498db';  // Change color back to blue
  }, 1000); // Reset after 1 second (1000ms)
}

// Add event listener to the button
btn.addEventListener('click', animateBox);
```

### **Explanation:**
- We select the **box** and **button** elements using `getElementById`.
- **`animateBox()`** is a function that animates the box using the **transform** property (to move the box) and **background-color** (to change color).
- The box moves to the right by 300px when the button is clicked. After 1 second, the box resets to its original position.
- The **`setTimeout()`** function is used to delay the reset of the animation by 1 second.

---

### **5. CSS Transitions**

You can use **CSS transitions** to animate properties like position, color, and size. Let’s modify the previous code to use CSS transitions to animate the box when hovering.

```css
/* Box Style with CSS Transition */
.box {
  width: 100px;
  height: 100px;
  background-color: #3498db;
  margin: 20px auto;
  transition: all 0.5s ease;
}

.box:hover {
  transform: scale(1.5) translateY(-50px);  /* Grow the box and move it up */
  background-color: #e74c3c;  /* Change color on hover */
}
```

### **Explanation:**
- **CSS Transition**: The `transition: all 0.5s ease;` applies smooth transitions to all properties when they change.
- On hover (`.box:hover`), the box will **scale** and **move up** while its background color changes to red.

---

### **6. CSS Keyframe Animations**

CSS keyframes allow you to define more complex animations with multiple steps.

```css
/* Box with Keyframe Animation */
@keyframes moveAndColorChange {
  0% {
    transform: translateX(0);
    background-color: #3498db;
  }
  50% {
    transform: translateX(150px);
    background-color: #f39c12;
  }
  100% {
    transform: translateX(0);
    background-color: #3498db;
  }
}

/* Apply the keyframe animation to the box */
.box {
  width: 100px;
  height: 100px;
  background-color: #3498db;
  margin: 20px auto;
  animation: moveAndColorChange 3s ease-in-out infinite;
}
```

### **Explanation:**
- **Keyframe Animation**: The `@keyframes` rule defines the **steps** in the animation. In this case, we are moving the box and changing its color.
- The box will **move 150px** to the right and change color to **yellow** at 50% of the animation, and return to the initial position and color at 100%.

---

### **7. Triggering Animations with JavaScript**

In the previous examples, animations were triggered automatically. You can also trigger animations on events such as button clicks or user interactions.

```javascript
// Function to trigger the keyframe animation when the button is clicked
btn.addEventListener('click', function() {
  box.style.animation = 'moveAndColorChange 3s ease-in-out infinite';
});
```

### **Explanation:**
- When the user clicks the button, the **JavaScript** will trigger the keyframe animation (`moveAndColorChange`) for the box.

---

### **8. Conclusion**

In this tutorial, you learned how to create animations using **JavaScript** and **CSS**. Here’s a summary of the techniques covered:

- **CSS Transitions**: Smooth transitions triggered by property changes, such as scaling and moving elements.
- **CSS Keyframe Animations**: Defining complex animations with multiple steps, like moving an element and changing colors.
- **JavaScript Animations**: Manipulating elements with JavaScript, changing properties like **transform** and **background-color** dynamically.

### **More things to explore:**


- More complex animations (e.g., rotating elements, fading in/out).
- Integrating animation libraries like **GSAP** or **Anime.js** for even more powerful animation features.
- Animating multiple elements with delays and durations.

---
