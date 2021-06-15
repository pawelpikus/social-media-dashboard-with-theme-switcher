# Frontend Mentor - Social media dashboard with theme switcher solution

This is a solution to the [Social media dashboard with theme switcher challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/social-media-dashboard-with-theme-switcher-6oY8ozp_H). Frontend Mentor challenges help you improve your coding skills by building realistic projects. 

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
- [Acknowledgments](#acknowledgments)

## Overview

### The challenge

Users should be able to:

- View the optimal layout for the site depending on their device's screen size
- See hover states for all interactive elements on the page
- Toggle color theme to their preference

### Screenshot

![](./design/desktop-preview.jpg)

### Links

- Solution URL: [Github Repo](https://github.com/pawelpikus/social-media-dashboard-with-theme-switcher)
- Live Site URL: [Github Pages](https://pawelpikus.github.io/social-media-dashboard-with-theme-switcher/)

## My process

### Built with

- Semantic HTML5 markup
- CSS custom properties
- Flexbox
- CSS Grid
- Mobile-first workflow
- JS

### What I learned

There's this cool feature in CSS Grid called auto-fill which I found really useful: 

```css
.main-grid{
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(200px, 1fr)); 
  }
```
It helped me a lot to maintain the full responsiveness of this site.

Also, the toggle button was a bit of a challenge - I learned how to use :checked and ::after pseudo classes to make it work.

```html
  <input type="checkbox" id="toggle-button" class="toggle-button" aria-label="dark mode slider">
```

```css
.toggle-button::after {
  content: "";
  display: inline-block;
  position: absolute;
  left: 1px;
  top: 1px;
  width: 18px;
  height: 18px;
  background-color: #fff;
  border-radius: 50%;
  transform: translateX(0);
  transition: all 0.3s cubic-bezier(0.2, 0.85, 0.32, 1.2);
}

.toggle-button:checked::after {
  transform: translateX(calc(100% + 2px));
  background-color: hsl(228, 28%, 20%);  
}
```
And how about the gradient border? I didn't realised there is no possibility to directly enforce gradients to border attribute. So, I used a hack with good ol' ::after:

```css
.main-card--insta{
  position: relative;
  top: 2px;
  border: 2px solid transparent;
  background-clip: padding-box;
}

.main-card--insta::after{
  position: absolute;
  content: '';
  top: -5px; bottom: 0;
  left: 0; right: 0;
  background: linear-gradient(90deg, hsl(37, 97%, 70%), hsl(329, 70%, 58%));
  border-radius: 10px;
  z-index: -1;
}
```


### Continued development

Now it is time to incorporate more JS in my sites!

## Author

- Frontend Mentor - [@pawelpikus](https://www.frontendmentor.io/profile/pawelpikus)

## Acknowledgments

Thank you Kevin Powell for an awsome Scrimba Bootcamp on Responsive Web Design! And frontendmentor.io for great challenges.
