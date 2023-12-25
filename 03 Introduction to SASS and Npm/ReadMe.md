## SCSS 7 in 1 Style &mdash;

- base - animation, base, typography and utilities
- abstracts - function, mixin and variables
- components - store reusable codes and building block
- layout - layouts of website
- pages - pages (home page, about page and etc.)
- vendor - vendor plugin (bootstrap)

## Review: Basic Responsive Design Principles &mdash;

1. Fluid Layout

   - To allow webpage to adapt to the current viewport width (or even height)
   - Use %(or vh / vw) unit instead of px for elements that should adapt to viewport (usually layout)
   - Use max-width instead of width

2. Responsive Units

   - Use rem unit instead of px for most lengths
   - To make it easy to scale the entire layout down (or up) automatically

3. Flexible Images

   - By default, images don't scale automatically as we change the viewport, so we need to fix that
   - Always use % for image dimensions, together with the max-width property

4. Media Queries
   - To change CSS style on certain viewport width (called breakpoints)

## Layout Types &mdash;

1. Float Layouts

   - The `old way of building layouts` of all sizes, using the float CSS property. Still used, but getting outdated.

2. Flexbox

   - Modern way of laying out element in a `1-dimensional row` without using floats. Perfect for `component layouts.`

3. CSS Grid
   - For laying out element in a fully-fledged `2-dimensinal grid.`Perfect for `page layous and complex components.`

## Why use a float layout in the project &mdash;

- `The focus of this project is on using modern CSS properties and techniques:` clips, transforms, animations, background video, etc.

- Even though flexbox and CSS Grid are more modern, `every web developer should still know how float layouts work`

- As a profecssional developer, `your job will include working with older CSS codebases`, which will contain float layouts.
