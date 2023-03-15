# Frontend Mentor - card\_\_stats preview card component solution

This is a solution to the [card\_\_stats preview card component challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/card__stats-preview-card-component-8JqbgoU62). Frontend Mentor challenges help you improve your coding skills by building realistic projects.

## Table of contents

- [Overview](#overview)
  - [The challenge](#the-challenge)
  - [Screenshot](#screenshot)
  - [Links](#links)
- [My process](#my-process)
  - [Built with](#built-with)
  - [A few code examples](#a-few-code-examples)
  - [Continued development](#continued-development)
  - [Useful resources](#useful-resources)
- [Author](#author)
- [Acknowledgments](#acknowledgments)

## Overview

### The challenge

Users should be able to:

- View the optimal layout depending on their device's screen size.
- This has been achieved, the design is fully responsive.

---

### Screenshot Mobile

---

![stats preview card at mobile size](./readme-images/stats-preview-card-mobile-375.png)

---

### Screenshot Desktop

---

![stats preview card at desktop size](./readme-images/desktop_card__stats%20preview%20card%20component.png)

### Links

- Solution URL: [here](https://your-solution-url.com)
- View the live site: [here](https://stats-preview-card-wom.netlify.app/)

## My process

I used a mobile first approach and focussed on getting the structure of the HTML finished before doing any styling.

### Built with

- Semantic HTML5 markup
- BEM class naming
- CSS custom properties
- SCSS
- Flexbox
- CSS Grid
- Mobile-first workflow

### A few code examples

In the first example I have styled the background image to cover the container and maintain an aspect-ratio of 4/3.

When you use the aspect-ratio property in CSS, you don't need to set a specific width or height for the image. Instead, you can set the aspect-ratio property to the desired ratio, and the image will automatically adjust its size to maintain that ratio.
This can be useful when you want to ensure that an image maintains a specific aspect ratio but you don't know the exact dimensions of the container or how the image will be displayed on different devices or screen sizes.

#### aspect-ratio

---

```css
&__image {
  background-color: var(--img-bg-color);
  background-image: url(./images/image-header-mobile.jpg);
  background-size: cover;
  background-repeat: no-repeat;
  background-blend-mode: multiply;
  aspect-ratio: 4 / 3;
}
```

---

#### Clamp()

I used [clamp()](https://developer.mozilla.org/en-US/docs/Web/CSS/clamp) for the first time on this project. This allows you to set a minimum and maximum size for (in this case) font size, or another measurement value.
I also used it here for margin.

The function takes three values: a minimum, a preferred, and a maximum value. As the viewport is resized, the preferred value will kick in and calculate the size relative to the viewport width (vw) and root em size (rem), which is based on the root font size (usually set to 16px by default). The maximum value ensures that the size won't go beyond a certain limit. While you can use just a viewport width value for the preferred parameter, specifying a rem size can help provide a more consistent and reliable result across different devices and screen sizes. I used an online calculator for this which I've linked to below.

---

```css
h1 {
  font-size: clamp(2rem, 1.859rem + 0.563vw, 2.4rem);
}
```

```css
&__content-text {
  margin-top: clamp(1.067rem, 0.855rem + 0.845vw, 1.667rem);
  color: var(--primary-text-color);
  font-weight: var(--font-weight-regular);
  line-height: var(--line-height);
}
```

---

#### ARIA - Accessible Rich Internet Applications

Accessibility to website content whether it be for the visually impaired, or to those with other cognitive issues is essential for modern development, particularly for sites developed with JavaScript (React etc)

I must admit I've only just started to think about the importance of this with regard to markup and it's something I will spend time developing.

In this project I used an empty div to place the image as a background image on the page. I decided that this was a purely decorative feature and wasn't in need of any alt text, according to [W3C](https://www.w3.org/WAI/tutorials/images/decorative/).

I couldn't find a definitive answer to what I should put if using an empty div, so I settled on role="decorative". Correct me if I'm wrong please.

```html
<div class="card__image" role="presentation"></div>
```

#### CSS Custom Properties AKA CSS Variables

I have made the choice to switch from using SASS variables to CSS variables,
both allow you to store and reuse values in your CSS, but SASS variables are not as flexible.

With custom properties, you can change the value of a property dynamically using JavaScript, at the click of a button for example - think switching from light to dark mode.

Also custom properties follow the same inheritance rules as other CSS properties, so they can be reassigned at a lower level in the cascade, overriding the setting made at the root level.
Sass variables are static and cannot be changed once they are compiled.

I've put a link below if you'd like to read more about it.

---

### Continued development

I have dipped my toe into [ARIA](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA) and have started thinking a lot more about accessibility. This is something I will continue to develop.

### Useful resources

- [Clamp() Calculator](https://chrisburnell.com/clamp-calculator/?font-size-root=15&font-size-min=30&font-size-max=36&viewport-min=375&viewport-max=1440) - This is what I used to calculate clamp().
- [CSS Variables vs SASS Variables](https://codyhouse.co/blog/post/css-custom-properties-vs-sass-variables) - Some practical examples of how CSS variables compare to SASS variables.

## Author

- Website - [Mark Lawson](https://walkonmars.dev/)
- Frontend Mentor - [@walkonmars36](https://www.frontendmentor.io/profile/walkonmars36)
- Twitter - [@redmarkel](https://www.twitter.com/redmarkel)
