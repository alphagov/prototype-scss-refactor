GOV.UK Template, Toolkit & Elements SCSS Refactor

1. Decide on filenames and conventions
2. Take the existing code from the GOV.UK template and GOV.UK frontend toolkit and fit it into this new structure
3. Rewrite elements using BEM to give greater flexibility when using it
4. Check against all principles below

Principles

Remove duplicate resets


Writing classnames:

Use single-level-deep classes wherever you can. Avoid nesting.
Avoid qualifying.
Avoid type selectors.



.namespace-thing-type



Naming conventions

More transparent.
More strict.
More informative.
Most useful in your HTML. Let’s look at BEM.

--

Convention for names of sizing things

for example .button--big or .button--large?

Same for type sizes

--

Do we want to use full words or abbreviations?
for example, .btn vs .button
.nav vs .navigation

--

Things to do:

[ ] Compare Normalize to GOV.UK base styles and resets
// https://raw.githubusercontent.com/necolas/normalize.css/master/normalize.css
// https://github.com/alphagov/govuk_template/blob/master/source/assets/stylesheets/_basic.scss

[ ]