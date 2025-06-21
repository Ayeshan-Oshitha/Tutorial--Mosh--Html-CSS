# The Box Model

Concept of Box Model - whenever browser renders an element, It puts that element inside an invisible box.

<img src="../Images/image-1.png" width="800">

```html
<div>
  <p>Lorem ipsum dolor sit amet consectetur adipisicing elit.</p>
  <p>Lorem ipsum dolor sit amet consectetur adipisicing elit.</p>
</div>
```

If we apply `padding: 20px;` to each `<p>` element, the space between the two paragraphs becomes **40px** — because each paragraph adds 20px padding to its top and bottom, and they don't overlap. Padding adds space **inside** the element, between its content and its border.

However, if we apply `margin: 20px;` instead, the space between the two paragraphs remains **20px**, not 40px. This is due to a CSS behavior called **margin collapsing**. When **vertical margins** of two adjacent block elements meet, only the larger margin is used—they don't add up.

#### Summary:

- Use **padding** to add space between the content and the border of an element.

- Use **margin** to create space **between elements.**

- When **vertical margins** of two elements touch, **margin collapsing occurs**, and only the larger margin is applied. In contrast, **horizontal margins** (left and right) **do not collapse**. When two horizontal margins touch, they are **added together**.

# Sizing Elements

```css
.box {
  width: 100px;
  height: 100px;
}
```

<img src="../Images/image-2.png" width="800">

```css
.box {
  width: 100px;
  height: 100px;
  padding: 20px;
  margin: 10px;
}
```

<img src="../Images/image-3.png" width="800">

If we add **padding** or **border** to an element using the default box model, the **actual size of the element (the visible box)** will increase.

By default, the `width` and `height` properties apply **only to the content area**. So, when we add padding or border, it **increases the total size** of the visible element. However, the `margin` property does **not** increase the size of the visible box — it only adds space **outside** the element, separating it from other elements. This is the behavior of **`box-sizing: content-box`**;

If we use **`box-sizing: border-box`** then the width and height include content + padding + border.

So:

- If there’s no padding or border, the entire width and height will be used for the content.

- If there is padding or border, they will be included within the specified width and height — which means the content area will shrink accordingly to make room for them.

```css
.box {
  width: 100px;
  height: 100px;
  padding: 20px;
  margin: 10px;
  box-sizing: border-box;
}
```

<img src="../Images/image-4.png" width="800">

#### Summary:

- content-box: width/height = content only → padding & border added outside

- border-box: width/height = content + padding + border → total size stays fixed

---

To apply **`box-sizing: border-box`** to the entire HTML page, use the universal selector like this:

```css
*,
*::before,
*::after {
  box-sizing: border-box;
}
```

To check whether `box-sizing: border-box` is applied to an element, inspect the element in your browser’s developer tools, then go to the **Computed tab** and use the **filter section** to find the `box-sizing` property and see if it is set to `border-box`.

---

The `width` and `height` properties only apply to **block-level elements**. Block-level elements start on a new line and take up the full available horizontal space within their parent container. For example, `<div>` elements are block-level by default because they have `display: block`.

**Inline elements**, on the other hand, do not respond to `width` and `height` because they are set to `display: inline` by default.

If you want to apply `width` and `height` to inline elements, you need to change their display to `inline-block`. This allows the element to behave like a block element in terms of size(respond to width and height ) but still flow inline without starting a new line.

# Overflow

Another important concept is **overflow**, which occurs when dealing with fixed-size elements. If a container has a fixed width or height and contains **more content than it can hold**, the content may overflow outside the container.

To control this behavior, we use the `overflow` property. It has the following common values:

- `visible` – This is the default value. The overflowed content is **not clipped** and will spill outside the container.

- `hidden` – The overflowed content is **cut off** and not visible.

- `scroll` – Scrollbars are **always shown**, even if they’re not needed.

- `auto` – Scrollbars are **shown only when necessary** (if content overflows).

