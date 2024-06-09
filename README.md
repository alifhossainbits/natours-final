# Natours - A travelling web page

## Howdy!🚀 Just a heads-up:

So, this README is basically Alif's SCSS playground—think of it as a rollercoaster of insights and a dash of chaos. Not everyone's jam, but that's cool! Questions poppin'? Hit up Alif anytime; he's down for a chat. Ready for the wild ride through this learning maze? Buckle up! 🎢🤘💬

# node SASS

`npm init`

`npm install node-sass --save-dev`

- `—save` it saves as dependencies while `—save-dev` saves as dev-dependencies

to install from package.json run `npm install`

to uninstall a package `npm uninstall jquery`

## Create SCSS

create sass folder `mkdir sass`

- `touch main.scss` creates first scss file
-

### run compiler

```json
"scripts": {
"compile:sass": "node-sass sass/main.scss css/style.css -w" // -w keeps watching the code
},
```

“command”: “package name input folder output folder” `npm run compile:sass`

# 7-1 CSS Architecture

Inside sass folder there should be -

- **base folder** - for low level basics such as resets and styles for html and body element selectors.
  - \_base.scss
  - \_animations.scss
  - \_typography.scss
  - \_utilities.scss
- **abstracts folder** - only put code thats not gonna output any css. such as variables, mixins etc.
  - touch \_variables.scss \_mixins.scss \_functions.scss
- **components folder** - one file for each components, reuseable building blocks, completely independent, held together by the layout of the page.
  - \_button.scss
- **layout folder** - global footer, header etc
  - \_header.scss
- **pages folder** - specific design for specific page
  - home.scss
- **themes folder** - for themes
- **vendors folder** - for third party css like bootstrap, tailwind or an icon system, or an animation framework

to import these sub files in main.scss we need to `@import "path;"` for ex: `@import "base/base";`

### linux command for easy creation:

- folders - mkdir base abstracts components layout pages

### put this in main.scss

```json
@import "abstracts/functions";
@import "abstracts/mixins";
@import "abstracts/variables";

@import "base/animations";
@import "base/base";
@import "base/typography";
@import "base/utilities";

@import "pages/home";
```
