# CSS Best Practices

1.  **Follow a consistent naming convention**  
    Use the same naming style across your team to keep your code readable and consistent. Common conventions include:

    - **kebab-case** – Separate words with hyphens (e.g., `nav-bar`)
    - **camelCase** – First word lowercase, next words capitalized (e.g., `navBar`)
    - **PascalCase** – Every word starts with a capital letter (e.g., `NavBar`)
    - **snake_case** – Separate words with underscores (e.g., `nav_bar`)

2.  **Organize your stylesheet into logical sections**  
    Use comments to divide your CSS into sections like:

    - Basic styles
    - Typography
    - Layout
    - Forms

3.  **Avoid over-specific selectors**  
     Keep selectors simple and flexible. For example, avoid:

    ```css
    div.nav > ul.items > li
    ```

    Instead, use:

    ```css
    .nav-item
    ```

4.  **Avoid using `!important`**

    Overusing `!important` can make your CSS hard to maintain and debug. Use it only when absolutely necessary.

5.  **Sort CSS properties logically**

    Sorting properties (e.g., by category or alphabetically) makes the code easier to read and maintain.

6.  **Leverage CSS inheritance**

    Use the natural inheritance of CSS to avoid redundant declarations and keep styles minimal.

7.  **Extract repetitive patterns**

    Use reusable classes and follow _Object-Oriented CSS (OOCSS)_ principles to keep your styles clean and modular.

8.  **Avoid repeating values – Keep it DRY**

    Don’t Repeat Yourself. Reuse values and classes where possible to reduce redundancy.

# Variables

We can use **CSS variables** to store reusable values like colors, fonts, or sizes. They are usually defined in the `:root` selector so they can be accessed anywhere in the CSS.

# Object-Oriented CSS (OOCSS)

Object-Oriented CSS (OOCSS) is a method for writing CSS that focuses on creating **reusable and maintainable components**.

It works like object-oriented programming: define reusable "objects" (like cards, buttons, containers), so you **don’t repeat the same styles** again and again.

### Core Principles of OOCSS

1. **Separate container from content**  
   Layout and structure should not depend on the specific content inside the component. This makes it reusable in different situations. (Instead of using `.hero .btn`, We can just use button, So the `btn content` is not dependent on `hero container`, We can use it again and again)

2. **Separate structure from skin**  
   Keep layout-related styles (like padding, width, positioning) separate from visual styles (like colors, fonts, backgrounds).  
   This makes it easy to update the look without changing the layout.

# BEM (Block Element Modifier)

BEM is use as Block elemt and Modifier

**BEM** is a naming convention for writing clean and reusable CSS class names.

#### Structure

- **Block**: The base component  
  Example: `button`, `form`, `nav`

- **Element**: A part of the block  
  Syntax: `block__element`  
  Example: `button__icon`, `form__label`

- **Modifier**: A variation of the block or element  
  Syntax: `block--modifier` or `block__element--modifier`  
  Example: `button--primary`, `form__label--bold`

#### Syntax:

- Use `double underscores (__)` to connect an element to its block.

- Use `double hyphens (--)` to add a modifier.

#### Example

```html
<div class="card card--featured">
  <h2 class="card__title">Title</h2>
  <p class="card__description">Description here</p>
  <button class="btn"></button>
</div>
```
