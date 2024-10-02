

### **Topic 1: Transitions and Animations in CSS**

#### **Introduction to Transitions**
- CSS **transitions** allow you to change property values smoothly over a specified duration.
- Properties you can animate include `color`, `background-color`, `height`, `width`, `transform`, etc.

**Syntax:**
```css
element {
  transition: property duration timing-function delay;
}
```
- **Property**: The property to animate (e.g., `width`, `opacity`).
- **Duration**: How long the transition takes (e.g., `1s`, `500ms`).
- **Timing-function**: Controls the speed of the transition (`ease`, `linear`, `ease-in`, `ease-out`).
- **Delay**: The delay before starting the transition (optional).

**Example:**
```html
<div class="box"></div>
```
```css
.box {
  width: 100px;
  height: 100px;
  background-color: blue;
  transition: width 1s ease-in-out, background-color 0.5s;
}

.box:hover {
  width: 200px;
  background-color: green;
}
```
When you hover over the `.box`, it smoothly changes its width and color.

#### **Introduction to Animations**
- CSS **animations** let you create complex animations using keyframes.
- **Keyframes** specify the style at different points in the animation timeline.

**Syntax:**
```css
@keyframes animation-name {
  0% { /* starting state */ }
  100% { /* ending state */ }
}

element {
  animation: animation-name duration timing-function delay iteration-count direction;
}
```
- **@keyframes**: Defines the stages of the animation.
- **Animation properties**:
  - **Animation-name**: Specifies the name of the animation.
  - **Duration**: Time for each iteration.
  - **Timing-function**: Controls the speed of the transition (`ease`, `linear`, `ease-in`, `ease-out`).
  - **Delay**: The delay before starting the transition (optional).
  - **Iteration-count**: Number of times the animation runs (e.g., `infinite`).
  - **Direction**: specifies the direction of the animation (e.g., `normal`, `reverse`).

**Example:**
```html
<div class="circle"></div>
```
```css
.circle {
  width: 100px;
  height: 100px;
  border-radius: 50%;
  background-color: red;
  animation: move 2s ease-in-out infinite alternate;
}

@keyframes move {
  0% {
    transform: translateX(0);
  }
  100% {
    transform: translateX(300px);
  }
}
```
This example creates a red circle that moves horizontally from its initial position to 300 pixels to the right and then back, repeating infinitely.

#### **Classwork Exercise:**
1. Create a box that changes size and background color when hovered over.
2. Create a bouncing ball using `@keyframes` animation, making it move up and down repeatedly.

---

### **Topic 2: Introduction to CSS Preprocessors (Sass or LESS)**

#### **What is a CSS Preprocessor?**
- **CSS preprocessors** extend CSS with additional features like variables, nesting, functions, and more.
- Popular preprocessors include **Sass** and **LESS**.
- They help keep your CSS code cleaner, more maintainable, and reusable.

#### **Sass Basics**
- Sass files have the extension `.scss`.
- Features include:
  - **Variables**: Store values for reuse.
  - **Nesting**: Organize CSS in a more readable way.
  - **Partials and Import**: Split CSS into smaller files.

**Example: Variables and Nesting (Sass)**
```scss
$primary-color: #3498db;

.container {
  background-color: $primary-color;
  padding: 20px;

  .text {
    color: white;
    font-size: 16px;
  }
}
```
In the example above, `$primary-color` is used to set the container's background. Nesting helps logically organize related styles.

#### **LESS Basics**
- LESS files have the extension `.less`.
- LESS is similar to Sass and allows variables and nesting.

**Example: Variables and Nesting (LESS)**
```less
@primary-color: #e74c3c;

.box {
  background-color: @primary-color;
  padding: 10px;

  .inner {
    color: #fff;
    text-align: center;
  }
}
```

#### **Classwork Exercise:**
1. Write a nested CSS style for a card using either **Sass** or **LESS**.
2. Create a simple stylesheet with variables for different colors and apply them to different elements.

---

### **Class Assignment**
1. **Transitions & Animations**: Create a simple webpage with at least three elements using CSS transitions and animations. For instance, make a button that changes color on hover and a box that moves continuously.
2. **Sass/LESS Preprocessing**: Convert an existing CSS file into a **Sass** or **LESS** file by using variables and nesting.

---

