# Systementor Zoo

A responsive single-page website created for **Systementor Zoo**.

The concept is **"The Chill Zoo"** --- a humorous zoo where the animals are mostly interested in
sleeping, relaxing, and doing as little as possible.

## Technologies

- HTML5
- CSS3
- CSS Flexbox
- CSS `clamp()`
- CSS media queries
- Google Maps embed
- Postman Echo for testing the newsletter form

No JavaScript or frontend framework is used.

## Assignment Requirements

### G requirements

The project fulfills the main requirements by providing:

- One `index.html` page / single-page application
- HTML and CSS only
- A separate CSS file
- English CSS class names
- One main `<h1>` heading
- `<h2>` and `<h3>` headings
- Images representing the selected animal species
- Animal images arranged horizontally with spacing and wrapped responsively
- A "Things to do" section with icons and descriptions
- Sections for:
  - Playground for the kids
  - Restaurants
  - All our amazing animals
- A newsletter subscription form
- Separate first-name, last-name, email and age fields
- Required fields
- Email format validation
- Form submission to `https://postman-echo.com/post`
- An animal table containing name, animal image, weight, and Wikipedia link

### VG requirements

The project also addresses the VG requirements:

- Responsive behavior for desktop, tablet, and mobile
- Multiple responsive breakpoints
- A Google Maps embed showing a zoo location

## Page Structure

### Header

The header contains the Systementor Zoo Logo and navigation links to the main sections of the page.

On smaller screens, the normal navigation is replaced by a CSS-only hamburger menu.
The menu uses a checkbox, label, the `:checked` pseudo-class, and the general sibling selector instead of JavaScript.

### Hero

The hero introduces the site with the main heading:

> The most boring zoo you will ever visit.

A sloth image is used as part of the humorous design.

### Animals

The featured animal section contains eight animals:

1.  Koalas
2.  Sloths
3.  Pandas
4.  Lions
5.  Elephants
6.  Giraffes
7.  Hippos
8.  Red Pandas

Each animal has an image, an `<h3>` heading, and a short description.

Flexbox with `flex-wrap` is used so the cards automatically move to new
rows as the available width becomes smaller.

The cards use consistent widths and fluid sizing so different text
lengths do not create uneven card widths.

### Things to Do

The "Things to do" section presents activities using icons and short descriptions.

Additional content describes the playground, restaurants, and the zoo's animals.

### Newsletter

The newsletter form asks for:

- First name
- Last name
- Email address
- Age

Native HTML validation is used to make fields required and to validate
the email and numeric age fields.

The form submits to:

```text
https://postman-echo.com/post
```

The response does not need to be displayed.

### Animal Table

The animal table contains:

- Animal name
- Animal image
- Weight
- Wikipedia link

### Find Us

The page contains an embedded Google Map showing Kolmårdens djurpark.

### Footer

The footer contains the project/author information.

## Responsive Design

Responsive design was an important part of the project.

The layout adapts to different screen sizes by using:

- Flexbox
- `flex-wrap`
- Fluid dimensions
- `clamp()`
- Media queries
- A mobile hamburger navigation

The animal cards, headings, spacing, and other elements can scale
smoothly without requiring a media query for every small change.

For example:

```css
width: clamp(9rem, 14vw, 15rem);
```

allows an element to scale between a minimum and maximum size.

The stylesheet contains responsive breakpoints for desktop, tablet, and mobile layouts.

## CSS Approach

The stylesheet starts with a small reset and defines reusable CSS
variables in `:root` for the project's colors.

Examples include variables for:

- Header colors
- Text colors
- Background colors
- Gold/accent colors
- Table colors
- Link colors

### Flexbox

Flexbox is used for:

- Header navigation
- Animal cards
- Activity cards
- Form layouts
- Mobile navigation

For the animal section, `flex-wrap: wrap` allows the cards to move to
new rows automatically.

One important lesson was that `gap` controls the space between flex
items, but different item widths can make the spacing appear uneven.
Giving the animal cards a consistent width produces a more balanced
layout.

### `clamp()`

`clamp()` is used for fluid sizing of images, headings, spacing, and other elements.

This reduces the need for unnecessary media queries and makes the layout
transition more smoothly between screen sizes.

## Form Validation

The newsletter form uses native browser validation.

Examples include:

```html
<input type="text" required />
<input type="email" required />
<input type="number" required />
```

