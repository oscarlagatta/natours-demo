# CSS Architecture, Components and BEM

# Architectue

## Think, build, architect mindset.

#

### Think

we should think abou the layout of your page before writing code

### Build

build the layout in HTML and CSS with a consistent structure for naming classes

### Architect

create a logical structure for the css with files and folders

Think in Component Strategy, we use component driven design. With CSS we try to devide the page in module building blocks that make up interfaces.
Components are the building blocks that we use to construct our interfaces so we can basically think of our interface as a collection of components, held together by the LAYOUT of the page.
The most important thing about components is that they should be RE-USABLE across project, and between different projects
Components should be independent, components should not depend of parent elements.

Build (we code with HTML / CSS) having a consistent strategy for naming our classes, using BEM (BLOCK ELEMENT MODIFIER).  
.block {}
.block**element {}
.block**element--modifier {}

BLOCK: stand alone component that is meaninful on its own. So those components that can be re-used anywhere in the project. And sometimes two or more blocks can be nested.
e.g. the recipe and the btn. The button block is inside the recipe block and that's perfectly normal and acceptable

# <figure class="recipe">

    <a class="recipe__button btn btn--round" href="#">Try</a>

ELEMENT: part of a block that has no stand alone meaning.
e.g. and info panel or stats box, if we take one of these elements out of the block the wouldn't be useful at all, the won't have any meaning. What's important to know here, is how the recipe block still appears in the class name within the block. And the selectors are created with really low specificity because we always use classes and they are never nested and then have a low specificity.

# <figure class="recipe">

    <div class="recipe__info">
    </div>
    <div class="recipe__status-box">
    </div>

MODIFIER: a different version of a block or an element.

# Architect

Create a logical folder structure for the cSS to live in, like 7-to-1 pattern, all it means is:

7 folder for partial SASS files, and
1 main SASS file to import all other files into a compiled CSS stylesheet.

#

# THE 7 FOLDERS

- base/
- components/
- layout/
- pages/
- themes/
- abstracts/
- vendors

Responsive design: to make the page adjust layout and visual style to any screen size.
Four principles:

Fluid Layout

- To allow the webpage to adapt to the current viewport with (or even height)
- Use % (or vh/vw) unit instead of px for elements that should adapt to viewport (usually layout)
- use max-width instead of width

Responsive Units

- use rem unit instad of px for most lengths
- to make it easy to scale the entire layout down (or up) automatically

Fleixble Images

- By default images don't scale automatically as we change the viewport, so we need to fix that
- Always use % for image dimensions, together with the max-width property

Media Queries

- To change CSS styles on certain viewport widths (called breakpoints)

Media queries along are completely useless, we really need to start creating fluid layouts from the very beginning. And the same is true for Responsive Units and Flexible Images.

# Layout Types

There are three ways of laying out web applications.

FLOAT LAYOUTS

The old way of building layouts of all sizes, using the float CSS property. Still used, but getting outdated.

FLEXBOX

Modern way of layoin out elements in a 1 dimensional row without using floats. Perfect for components layouts.

CSS GRIDS

For laying out element in a fully fledged 2 dimensional grid. Perfect for page layouts and complex components.

# Grid System

All columns they should be in a container called row