We can also control overflow horizontally and vertically using: `overflow-x` for horizontal overflow and `overflow-y` for vertical overflow. Use these properties as needed to manage overflow behavior in specific directions.

# Measurenment Units

There are quite a few of measurments that fall in to two cateogary. Absolute units are always fixed, the value doesn't change. Relative units are relative to something else.

<img src="../Images/image-5.png" width="800">

There are another absolute units such as pt, in, cm and mm, But these are not commonly used in web design.

**Note**: By default, the **width** of block-level elements **is 100%** — they take up all the available horizontal space of their **parent element**. Also, by default, the **height** of a block-level element is **determined by its content**. If there is no content, the height is essentially **0**.

Ex -: In a `<div>`, if we set `height: 100% ` **without any content** or **without a defined height on the parent**, the height will still be **0**. So, to make an element take the full height of the web page, we can use **height: 100vh**.

10em = **10** x **font size of the current element** , If the current element does **not have a defined font size**, it will **inherit** the font size from its **nearest parent element** that has one defined.

The `em` unit in CSS can be confusing because its value depends on the font size of the current element or its parent. This means that if you change the font size within a container, all `em`-based sizes inside it will also change. This behavior can make it difficult to maintain consistent spacing and sizing across your layout.

To avoid this issue, CSS provides the `rem` unit, which stands for "root em." Unlike `em`, `rem` is always relative to the font size of the root element (`<html>`), making it more predictable and easier to manage. By default, the root font size is typically 16px, so `1rem` equals 16px.

For easier calculation, many developers override the default root font size and set it to 10px. This can be done like this:

```css
html {
  font-size: 62.5%; /* 62.5% of 16px = 10px */
}
```

With this setup, _1rem_ equals _10px_, _2rem_ equals _20px_, and so on. This makes converting between rem and pixels straightforward and improves the readability and scalability of your CSS.

You don’t have to use just one unit in CSS. You can mix and match units like `px`, `vh`, and `rem` depending on what you need. For example, use `px` for exact sizes, `rem` to scale with the root font size, and `vh` to size elements based on the viewport height—all in the same project.

```css
.box {
  width: 15rem;
  height: 100vh;
  background-color: gold;
  border-top: 3px solid red;
}
```

# Positioning

By default, the position of HTML elements is set to **`static`**, which means they follow the normal document flow and appear exactly where they naturally belong on the page.

To change how elements stack on top of each other, we use the `z-index` property. A higher `z-index` value means the element will appear **on top** of elements with a lower `z-index`. You can think of `z-index` as a line extending from the screen to your eyes—the higher the value, the closer the element appears to you. By default, `z-index` is `0`.

When we use **`position: relative`**, it allows us to **move an element relative to its original position** without affecting the position of other elements on the page.

With **`absolute positioning`**, we can position an element **relative to its container**. When we absolutely position an element, that element is **removed from the normal flow of the page**. So, all the other elements are rendered **as if the absolutely positioned element doesn't exist**.

( ChatGPT said - With `position: absolute`, an element is positioned relative to **its closest positioned ancestor** (an ancestor with `position` set to `relative`). If no such ancestor exists, it will be positioned relative to the `<html>` element (the page itself).)

If we want to position an element **relative to the viewport** (so it stays in the same place even when the page is scrolled), we can use **`position: fixed`**.

Note - (Chatgpt) - **`position: sticky`** lets an element stay at the top (or side) of the screen **while scrolling**, but **only inside its parent**. It **starts in its normal position** (like `static`), then when you scroll and it reaches a set point (like `top: 0`), it sticks in place. Once the parent container scrolls out of view, the sticky element also **scrolls away (disappears)** with it.

<img src="../Images/image-6.png" width="800">

---

Extra :

There are two main ways to size an element in CSS:

- Using `width` and `height`

- Using position offsets like `top`, `left`, `right`, and `bottom`

```css
position: fixed;
height: 100px;
width: auto;
left: 2rem;
right: 2rem;
```

In this case, the **width** of the box is automatically calculated based on the space between the left and right (2rem on each side), since both `left` and `right` are set.
