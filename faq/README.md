# Frequently Asked Questions

## how to remove scroll but that's still working

[https://stackoverflow.com/questions/16670931/hide-scroll-bar-but-while-still-being-able-to-scroll](https://stackoverflow.com/questions/16670931/hide-scroll-bar-but-while-still-being-able-to-scroll)

---

## how to add a line / border that is not as long as the content it is bordering on?

[https://stackoverflow.com/questions/4131490/any-way-to-limit-border-length](https://stackoverflow.com/questions/4131490/any-way-to-limit-border-length)

---

## how center an element?

on the parent of the element that you want to center set display flex & justify content as center (this is just one of the ways of doing it)

```HTML
<section class="parent">
    <article>element to center</article>
 </section>
```

```CSS
.parent {
    display: flex;
    justify-content: center;
}
```

---

## how put two or more elements next to eachother

on the parent of the elements you want to put next to eachother: set display flex & justify content as e.g. space-around (this is just one of the ways of doing it)

[more info on MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/justify-content)

```HTML
<section>
    <article>element to center</article>
    <article>element to center</article>
 </section>
```

```CSS
section {
    display: flex;
    justify-content: space-around;
}
```

---

## when creating a grid, sometimes it is expanding & not taking in to account the gap?

standard, when using fractions e.g. 1fr it will use 1 fraction of the available space

to ensure that instead we only use the maximum size of the object; we can use "max-content"

e.g. this will define a grid 5 by 5, with a gap of 50px

```CSS
.grid-wrapper {
    display: grid;
    grid-template-columns: repeat(5, max-content);
    grid-template-rows: repeat(5, max-content);
    gap: 50px
}
```

---

## where to find free icons / logos

### Icomoon

[free icons on https://icomoon.io/](https://icomoon.io/#icons-icomoon)

### Font Awesome

- [https://fontawesome.com/](https://fontawesome.com/)


---

## How to make a box or image perfectly round?

```CSS
div {
    border-radius: 50%;
}
```

---

## How to find / identify fonts?

- see: [this link from Reddit](https://www.reddit.com/r/identifythisfont/comments/vicnxt/web_font_finding_tips/) on finding web fonts

- google on "identify font"

---

## how to remove scroll but that's still working?

[https://stackoverflow.com/questions/16670931/hide-scroll-bar-but-while-still-being-able-to-scroll](https://stackoverflow.com/questions/16670931/hide-scroll-bar-but-while-still-being-able-to-scroll)

---

## How to stretch a background image?

```CSS
body {
    /** set the url of the image **/
    background-image: url(media/images/berg.png);
    /** set image size to "cover, this will ensure the images always covers either the maximum amount of height of width (whatever it is reaching first) **/
    background-size: cover; /** alternatively set to 100% **/
}
```

## How to ensure background image is not repeated?

```CSS
body {
    background-repeat: no-repeat;
}
```

## What is mainly determining the font size?

- short answer: it's complicated. font-size refers to the height needed to display the gamut of characters (from below stack overflow:)
- medium answer: [https://stackoverflow.com/questions/3495872/how-is-font-size-calculated/3496463#3496463](https://stackoverflow.com/questions/3495872/how-is-font-size-calculated/3496463#3496463)
- [long answer](https://www.w3.org/TR/CSS2/fonts.html) - official W3 specifications

---

## how to change default branch (e.g. from master to main)?

[https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/managing-branches-in-your-repository/changing-the-default-branch](https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/managing-branches-in-your-repository/changing-the-default-branch)

---

## priority questions

- hoe gebruik ik een icon (svg) voor een li element?

## future list to be answered

- flex-grow re-explain

- eenmaal flex wrap gebeurt, kan je dan nog flex end forceren?

- refer website met stage offers / erasmus hogeschool?

- uitleg :after / :before
[https://developer.mozilla.org/en-US/docs/Web/CSS/::after](https://developer.mozilla.org/en-US/docs/Web/CSS/::after)

## to mark in gotcha's

- flex style not inherited, only by direct children while other styles like font-size or background-color can be inherited by all descendants

## nice to have

- play with animations transform, 3D, animations / invert / blur

---



What is mainly determining the font size?

[long answer](https://www.w3.org/TR/CSS2/fonts.html)

---
