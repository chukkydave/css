### **CSS Grid for Advanced Layouts**

#### **Introduction to CSS Grid**
- **CSS Grid** is a powerful layout system in CSS that allows for the creation of complex, flexible, and responsive layouts.
- It uses **rows** and **columns** to define a layout structure.
- A grid container holds the grid items, and it’s defined by setting the display property of an element to `grid` or `inline-grid`.

#### **Grid Terminology**
- **Grid Container**: The parent element where the grid items (children) are placed.
- **Grid Items**: The direct children of the grid container.
- **Grid Lines**: The dividing lines that create the structure of rows and columns.

#### **Basic CSS Grid Properties**
- **display: grid;** - Defines the element as a grid container.
- **grid-template-columns / grid-template-rows**: Define the number of columns or rows and their sizes.
  ```css
  .container {
    display: grid;
    grid-template-columns: 200px 1fr 1fr;
    grid-template-rows: 150px auto;
  }
  ```
- **grid-gap**: Defines the space between grid items. You can also use **row-gap** and **column-gap** separately.

#### **Defining Tracks with Fractional Units (fr)**
- The `fr` unit represents a fraction of the available space in the grid container.
  ```css
  .container {
    display: grid;
    grid-template-columns: 1fr 2fr 1fr;
  }
  ```

#### **Placing Grid Items**
- **grid-column / grid-row**: Specifies where an item should start and end.
  ```css
  .item {
    grid-column: 2 / 4; /* Starts at column 2 and spans to column 4 */
    grid-row: 1 / 3; /* Starts at row 1 and spans to row 3 */
  }
  ```
  
#### **Grid Template Areas**
- You can use **grid-template-areas** to create a visual map of the layout.
  ```css
  .container {
    grid-template-areas:
      "header header"
      "sidebar main"
      "footer footer";
  }
  .header {
    grid-area: header;
  }
  .sidebar {
    grid-area: sidebar;
  }
  ```
  
#### **Advanced Grid Techniques**
- **repeat()**: Defines repeated track listings.
  The `repeat()` function in **CSS Grid Layout** is a powerful and convenient tool that simplifies the definition of grid tracks (columns or rows) that share similar sizes or patterns. Here’s a detailed explanation of how it works and why it is useful.

### **Understanding `repeat()` in CSS Grid**

- The `repeat()` function is used to **define repeating grid tracks**. Instead of writing each column or row size individually, `repeat()` allows you to specify how many times a particular track should repeat and its size, making your code **more concise and readable**.
  
  The syntax of `repeat()` is:
  ```css
  repeat(count, track-size);
  ```
  - **`count`**: The number of times the track should repeat.
  - **`track-size`**: The size of each track. It could be a specific length unit (e.g., `px`, `%`, `em`), a relative unit (`fr`), or even a combination of these.

### **Examples of Using `repeat()`**

#### **1. Simple Repeating Columns**
To create a grid container with **four equal columns**, you would normally write:
```css
.grid-container {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr 1fr; /* Defines four columns each taking 1 fraction of the available space */
}
```

Using `repeat()`, this can be simplified to:
```css
.grid-container {
  display: grid;
  grid-template-columns: repeat(4, 1fr); /* Repeats 1fr column size 4 times */
}
```
- This defines a grid with four equal-width columns, each taking `1fr` (one fraction) of the available space.

#### **2. Combining Repeated Tracks with Other Tracks**
You can use `repeat()` in combination with other values to create more complex grid structures.
```css
.grid-container {
  display: grid;
  grid-template-columns: 100px repeat(2, 1fr) 200px;
}
```
- This defines a grid with **four columns**:
  - The **first column** is `100px`.
  - The **next two columns** are repeated twice with `1fr` each.
  - The **last column** is `200px`.

#### **3. `repeat()` with Auto-Filling Columns**
The `repeat()` function can be combined with **auto-fit** or **auto-fill** to create more dynamic, responsive layouts.

- **`auto-fit`** and **`auto-fill`** allow the grid to **automatically adjust** the number of columns based on the available space.

##### **Auto-Fill Example**
```css
.grid-container {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(100px, 1fr));
}
```
- **`auto-fill`**: Creates as many columns as will fit in the container based on the track size (`minmax(100px, 1fr)`).
- **`minmax(100px, 1fr)`**: Ensures each column has a **minimum size of `100px`** and can grow up to **`1fr`** of the available space.
- **`auto-fill`** continues adding columns even if there is empty space, meaning some columns may be empty if there's not enough content.

##### **Auto-Fit Example**
```css
.grid-container {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(100px, 1fr));
}
```
- **`auto-fit`**: Similar to `auto-fill`, but it **"collapses"** any extra columns, so the grid items stretch to fill the remaining space without leaving any empty columns.

### **Key Differences: `auto-fit` vs `auto-fill`**
- **`auto-fill`**: Fills the grid with as many columns as possible, even if some of them end up empty.
- **`auto-fit`**: Fits the columns to the container, but if there is extra space, the columns stretch to fill it without creating empty tracks.

### **Benefits of Using `repeat()`**
1. **Readability**: Reduces redundancy and makes the code much more readable.
2. **Flexibility**: Makes it easy to adjust the layout with fewer code changes. If you need to add or reduce the number of columns, you only need to change the repeat count.
3. **Dynamic Layouts**: Using `auto-fit` or `auto-fill` allows for a highly flexible layout that adapts to different container sizes, which is especially useful in responsive design.