The browser therefore checks that required fields are filled and that
the email field uses an appropriate email format.

## Accessibility

Basic accessibility practices are included:

- Semantic elements such as `<header>`, `<main>`, `<section>`,
  `<article>`, `<nav>`, and `<footer>`
- Descriptive `alt` text
- Labels associated with form fields
- A title for the Google Maps iframe
- Navigation links pointing to page sections
- A viewport meta tag for mobile devices

There is still room for further accessibility improvements, especially
for keyboard interaction with the mobile menu.

## My Work Process

The general development process was:

1.  Identify the required sections from the assignment.
2.  Plan the page structure.
3.  Build the semantic HTML structure.
4.  Add images, animal cards, activities, form, table, map, and footer.
5.  Create the CSS reset and reusable color variables.
6.  Build the desktop layout.
7.  Make the animal cards responsive using Flexbox.
8.  Add fluid sizing with `clamp()`.
9.  Add responsive behavior for smaller screens.
10. Implement the CSS-only hamburger menu.
11. Test different viewport sizes.
12. Use browser DevTools to investigate CSS and layout problems.
13. Clean up and simplify the stylesheet.

Testing at different viewport sizes was especially important because a
layout that looks correct on desktop can behave very differently on a
narrow mobile screen.

## How I Learned New Things

The project gave me practical experience with several areas of CSS.

### Flexbox

I learned more about:

- `display: flex`
- `flex-direction`
- `justify-content`
- `align-items`
- `flex-wrap`

A particularly useful lesson was understanding that different content
lengths can change the width of flex items and therefore affect how
spacing appears.

### CSS Specificity

The mobile navigation was a good example of CSS specificity.

For example:

```css
header .header-container nav {
  display: flex;
}
```

is more specific than:

```css
header nav {
  display: none;
}
```

Browser DevTools made it possible to see which rule was winning and why.

### CSS-only Interaction

The hamburger menu demonstrated how simple interaction can be created
without JavaScript using:

- A checkbox
- A `<label>`
- `:checked`
- The `~` sibling selector

### Responsive CSS

I also learned to distinguish between cases where a media query is
necessary and cases where fluid CSS such as `clamp()` is a better
solution.

## How AI Was Used

AI was used as a development assistant rather than as a replacement for
understanding the code.

It was used to:

- Explain HTML and CSS concepts
- Investigate layout problems
- Suggest possible CSS solutions
- Explain why CSS rules were not being applied
- Compare Flexbox and Grid
- Help structure documentation

The suggestions were tested and checked in the browser.

For example, when the mobile navigation did not work correctly, browser
DevTools was used to inspect the actual `<nav>` element. This revealed
that a more specific CSS selector was overriding the mobile rule.

## What I Learned

Some of the main lessons from the project were:

- HTML structure affects what CSS selectors can target.
- Flexbox is well suited for responsive collections of cards.
- Different content lengths can affect perceived spacing.
- `gap` does not make differently sized flex items visually identical.
- CSS specificity can cause a seemingly correct media-query rule to be
  ignored.
- Browser DevTools is extremely useful for finding CSS problems.
- `clamp()` can reduce the need for excessive media queries.
- Semantic HTML makes the page structure clearer.
- Native HTML validation can handle many basic form requirements
  without JavaScript.
- Responsive design should be considered throughout the
  implementation, not only at the end.

## What I Would Do Differently

If I started the project again, I would:

- Spend more time planning the layout structure before writing detailed CSS.
- Establish clearer container naming from the beginning.
- Decide on the responsive strategy earlier.
- Use DevTools earlier when a CSS rule behaves unexpectedly.
- Plan the mobile navigation structure before implementing it.
- Consider keyboard accessibility for the mobile menu in more detail.

## Future Improvements

Possible future improvements include:

- Better keyboard accessibility for the mobile menu
- Improved table behavior on very small screens
- More detailed animal information
- More sophisticated animations
- A real backend for newsletter subscriptions
- User feedback after successful form submission
- More accessibility testing

## Running the Project

No build process is required.

Open `index.html` in a browser.

Alternatively, use a local development server such as the Live Server
extension in VS Code.

## Project Structure

```text
SystementorZoo/
├── index.html
├── index.css
├── README.md
└── images/
    ├── animals/
    ├── icons/
    └── background.png
```

## Author

**Per Söderberg**

Systementor Zoo --- Frontend Development Project
