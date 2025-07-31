# Web Systems Project: Personal Portfolio Website

**Live Demo:** [**View the live website here**](https://ryea9.github.io/University-projects/Web-Systems/)
*(Note: The link points to the `index.html` file within this folder)*

---

### Project Overview

This project is a multi-page personal portfolio website developed as the sole project for the Web Systems course. It was built from the ground up and hosted on a Linux server environment. The primary goal was to demonstrate a practical understanding of core web technologies, including HTML for structure, CSS for styling, and essential web server management concepts like file permissions. The website introduces me, details my experiences and future goals, and includes a self-critique page to analyze the design and accessibility choices made during development.

### Development Environment

*   **Operating System:** The website was developed and tested within a **Linux server** environment.
*   **Core Technologies:** HTML5, CSS3
*   **Code Editor:** Visual Studio Code (or your editor of choice)
*   **Version Control:** Git & GitHub

### Page-by-Page Breakdown

The website is structured into four main pages:

1.  **Home Page (`index.html`):** The main landing page that welcomes visitors and provides a brief introduction to my profile and the website's purpose.
2.  **Past Page (`past.html`):** This page details my journey, including my academic background, extracurricular activities, and previous work experience, providing context for my skills.
3.  **Future Page (`future.html`):** Outlines my career aspirations, specifically focusing on my passion for cybersecurity and the motivations driving me to pursue a career in this field.
4.  **Comments Page (`comments.html`):** This page serves as a detailed self-critique and technical commentary. It breaks down my development choices regarding the website's structure, aesthetics, and accessibility. I analyze my own decisions on **color palettes, font selection (Tahoma for readability), spacing, and layout**. This demonstrates a reflective approach to development, which is crucial for improvement.

### Core Technologies & Elements

#### HTML Elements
The structure of the website relies on a variety of semantic and structural HTML5 elements to ensure clarity and accessibility.
*   **Structural Elements:** `<div>`, `<header>`, `<footer>`, `<section>`, `<nav>`
*   **Content Elements:** `<h1>` to `<h4>`, `<p>`, `<a>` for navigation, `<img>` for images, and `<ul>` for lists.
*   **Tables:** A `<table>` was used on the comments page to present the file structure in an organized manner.

#### CSS Styling and Effects
The visual appearance was controlled entirely by an external stylesheet (`websystems.css`).
*   **Layout:** Key layout techniques included using **Flexbox** for aligning content, setting a `max-width` on containers to ensure readability on wide screens, and using properties like `margin` and `padding` for spacing.
*   **Aesthetics:** The `color` and `background-color` properties were used to create a consistent theme. `box-shadow` was applied to add depth to images and other elements.
*   **Interactive Effects:** A **`hover`** effect was added to all navigation links. This provides visual feedback to the user by changing the link's color or background, enhancing interactivity.

### Key Features

#### Responsive Design
The website is designed to be responsive and accessible across different devices. By using `@media` queries in CSS, the layout adjusts to different screen sizes. For example:
```css
@media only screen and (max-width: 600px) {
  /* CSS rules for phones and small devices go here */
}
