# Adding Style to The React Datetime Library

### Project
Work Project

### Date
04/15/2022

### Technology
- JavaScript
- React
- [React Datetime](https://github.com/arqex/react-datetime)

### The Problem

I received feed back on my PR for the Combine project where I updated the date time picker for the observation tables. There was some needed styling for the input box to match the rest of the table.

I needed figure out how to add styles to the Datetime JSX component. Currently the styles were coming from the library CSS and the tailwind classes.

### Process

- Began editing the `className` attribute to take advantage of tailwind features for styling.
    - This resulted in everything around the box being styled.
    - discovered that the `classNames` were being assigned to the parent tag.
- Tried adding CSS to the lib's CSS file
    - Turns out the library overwrites all the CSS in that file, so anything added would be deleted at build time.
- Used the chrome webtools to deep dive into what is being assigned where in the HTML.
    - Turns out the CSS I was adding to the library styles wasn't working even before being overwritten.
- Played with the chrome webtools to see if I could discover what was overriding the color of the input box to not match the cell background.
    - Was able to see that it looked like user agent styles were overriding it.
- Reached out to Michael Li for help.
    - He took a look and suggested exactly what I did, which was to create a custom CSS and use that.
    - However, he took all the CSS from the library styles and copied them over to a new CSS file in the same directory as the input widget. Then added the custom stuff needed.
    - Then he added the custom styles he needed and switched the import to the custom file in the module, which worked.

### Solution

Copy over the library CSS into a custom CSS file and add the styles needed. Then import that custom CSS into the JSX component.

#ProblemSolving