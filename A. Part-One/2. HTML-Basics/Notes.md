# Head Section (`<head></head>`)

The `<head>` section of an HTML document contains metadata — information about the webpage. This information is not displayed on the page itself but is used by **browsers** and **search engines** to understand the page better.

Common things included in the <head>:

- Title of the page
- Character set
- Viewport settings
- Links to stylesheets or scripts
- SEO meta tags

#### Charset (`<meta charset="UTF-8">`)

The charset defines the character encoding used in your HTML document. It tells the browser how to interpret text characters.

- UTF-8 is the most common and supports almost all characters from all languages.

#### Viewport (`<meta name="viewport" content="width=device-width, initial-scale=1.0">`)

The viewport meta tag helps make your website look good on all devices, especially mobile phones and tablets.

It controls:

- The initial **width** of the page (usually set to the device's width)
- The **zoom level** when the page first loads

#### Meta Keywords

You can add **SEO keywords** to help search engines understand what your webpage is about.

#### Meta Description

You can add a **short description** of your webpage. This is often shown in search engine results.

# Text

```Html
<p>

<em>

<i>

<strong>

<b>

<h1> to <h6>
```

The `<em>`, `<i>`, `<strong>`, and `<b>` tags are meant to give meaning to the text, not just change how it looks. For example, `<em>` and `<i>` are used to emphasize or highlight important words, while `<strong>` and `<b>` are used to show importance. These tags should not be used just for visual styling. If you want to make text bold or italic for design purposes, it's better to use CSS.

The heading tags `<h1>` to `<h6>` are used to define the structure of a web page. `<h1>` is the main heading, and `<h2>` to `<h6>` are used for subheadings. These tags help organize content and improve accessibility and SEO. You should not use heading tags just to make text look bigger or bolder. Also, each page should have only one `<h1>` tag, which represents the main topic of the page.

# Entities

Some characters are reserved in HTML, which means they have a special meaning (like <, >, &). To display these characters as normal text on a web page, you need to use special codes called HTML entities.

For example:

- `<` becomes `&lt;`
- `>` becomes `&gt;`
- `&` becomes `&amp;`
- copyright symbol - `&copy`;
- non breaking space - `&nbsp`

These notations let you safely show the characters without confusing the browser.

# Hyperlinks

- `<a href="">` - for href, we can use relative or absolute path . ( Absolute URLs start from the root folder using `/`. Relative URLs start from the current folder using `.` or `..` )

- The `hre`f attribute in an `<a>` tag is not just for linking to web pages. You can also use it to link to images, PDF files, external websites, different sections on the same page, or even a "**Back to Top**" link.

- You can use the `download` attribute to let users **download** the linked file when they click it, instead of opening it.

- By using the `target` attribute, you can control **where** the link opens. For example, `target="_blank"` opens the link in a **new tab**.

- A **link** is just a web address (URL). A **hyperlink** is a clickable element (like text or an image) that takes the user to another page or resource when clicked.

# Image

- Always use the `alt` attribute for images. The alt text provides a description that appears if the image fails to load. It also helps people using screen readers to understand what the image is about, improving accessibility. Additionally, search engines use the alt text to better understand the content of your page, which can help with SEO.

# Audio and Video

The `<video>` tag in HTML supports several main attributes:

- controls – shows play, pause, and volume buttons

- autoplay – makes the video play automatically when the page loads

- loop – makes the video play again and again in a loop

Inside the `<video>` tag, you can also add _fallback text_. This message will be shown if the browser doesn't support the video.

# Lists

There are three types of lists in HTML:

1. Ordered List (`<ol>`) – A numbered list
2. Unordered List (`<ul>`) – A bulleted list
3. Description List (`<dl>`) – A list of terms and descriptions

# Tables

In HTML tables, the main tags are:

- `<thead>` – defines the table header section

- `<tbody>` – defines the main content/body of the table

- `<tfoot>` – defines the footer section of the table

- `<tr>` – stands for table row

- `<th>` – stands for table header cell (bold and centered by default)

- `<td>` – stands for table data cell (regular data)

# Containers

`<div>` and `<span>` are common container elements in HTML.

- `<div>` is a block-level element. It takes up the full width available and starts on a new line. It's often used to group larger sections of content.

- `<span>` is an inline element. It stays within the line and is used to group small parts of text or elements inside a paragraph.

# Semantic Elements

Apart from container elements like `<div>` and `<span>`, HTML also has **semantic elements** — these give meaning to the content.

- `<article>` – Represents an **independent, self-contained** piece of content. It can be used for things like blog posts, comments, reviews, news articles, or product cards.

- `<figure>` – A container for media content like images, diagrams, or charts. It can optionally include a **caption** using the `<figcaption>` tag.

- `<mark>` – Used to **highlight text**, usually with a yellow background, to draw attention.

- `<time>` – Represents **dates or times**. It can be used to mark events, schedules, or timestamps in a machine-readable format.

# Structuring a Web Page.

A typical web page is mainly structured using **three main semantic elements** -`<header>`, `<main>`, and `<footer>`.

In addition to these, we can use the `<aside>` element to create a **sidebar**, which usually contains related links, ads, or extra information.

- The `<header>` is used for the **top section** of a page or a section. It usually contains the logo, navigation links, or page title.

- The `<main>` contains the **main content** of the page. There should only be one `<main>` **element** per page.

- The `<footer>` is used at the **bottom of the page** or section and often includes contact info, copyright, or links.

- The `<aside>` is for **side content** related to the main content, like tips, side notes, or extra links.

- The `<section>` element is used to **group related content**. Each section should have a heading (`<h1>` to `<h6>`). If a section doesn’t have a heading, it may cause a validation warning in HTML checkers.
