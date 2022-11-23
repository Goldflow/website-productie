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

- Kevin Powel video [https://www.youtube.com/watch?v=rg7Fvvl3taU](https://www.youtube.com/watch?v=rg7Fvvl3taU)

- Wes Bos' [https://cssgrid.io/](https://cssgrid.io/)

- Firefox has a grid inspector, use it

- Morten Rand-Hendriksen did a pretty good talk on CSS Grid (although from 2017) - check it out [here](https://www.youtube.com/watch?v=Qgyg-SRr-UQ)

- complete guid to CSS grid on CSS tricks [here](https://css-tricks.com/snippets/css/complete-guide-grid/)

---

### grid template areas - what are they & how to use?

see this video [here](https://youtu.be/Qgyg-SRr-UQ?t=1045)

---

## I want to show an animation on a photo gallery, how could I do this?

see how Kevin Powel does it: [https://youtu.be/OGJvhpoE8b4?t=701](https://youtu.be/OGJvhpoE8b4?t=701)

---

## need more info on pseud selectors?

### :after / :before

 :after / :before [https://developer.mozilla.org/en-US/docs/Web/CSS/::after](https://developer.mozilla.org/en-US/docs/Web/CSS/::after)

### :has

nice video [here](https://www.youtube.com/watch?v=OGJvhpoE8b4)

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
