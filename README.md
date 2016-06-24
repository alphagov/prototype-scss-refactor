# GOV.UK Template, Toolkit & Elements SCSS Refactor

---

The purpose of this:

- Decide on filenames and naming conventions
- Take the existing scss from the GOV.UK template, GOV.UK frontend toolkit and GOV.UK elements and apply ITCSS principles
- Rewrite classnames using BEM to give greater flexibility than provided by GOV.UK elements

---

Things to do:

Use BEM
Use Normalize

Remove duplicate resets
Compare Normalize to GOV.UK base styles and elements reset

Use scss comments // not css comments /* */

Use single-level-deep classes, reduce nesting
Avoid qualifying
Avoid type selectors


Ideally, it will work like this:

---

Questions:

Names for sizes of things?
for example

    .button--big or .button--large
    .font-small or .font-alpha

Do we want to use full words or abbreviations?
for example

    .btn vs .button
    .nav vs .navigation

--

The structure of the /scss/ folder aims enable css to be written in specificity order.

### Settings

High level settings, global variables

For example colour values, spacing units, globally available variables
This layer can be used by the entire project

### Tools

Mixins and functions
Global mixins come after the settings
Need to come before the rest of the prohect and can affect the entire project

For example globally available font sizes
tools.typography.scss
Decide which mixins are global ones

### Generic

Ground zero styles, normalize, resets box sizing
the * selector for box-sizing
This layer affects a lot of the dom

### Base

Unclasses HTML elements (type selectors)
More explicit than the reset layer
h1 - h6, basic links, lists

### Objects

We will work up to having this layer!!
This is the objects layer, put the media object in here.

Try to create a generic list object

    .ui-list {}
    .ui-list-item {}

Choose agnostic names

### Components

Fully designed chunks of UI
Private mixins sit in relevant file
This is where the ui-list becomes a product list

    .products-list {}
    .products-list__item {}

### Overrides, helpers and utilities

Affect one piece of the dom at a time
Very high specificity, usually carry !important;
e.g. helper class

    .one-half {
      width: 50% !important;
    }

This is the most specific.

We are progressively adding and never undoing.
Causes rules to trickle together and we are adding on layers, not undoing.
Global styles happen early,

We need a way of making a familiar environment from people.

Reduce the size of the codebase.
Remove CSS which isn't being used, remove bloat and waste.

### ITCSS Principles:

- Order stylesheets from generic to specific, this helps you manage the cascage
- You're also then doing less overriding as you move further down the set of stylesheets
- Manages source order and makes it specificity based
- Filters explicitness
- Check to see how much waste it removed (reduced number of strikethroughs for each element)
- Add documentation, if you need to edit type selectors, edit overrides, look in this layer.
- Open to extension, but closed to modification

### ITCSS tl;dr
- Write CSS in specificity order
- All rulesets should only ever add to and inherit from other styles
- DO NOT UNDO CSS later in the stylesheet
- Overrides and helpers need to come last
  This prevents a spike in the specificity graph
- Add extra layers as you need
- Media queries sit with the rules that they affect



------------------------------------------------------------------------------------------

### Other things to think about

- What to do with the font files?
- Can we fallback to PNGs in template/images and instead use SVG?
- Print stylesheet & how do the mixins for this work?
- What units do we want to use rem/em/px a combo? At the moment we use 15px, this means we can't vertically align things properly

