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
  ```css
  grid-template-columns: repeat(3, 1fr); /* Creates 3 equal columns */
  ```
- **auto-fit / auto-fill**: Allows for flexible columns that adjust based on the available space.
  ```css
  grid-template-columns: repeat(auto-fit, minmax(100px, 1fr));
  ```

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
