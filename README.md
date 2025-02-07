CSS SHORT NOTES:

---

- universal reset, ensures the page will be redered the same in all browsers

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  }

body{
font-family: "Lato", sans-serif;
font-weight: 400;
font-size: 16px;
line-height: 1.7;
color: #f4f4f4;
padding: 30px; -- its always so clean...
}

95vh - 95% of the view height
background-position: top; ---The top of image stays there always, you can also use bottom and center
Use of gradients with background-image:
e.g. background-image: url(../img/hero.jpg)
background-image: linear-gradient( --use the color you want as the gardient--) , url(../img/hero.jpg)

e.g. linear-gradient(to right, #fhhfhdf, #uhfuhf) ...to right bottom (haha even two descriptions)
use a good color picker extension, so that you can pick the rgba() at atleast 70% eg.
linear-gradient(to right, rgba(..., ..., ..., 0.7), rgba(..., ..., ..., 0.7))

\*\*\*\*Using clip-path to cut out a small piece;
you will use x and y coordinates starting from left in a clockwise marner...
The div with the clip-path will be clipped accordingly.
clip-path: polygon(x y, x y, x y, x y)
clip-path: polygon(0 0, 100% 0, 100% 80%, 0 100%) --you can specify with percentage, px, vh (e.g. 75vh)
You can make a triangle with this:
clip-path: polygon(50% 0, 100% 0, 0 100%)
search clippy website with this shapes.

\*\*\*\*Easy way to center anything - using transform, top, left...
When using images control the height and leave width to be automatic... height:20px ...no weight specified...
e.g logo-box{
position: absolute;
top: 40px;
left: 40px;
}
or .text-box{
position: absolute;
top: 40%;
left: 50%;
transform: translate(-50%, -50%);
text-align: center;
}
you can use px or %

\*\*\*\* Create CSS animations using @keyframes and animation property:
@keyframes moveInLeft{
/_ 0% is what we want at the start of the animation_/
0%{
opacity: 0;
transform: translateX(-100px);
}
80% {
transform: translateX(20px);
}
100%{
opacity: 1;
transform: translateX(0);
}
/_ 100% is what we want at the end of the animation_/
/_ translateX means the animation is on X axis_/
}
-- use it to the text class you want to animate using-
animation-name: moveInLeft;
animation-duration: 1s;
other cools like:
animation-delay:
animation-itereation-count: ---being how many times...
animation-timing-function: ---How the animations work out they are built in,
e.g ease, ease in, ease out etc
-- Css shortcut being:
animation: moveInRight 1s ease-out;
where we have animation and all attributes, no comma.
-- Its good habit to use "backface-visibility: hidden;" on the parent div, This reduces any movements of the parent div due to the transform animation bit... "You can notice the shaking"
-- Animations can be reused all over once defined:
e.g reuse
.logo:hover{
animation: moveInRight 1s ease-out;
}

\*\*\*\* What pseudo-elements and pseudo-classes are, use of ::after pseudo-element, creation of hover animation using transition property

Pseudo-classes are a special state of a selector.
.btn:link, .btn:visted{

} --- When styling the btn you use the pseudo-class link
--- visited pseudo state is obvious when the link has already been seen by the user.
We want the visited to remain the same color not changing, thats why they are being styled together

-- display: inline-block; is used when the elements have heights and padding in them.

pseudo-element is a copy of the element...

---

3 pillars of good html and css

- Responsive design - good on all screen sizes.
- Writing maintainable and scalable code - take care of how you organize your code, naming folders and more ...
- Good web performance - little http requests, little files and less code..., reducing also the images!!!

Usage of rem is soo good...
you can change values by just modifying the font size...

set font size to 10px for easier calculations.
html{
font-size: 10px;
}

-- Margin is used to specify the space between one element and the other...

box-sizing: border-box; /_ This is to ensure that the padding and border are included in the width and height of the element _/
\*\* This really ensures the visual formatting model just picks any specified width or height and use it when calculating the width or height respectively of a given element.

--- Box Types: Block, inline & inline-block
The box type is defined using the display property.
e.g display: block; **_ flex, list-flex and table also produce block-level boxes."_**

- Block boxes occupy 100% of parent's width and are vertically, one after another...e.g Divs and Ps are by default set as block level boxes.

Inline box - content is distributed in lines.
Therefore occupies only content's space, there is no line breaks like in border box (where a new div is by default in a new line)
there are no heights and widths in inline box and paddings & margins can only be used horizontally...

Inline Block combines the 2.
Just like inline they occupy only content's space and there is no line breaks like in border box. But they display like block boxes...

--- Positioning
Normal - just default or natural way
Float - This makes the element be uprooted from normal flow and taken to the utmost left or right; until it touches the edge of its containing box or another floated element. Text and inline elements will wrap around it. You can use clear fixes to position it well and remove floats!...

Absolute positioning - When an element is set to fixed or absolute positioning the elemnt is also uprooted from normal flow. Absolute position element does not affect content or elements that surround at all. You use top left right and bottom to relatively position it in its container. Css solves any overlapping issues here using stacking context.

-- Stacking Context
Stacking contexts are like layers that form a stack.
Most known is z-index...

---- Architecture
\*\*\* Think - About the layout and have an image of the webpage b4 writing code...
Use a component driven design. Try to divide the page into modular components. Now any interface will have a collection of components held together by the overall layout of the page. Have clean and reusable components that can be reused in the same project and even different projects... Also make sure they are independent so that each can be completely on its own!

\*\*\* Build - Build the layout now with a consistent structure for naming classes...
The best approach for naming classes is BEM (Block Element Modifier). You have one name for the block that you will use as BEM to specify the block we are in. This is more code but way better and readable.

<div class="header__logo-box">   : You use double bottom lines to separate block from its element.
<span class="heading-primary--main">Football</span>  : You use double lines to separate block from its modifier. main is not really an element but just a modifier...
 <a href="#" class="btn btn--white btn--animated">Meet our Team</a>   : Here the button is a block that will be reused while the rest are modifiers to change a bit the button and simply create some different versions of the same button.

\*\*\* Architect - Creation of a logical architecture for the CSS with files and folders. Use the 7-1 method where: There are 7 diff folders for partial sass files and 1 main sass file to import all the others into a compiled CSS stylesheet.

Use sass for cleaner css. You only need a compiler that will convert the sass code with css.

- Sass gives us variables, that can be reusable
  e.g colors, font-sizes, spacing e.t.c
- Sass allows nesting of selectors inside one another
- Operators for mathematical operations inside of css
- partials and imports - which allows different files and importing them all into one single file.
- mixins - this allows reusable pieces of css code
- extends - this makes different selectors inherit declarations that are common to all of them
- Control directives - helping to write code using conditionals and loops.
  \*\* You use the scss (Sassy Css) because its similar to css.

Basic Responsive Designs:

1. Fluid Layouts - To allow the webpage to adapt to the current viewport width/height
   use % or vh/vw
   use max-width instead of width

- use of flexbox and grid is key. (floatlayout is also another layout)

  2.Responsive units
  use rem units instead of px

  3.Flexible and fluid images
  Images don't scale up automatically, use % for image dimensions together with max-width in certain situations.

4. Media querries
   Ensure you use it to cahnge css styles on certain viewport widths. (called breakpopints)

\*\*\* How to build float layout grid:
--- How to build a simple grid system:
A grid helps build consistent interfaces.
The grid can have 1-4 columns: ---

- In the grid the columns must stay on their own solo rows.
  .row{
  max-width: 114rems; //we used rems and max width to specify the viewport width!//
  }
  margin: 0 auto; //This is used to center block elements in another block element e.g. div in another div ---

--- How the attribute selector works:
You can use [] boxes to enter an attribute in css that you want to style.
e.g [src]{
css goes here!
}  
Also e.g [class^="col-"] //This means pick and style all attributes that start with col-
e.g [class^="col-"]{
css goes here!
}
[class*="col-"] //Now this picks all attributes with the word col.
[class$="col-"] //Dollar sign picks all attributes ending with col.

---

--- How the :not pseudo-class works;
.row{
/_margin-bottom: 8rem;_/

$:not(:last-child){
margin-bottom: 8rem;
} //All rows will be selected except the last child when we use not pseudo class
} ---

--- How calc() works and its difference to sass operations
// Usage of native calc is used instead of sass because in grid layouts all the calculations will be done later when the users layout is known, instead of now like in sass.
width: calc((100% - $spacingSpace)/2);
You should use #{} because we are using sass variable in a css ftn.
e.g. width: calc((100% - #{$spacingSpace})/2);
also e.g width: calc((100% - 2 \* #{spacingSpace})/2);

---

\*\*\* ABOUT section - And things to learn!!!
--- Thinking about components
--- How and why to use utility classes
--- How to use the background-clip property
.heading-secondary{
font-size: 2.5rem;
text-transform: uppercase;
font-weight: 700;
display: inline-block; //The bg will not be the whole width
background-image: linear-gradient(to right, $light-orange, $dark-orange);

    -webkit-background-clip: text;   //Clip the bg around the text only.
    color: transparent;  // So the text can be colorless to allow the color to be seen on the text.

}
--- How to transform multiple properties simultaneously
--- How to use the outline-offset property together with outline
--- How to style elements that are not hovered while others are...

.section-about{
background-color: lighten($cream-bg, 20%);
    padding:$space-elements 0;
margin-top: -20vh;
}
I learnt how to lighten the bg, using lighten function. Also margin top of negative to move up.
