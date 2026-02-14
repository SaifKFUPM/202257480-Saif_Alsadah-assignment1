# AI Usage Report

## Overview

This document outlines how AI tools were used during the development of my personal portfolio website for SWE 363 Assignment 1.

---

## Tools Used & Use Cases

### Claude (Anthropic)

**Primary AI assistant used throughout the project.**

| Use Case | How It Helped |
|----------|---------------|
| HTML Structure Planning | Asked for suggestions on semantic HTML structure before writing code. Received guidance on proper document outline, section organization, and accessibility best practices. |
| CSS Reference | Requested a cheat sheet of useful CSS properties for portfolios, including selectors, Flexbox, Grid, and responsive design patterns. |
| Code Review | Submitted my initial HTML for review. Claude identified structural issues (nav inside head, missing body tag, improper nesting) that I then fixed. |
| CSS File Creation | After understanding the concepts, I had Claude generate a CSS file based on my requirements, which I then reviewed and customized. |
| JavaScript Implementation | Discussed options for interactive features, chose dark/light theme toggle, and had Claude explain the implementation using localStorage. |
| Documentation | Used Claude to help structure the README and documentation files. |

---

## Benefits & Challenges

### Benefits

1. **Faster Learning Curve** — Instead of searching through multiple tutorials, I could ask specific questions and get targeted explanations with examples relevant to my project.

2. **Code Quality** — AI helped identify issues in my HTML structure that I might have missed, like having `<nav>` inside `<head>` instead of `<body>`.

3. **Best Practices** — Learned about CSS variables for theming, mobile-first responsive design, and semantic HTML structure through practical application.

4. **Comprehensive Reference** — The CSS cheat sheet provided covered exactly what I needed without information overload.

5. **Debugging Assistance** — When something didn't work as expected, I could describe the issue and get potential solutions.

### Challenges

1. **Over-reliance Risk** — Had to consciously stop and understand the code rather than just copying it. Made sure I could explain every line.

2. **Context Limitations** — Sometimes needed to provide more context about my specific requirements to get relevant suggestions.

3. **Verification Required** — AI suggestions needed to be tested and verified. Not everything worked perfectly on the first try.

4. **Customization Needed** — Generated code was a starting point. I had to modify colors, spacing, and content to match my vision.

---

## Learning Outcomes

### Technical Skills Gained

1. **Semantic HTML**
   - Learned the difference between `<section>`, `<article>`, and `<div>`
   - Understood proper document structure (`<head>` vs `<body>` content)
   - Importance of accessibility attributes (`aria-label`, `for` attributes on labels)

2. **CSS Architecture**
   - CSS custom properties (variables) for maintainable theming
   - Mobile-first responsive design with `@media` queries
   - Flexbox for 1D layouts (navigation, header)
   - CSS Grid for 2D layouts (project cards, skills grid)
   - CSS transitions for smooth interactions

3. **JavaScript Fundamentals**
   - DOM manipulation (`getElementById`, `setAttribute`)
   - Event listeners (`addEventListener`)
   - localStorage for persisting user preferences
   - System preference detection (`matchMedia`)

4. **Development Workflow**
   - Using Live Server for real-time preview
   - Organizing code into logical files and folders
   - Writing documentation alongside code

### Conceptual Understanding

- **Progressive Enhancement** — Start with working HTML, enhance with CSS, add interactivity with JS
- **Separation of Concerns** — Keep structure (HTML), presentation (CSS), and behavior (JS) separate
- **User Experience** — Respecting user preferences (dark mode), ensuring accessibility

---

## Responsible Use & Modifications

### How I Ensured Academic Integrity

1. **Understanding Before Accepting**
   - For every code suggestion, I asked "why" before "how"
   - Requested explanations of CSS properties I wasn't familiar with
   - Made sure I could reproduce similar code independently

2. **Active Participation**
   - I planned the overall structure and content myself
   - Made design decisions (color scheme, layout choices)
   - Wrote all personal content (about me, project descriptions)

3. **Code Review & Modification**
   - Reviewed all AI-generated code line by line
   - Modified variable names, values, and organization to my preference
   - Added comments to clarify complex sections

### Specific Modifications Made

| Original AI Suggestion | My Modification |
|------------------------|-----------------|
| Generic color scheme | Changed to blue primary color (`#4b73ca`) matching my preference |
| Generic project cards | Customized with my GitHub repositories and descriptions |
| Basic documentation | Added specific details about my learning process |

### Transparency

- All conversations with AI were for learning purposes
- I can explain every line of code in my project
- This report honestly documents my AI usage

---

