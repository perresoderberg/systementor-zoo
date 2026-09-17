# Systementor Zoo

A website for Systementor Zoo.

The goal of the assignment was to build the website based on the
provided design images and reproduce the layout as closely as possible.
The assignment is built using vanilla HTML and CSS, with CSS Flexbox and/or Grid allowed.

## Contents

The project contains three parts:

- **Home page** -- a large Systementor Zoo image with two information tags
  and a footer containing three information areas.
- **News** -- information about activities, restaurants, and the animals.
- **Animals** -- four animal categories and a table containing
  animals, weight, and Wikipedia links.

## Technologies

- HTML5
- CSS3
- CSS Flexbox
- CSS `clamp()` for responsive sizing
- CSS gradients
- CSS variables
- A shared CSS file for the reset and global variables

## Running the project

The project is intended to run locally in a web browser.

1.  Clone the repository:

```bash
git clone https://github.com/perresoderberg/systementor-zoo.git
```

2.  Open the project folder in Visual Studio Code.

3.  Start `index.html` using, for example, **Live Server**.

4.  The website will open in the browser. When using Live Server,
    changes to the HTML/CSS can be reloaded automatically.

## Development workflow

### 1. Create the project

I started by creating a repository on GitHub and cloning it locally to my computer.

### 2. Get the assets

I downloaded the images from the template project and placed them in my own `images` directory.

### 3. Review the first page

I started by analysing how the first page was structured and which parts needed to be recreated.

I identified:

- A background image covering the main part of the page
- A footer covering the lower part of the page/image - two menu items
- Two information tags positioned over the main image
- A footer divided into three sections

I used Flexbox to place the three footer sections horizontally and
`flex-direction: column` for the content inside each section.

### 4. Make the first page responsive

I then worked on making the first page look good on both larger and smaller screens.

One problem I encountered was the two tags positioned over the main image.
Initially, I tried to make both tags responsive independently.
This made the positioning unnecessarily difficult because the two tags
needed to maintain their relationship to each other.

I therefore changed the structure and placed both tags inside a shared `tag-container`.
This allowed the tags to move as a unit when the window size changed.

This is one of the things I would definitely do differently if I started the project again.

### 5. Review `news.html`

I then reviewed `news.html`.

It was relatively simple, with different `section` elements.
I used CSS to create the layout and added, among other things,
a gradient to the `body` to reproduce the design.

### 6. Review `animals.html`

For the third page, I analysed how the different parts were structured.

The header consists of four sections:

- Cats
- Dogs
- Hens
- Parrots

Each section contains three elements:

1.  image
2.  heading
3.  text

I could use the same Flexbox approach here as on the first page.

### 7. Create the table

For the animal list, I used a real HTML `<table>` because the content
consists of tabular data with rows and columns.

I used:

- `<thead>` for the table header
- `<th>` for column headings
- `<tbody>` for the data
- `<td>` for the cells
- `:nth-child(even)` for alternating row colours
- borders between cells
- `box-shadow` for the table shadow

I mainly let the `<th>` and `<td>` elements determine the table's size
instead of giving the entire table a fixed width and height.

The layout around the table was built using Flexbox.
Grid could also have been used to place the table and information text next to each other.

### 8. Responsiveness on the animals page

The third page is not fully responsive.

I tried to make the layout work well on smaller screens, but it became
difficult to maintain the same layout while also making it look good.

Since responsiveness on this part was not an explicit requirement in the solution I chose,
I prioritised getting the desktop layout as close to the design as possible.

### 9. Shared CSS

I moved CSS that is used by several pages into a shared CSS file called
`global.css`.

This includes:

- CSS Reset
- global CSS variables
- shared basic settings

This means that I do not need to repeat the same reset and colour variables in every separate CSS file.

### 10. Final adjustments

Finally, I worked on details such as:

- shadows
- gradients
- spacing
- responsive sizes
- `clamp()`
- table size and positioning
- centering images
- padding and gaps
- positioning content at different screen sizes

## New knowledge and how I learned

During the project I gained a better understanding of how CSS works when
several different properties affect the same layout.

### Flexbox

I used Flexbox to:

- position elements horizontally
- centre elements
- create column layouts
- control spacing using `gap`
- combine horizontal and vertical layouts

### CSS Grid

I also learned that Grid could be a good alternative for some parts of
the project, especially for the layout where the table and information
text are placed next to each other.

### `clamp()`

I used `clamp()` to make sizes responsive.

For example:

```css
font-size: clamp(1rem, 1.5vw, 2rem);
```

This makes it possible to have a minimum and maximum value while
allowing the value to change with the viewport size.

### Gradients

I worked extensively with both `linear-gradient()` and `radial-gradient()`.

I gained a better understanding of:

- gradient direction
- percentage values in gradients
- multiple gradient layers
- `transparent`
- colour transitions from different directions

## How I used AI

I used AI as a support tool to help me understand and solve problems.

I mainly used AI:

- to create a CSS Reset
- when I had forgotten the syntax for certain CSS properties
- to get explanations of a few CSS properties
- to understand concepts such as gradients

## Lessons learned

The biggest lesson from this assignment is that it is important to think
about the **structure first and responsiveness afterwards**.

A clear example is the two tags on the home page. I initially tried to
make both tags responsive individually. It worked, but created
unnecessary CSS and made it harder to maintain their positions relative
to each other.

A better solution was to create a wrapper/container for both tags and
let the container handle their positioning.

I also gained a better understanding that it is not always necessary to
give an element a fixed `width` and `height`. In many cases it is better
to let the content determine the size and use properties such as
padding, `gap`, Flexbox, or Grid.

Another lesson is that CSS can become much harder to manage if a layout
problem is solved by continuously adjusting individual elements.
Sometimes it is better to go back and change the HTML structure.

## What I would do differently today

If I did the assignment again, I would spend more time planning the HTML
structure before starting to write the CSS.

In particular, I would:

1.  Identify which elements belong together and create wrappers for them from the beginning.
2.  Decide which parts should use Flexbox and which parts would be better suited to Grid.
3.  Start with a simple desktop layout and then make the required parts responsive.
4.  Avoid trying to make every individual element responsive if a shared container can solve the problem.
5.  Plan the shared CSS structure earlier so that the reset, variables and page-specific CSS are clearly separated.
