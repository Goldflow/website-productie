# Frequently Asked Questions

## when using absolute position, how to center that element?

```CSS
  width: 100px; /* we set the width of the element fixed */
  position: absolute;
  /* as we know the full width of the element is 100px 
  we can calculate where it should come so it will be centered
  - we position the element at 50%; this makes the element start from the middle of it's parent
  - then we reduce 50px (so 100px/2); so that instead that the element starts from the middle of the parent, it'll start from the middle, minus the half of the element itself - this will result in centered element
  */
  left: calc(50% - 50px);
```

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

## when setting background image, how to ensure stays positioned in the center, regardless if parts of the image are lost

[https://stackoverflow.com/questions/47324360/background-size-cover-center-not-working
](https://stackoverflow.com/questions/47324360/background-size-cover-center-not-working
)

```CSS
section {
    /* background-image: ...; */
    background-size: cover;
    background-position: center center; /* center in both x & y axis */
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

## Can I get some inspiration how to use semantic html?

good article on Pluralsight [here](https://www.pluralsight.com/guides/semantic-html)

article on W3schools [here](https://www.w3schools.com/html/html5_semantic_elements.asp)

good article on Mozilla Developer Network [here](https://developer.mozilla.org/en-US/docs/Glossary/semantics#semantics_in_html)

---

## to what extent does writing semantic html add value to search engine optimization?

good article explaining this can be found [here](https://www.pluralsight.com/guides/semantic-html)

basically by litteraly saying to ["search engine robots"](https://metamend.com/archive/education/search-engine-bots/) this is the header, this is the navigation & this is the article, makes it easier to for search engine to offer up relevant parts of your website in the results of searches online

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

## flexbox vs grid? what to use when?

Kevin Powel explains it in a good way [here](https://www.youtube.com/watch?v=3elGSZSWTbM)

some points;

### Flexbox

- more flexible

- all elements behave more independent from each other

- to get more finegrained control, you'll more often have to also apply css to the children of the flexbox container

- flexbox is very good at taking care of the intrinsic sizing of elements; this means the actual size of the element (an element with only the word "Lorem" will be twice as small as an element with the word "LoremLorem") - by default it shrinks to intrinsic size

### Grid

- more structured

- all elements behave more relative to each other (taking same height/width depending on where they are)

- you can do much more at parent level without having to apply css to individual children elements (compared to flexbox)

- children living within grid that is created & doing what the parent is telling it to do

- CSS grid will setup the space & the children will take up the space that is put available

A question you can ask yourself is, do I want the elements to take up their own size (flexbox) or do I want them to all be aligned equally (grid)?

more details on how to decide - also by KP [here](https://www.youtube.com/watch?v=3elGSZSWTbM)

- structured layouts: grid

- layouts where all elements need to keep their size (e.g. navigation): flexbox

---

## CSS grid! give me more resources, help?

- great resource by Rachel Andrew [https://gridbyexample.com/](https://gridbyexample.com/)

- Kevin Powel video on CSS grid [https://www.youtube.com/watch?v=rg7Fvvl3taU](https://www.youtube.com/watch?v=rg7Fvvl3taU)

- Kevin Powel video on responsive grid [here](https://www.youtube.com/watch?v=sKFW3wek21Q)

- Wes Bos' [https://cssgrid.io/](https://cssgrid.io/)

- Firefox has a grid inspector, use it

- Morten Rand-Hendriksen did a pretty good talk on CSS Grid (although from 2017) - check it out [here](https://www.youtube.com/watch?v=Qgyg-SRr-UQ)

- complete guid to CSS grid on CSS tricks [here](https://css-tricks.com/snippets/css/complete-guide-grid/)

---

## how to use minmax() css property to attain responsive grid? [responsive grid]

in this line:

> minmax(220px, 1fr)

220px will stand for minimum value
1fr for the maximum value (which is one fraction)

this will come down to: at minimum always showing a width of 220px for each cell & maximum using 1 fraction

```CSS
main > section.portfolio-section > div {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
}
```

more info here [https://www.hongkiat.com/blog/css-grid-layout-minmax/](https://www.hongkiat.com/blog/css-grid-layout-minmax/)

---

## grid template areas - what are they & how to use? [responsive grid]

way to design first using a grid

then place elements on the grid & re-arrange using media queries

e.g.

```CSS
.site {
    grid-template-columns: 1fr 1fr;
    grid-template-rows: auto 1fr 3fr;
    grid-template-areas:
    "title title"
    "main header"
    "main sidebar"
}

@media screen and (min-width: 34em) {
    .site {
    grid-template-columns: 2fr 1fr 1fr;
    grid-template-areas:
    "title title title"
    "main header header"
    "main sidebar footer"
    }
}
```

see this video [here](https://youtu.be/Qgyg-SRr-UQ?t=1045)

---

## I want to show an simple transation / animation on a photo, how could I do this?

simple:

```CSS
img {
    /* this indicates that:
    - we need to go to & back from the original value in this selector
    - for the properties scale & filter
    - within 300ms & 500ms respectively
    - using an "ease" animation
    */
  transition: scale 300ms ease, filter 500ms ease;
}

img:hover {
  scale: 1.1; /*will set the scale of the image on hover*/
  filter: contrast(120%); /*will set the filter on hover*/
}
```

or see more advanced way how Kevin Powell does it: [https://youtu.be/OGJvhpoE8b4?t=701](https://youtu.be/OGJvhpoE8b4?t=701)

---

## need more info on pseudo selectors?

### :after / :before

:after / :before [https://developer.mozilla.org/en-US/docs/Web/CSS/::after](https://developer.mozilla.org/en-US/docs/Web/CSS/::after)

### :has

nice video [here](https://www.youtube.com/watch?v=OGJvhpoE8b4)

e.g.

```CSS
.img-gallery:has(img:hover) {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
}
```

## priority questions

- hoe gebruik ik een icon (svg) voor een li element?

## future list to be answered

- flex-grow re-explain

- optimize website for slow connections; use native lazy loading ([here](https://www.youtube.com/watch?v=AActXSWxsRo))

- eenmaal flex wrap gebeurt, kan je dan nog flex end forceren?

- refer website met stage offers / erasmus hogeschool?

## to mark in gotcha's

- flex style not inherited, only by direct children while other styles like font-size or background-color can be inherited by all descendants

## nice to have

- play with animations transform, 3D, animations / invert / blur

---

What is mainly determining the font size?

[long answer](https://www.w3.org/TR/CSS2/fonts.html)

---