### **Examples for Practice**

1. **Create a Grid with Six Equal Columns**
   ```css
   .grid-container {
     display: grid;
     grid-template-columns: repeat(6, 1fr);
   }
   ```
   - This creates six columns, each taking up an equal fraction (`1fr`) of the container’s width.

2. **Create a Responsive Card Layout**
   ```css
   .card-container {
     display: grid;
     grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
     gap: 20px;
   }
   ```
   - **`auto-fit`** ensures the cards are **responsive**.
   - Each card has a **minimum width of `200px`** but can grow to fill the space (`1fr`).


### **Responsive Design with Media Queries**

#### **What are Media Queries?**
- **Media Queries** allow you to apply different styles for different devices or screen sizes.
- Syntax:
  ```css
  @media (max-width: 768px) {
    .container {
      grid-template-columns: 1fr; /* Makes it a single-column layout for smaller screens */
    }
  }
  ```

#### **Common Breakpoints**
- **Mobile**: `(max-width: 600px)`
- **Tablet**: `(max-width: 768px)`
- **Desktop**: `(min-width: 769px)`

#### **Media Query Example**
- Switching between a two-column and a single-column layout:
  ```css
  .container {
    display: grid;
    grid-template-columns: 1fr 1fr;
  }

  @media (max-width: 768px) {
    .container {
      grid-template-columns: 1fr; /* Changes to one column for smaller screens */
    }
  }
  ```

### **Mobile-First Design**

#### **Introduction to Mobile-First Design**
- **Mobile-First Design** is a design strategy that starts with designing for smaller screens and then adds complexity for larger screens.
- This approach ensures the website is functional for users on mobile devices before scaling to larger devices.

#### **How to Implement Mobile-First Design**
- Start by writing CSS for small screens first.
- Then, use media queries to add styles as the screen size increases.
  ```css
  .container {
    display: grid;
    grid-template-columns: 1fr; /* Mobile-first, single-column */
  }

  @media (min-width: 600px) {
    .container {
      grid-template-columns: 1fr 1fr; /* Adds a second column for tablets and up */
    }
  }

  @media (min-width: 1024px) {
    .container {
      grid-template-columns: 1fr 1fr 1fr; /* Adds a third column for larger screens */
    }
  }
  ```

### **Examples**

1. **Basic Responsive Grid Layout**:
   - Create a three-column grid layout that adjusts to a one-column layout on smaller screens.
   - Example Code:
     ```html
     <div class="container">
       <div class="item">Item 1</div>
       <div class="item">Item 2</div>
       <div class="item">Item 3</div>
     </div>
     <style>
       .container {
         display: grid;
         grid-template-columns: repeat(3, 1fr);
         gap: 20px;
       }
       @media (max-width: 768px) {
         .container {
           grid-template-columns: 1fr;
         }
       }
     </style>
     ```

2. **Grid Template Area Layout**:
   - Create a page with a header, sidebar, main content, and footer.
   - Example Code:
     ```html
     <div class="container">
       <header class="header">Header</header>
       <aside class="sidebar">Sidebar</aside>
       <main class="main">Main Content</main>
       <footer class="footer">Footer</footer>
     </div>
     <style>
       .container {
         display: grid;
         grid-template-areas:
           "header header"
           "sidebar main"
           "footer footer";
         grid-template-columns: 1fr 3fr;
         grid-gap: 10px;
       }
       .header {
         grid-area: header;
       }
       .sidebar {
         grid-area: sidebar;
       }
       .main {
         grid-area: main;
       }
       .footer {
         grid-area: footer;
       }
       @media (max-width: 600px) {
         .container {
           grid-template-areas:
             "header"
             "main"
             "sidebar"
             "footer";
           grid-template-columns: 1fr;
         }
       }
     </style>
     ```

### **Class Exercises**

1. **Exercise 1: Create a Three-Column Layout**
   - Create a three-column layout that adjusts to a single column on screens smaller than 600px.
   
2. **Exercise 2: Portfolio Page Using CSS Grid**
   - Design a portfolio page with a header, sidebar, main content, and footer.
   - Use **grid-template-areas** for the layout and make it responsive.

3. **Exercise 3: Responsive Pricing Table**
   - Create a pricing table with three plans. Use **CSS Grid** to align the plans horizontally on larger screens and stack them vertically on smaller screens.

### **Take-Home Assignment**

- **Project**: Build a Responsive Webpage Using CSS Grid
  - Requirements:
    - Create a webpage with the following sections: **Header, About, Services, Portfolio, Contact, Footer**.
    - Use **CSS Grid** to create a **two-column** layout for larger screens and a **single-column** layout for smaller screens.
    - The **Header** and **Footer** should span the entire width.
    - The **Portfolio** section should have at least **six items**, arranged in a **three-column** layout on larger screens and a **two-column** layout on tablets, stacking to **one-column** on mobile devices.
    - Include media queries to create a **responsive design** that adapts to different screen sizes.
  - **Deliverable**: Submit the link to your hosted webpage or a zipped file of your HTML, CSS, and any images used.
