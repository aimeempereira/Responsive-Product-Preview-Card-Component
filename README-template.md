# Frontend Mentor - Product preview card component solution

This is a solution to the [Product preview card component challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/product-preview-card-component-GO7UmttRfa). Frontend Mentor challenges help you improve your coding skills by building realistic projects.

## Table of contents

- [Overview](#overview)
  - [The challenge](#the-challenge)
  - [Screenshot](#screenshot)
  - [Links](#links)
- [My process](#my-process)
  - [Built with](#built-with)
  - [What I learned](#what-i-learned)
  - [Continued development](#continued-development)
  - [Useful resources](#useful-resources)
- [Author](#author)

## Overview

### The challenge

Users should be able to:

- View the optimal layout depending on their device's screen size
- See hover and focus states for interactive elements

### Screenshot

- Desktop[1440p width](https://www.linkpicture.com/q/Screenshot-2023-04-17-at-23-14-29-Frontend-Mentor-Product-preview-card-component.png)
- Mobile[375p width](https://www.linkpicture.com/q/Screenshot-2023-04-17-at-23-14-00-Frontend-Mentor-Product-preview-card-component.png)

### Links

- Solution URL: [Add solution URL here](https://your-solution-url.com)
- Live Site URL: [Add live site URL here](https://your-live-site-url.com)

## My process

### Built with

- Semantic HTML5 markup
- CSS custom properties
- Flexbox
- CSS Grid
- Mobile-first workflow
- [Kevin Powell's tutorial on YouTube](https://youtu.be/B2WL6KkqhLQ)
- [John Comeau's CSS reset](https://www.joshwcomeau.com/css/custom-css-reset/) - Resets CSS and removes any pre-styled elements, such as margin and box-sizing.

### What I learned

I had already started this challenge and got stuck because grid was not behaving how I expected. So, I redid the whole thing through a tutorial to understand better how it's done.
In the process, I got to better understand CSS Grid and was presented to concepts I didn't think of before or just didn't know, like these:

```html
<picture class="product-image">
          <source
            srcset="images/image-product-desktop.jpg"
            media="(min-width:600px)"
          />
          <img
            src="images/image-product-mobile.jpg"
            alt="Gabrielle Essence Eau De Parfum"
          />
        </picture>
```

Here, it's possible to use the alternative image for desktop and embed it inside the HTML code, which makes it better for accessibility.
Not only does it use the image tag, so it can give a description of the image for screen reader users(instead of just using the image as a background), but it also uses the SOURCE tag with the SRCSET, which makes the image change for the one on desktop when it's bigger than 600px.

```css
:root {
  --color-primary-400: hsl(158, 36%,37%);
  --color-primary-500: hsl(158, 36%,20%);
  --color-secondary-200:hsl(30, 38%,92%);

  --color-neutral-900:hsl(212,21%,14%);
  --color-neutral-400:hsl(228,12%,48%);
  --color-neutral-100:white;

  --ff-accent: 'Fraunces', serif;
  --ff-base: 'Montserrat', sans-serif;

  --fw-regular: 500;
  --fw-bold:700;
}
```

I really liked this naming system for root elements. Primary colors, secondaries and neutrals; 100-900 for color lightness (100 being the lightest); ff for font-family; fw for font-weight, accent and base for font types.
The whole gist of it is to declare eveything that you might need later on already in the root and just use the variables to make your life easier.

```css
.product {
--content-padding:1.5rem;
--content-spacing:1rem;

display: grid;
background-color: white;
border-radius: .5rem;
overflow: hidden;
max-width: 600px;
}
```

Here, the variables are declared within a container and facilitates changing the padding and spacing for multiple elements inside the container.
Also, "overflow:hidden;" makes sure the image inside the container follows the border-radius declaration. Before this, I was using "border-radius:10px 0 0 10px;" to make sure the style was being applied to the image.

```css
.visually-hidden:not(:focus):not(:active) {
  clip:rect(0 0 0 0);
  clip-path: inset(50%);
  height: 1px;
  overflow: hidden;
  position: absolute;
  white-space: nowrap;
  width: 1px;
}
```

This one is kind of a big deal for me in terms of accessibility. This class is applied to the prices (the original and current prices of the product) and name them in a span tag. This way, people who use screen readers have a more semantic experience when it comes to understanding the information flow of the page.

```html
<p class="product-price">
              <span class="visually-hidden">Current price:</span> $149.99
            </p>
            <p class="product-original-price">
              <span class="visually-hidden">Original price:</span>
              <s>$169.99</s>
            </p>
```

### Continued development

I'd like to make better use of semantic HTML, root declarations and accessibility pratices.

### Useful resources

- [Taking on a Frontend Mentor challenge | Responsive Product Preview Card Component](https://youtu.be/B2WL6KkqhLQ) - Very thorough and professional explanation on how to do this challenge.
- [Reset CSS](https://www.joshwcomeau.com/css/custom-css-reset/)
- [Hidden elements for accessibility](https://www.scottohara.me/blog/2017/04/14/inclusively-hidden.html)
- [Simplify CSS with :is()](https://www.youtube.com/watch?v=McC4QkCvbaY) - The is:() is a pseudo-class that includes more than one element for declarations without having to repeat yourself and still keep the specificity.

## Author

- Website - [Add your name here](https://www.your-site.com)
- Frontend Mentor - [@yourusername](https://www.frontendmentor.io/profile/yourusername)
- Twitter - [@yourusername](https://www.twitter.com/yourusername)
