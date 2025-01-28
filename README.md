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
