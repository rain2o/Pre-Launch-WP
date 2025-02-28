# Wordpress Pre-Launch 🚀

![WebPack 5.44.0](https://img.shields.io/badge/WebPack-5.44.0-brightgreen)
![Babel 7.14.6](https://img.shields.io/badge/Babel-7.14.6-brightgreen)
![BrowserSync 2.27.4](https://img.shields.io/badge/BrowserSync-2.27.4-brightgreen)
![PostCSS 8.3.5](https://img.shields.io/badge/PostCSS-8.3.5-brightgreen)
![Tailwind 3.1.3](https://img.shields.io/badge/Tailwind-2.2.4-brightgreen)

Wordpress Pre-Launch is a VERY beginnger friendly wordpress template built on webpack. It makes use of webpack, Babel, Sass, Tailwind, Browsersync, PostCSS, ESLint, Stylelint, Prettier and more. And if you have no idea what any of that is, then this is the template for you.

(I'm still a Work In Progress!)

## Features and Benefits

**General**

- [**Webpack.**](https://classic.yarnpkg.com/en/package/webpack) Built on webpack, this template allows for a modern development workflow + a production ready build.
- **Minification.** Complete with webpack's native features and CSSNano, this gets your CSS and JS files smaller than things in 40 degree water.
- [**Prettier.**](https://prettier.io/) An opinionated code formatter. It automagically formats all your code on save so that it always looks the same. This forces everyone's code to look the same, so no more arguing about tabs vs spaces.
- [**BrowserSync.**](https://browsersync.io/) Browsersync synchronises browsers, URLs, interactions and code changes across devices and automatically refreshes all the browsers on all devices on changes. If you have never used this it'll blow your mind.
- [**Sourcemaps.**]() Webpack generates sourcemaps for all js and css files. This helps with debugging simply because when you don't have them enabled your code hides from you like slenderman.
- Configuration. All of the config files have been neatly organized into /webpack to keep them out of the way of the main files. Webpack.config being the exception.

**CSS**

- [**PostCSS.**](http://postcss.org/) PostCSS allows for some code to be injected after the fact, most noteably...
- [**Autoprefixer.**](https://github.com/postcss/autoprefixer) Remember those CSS vendor prefixes you didn't add? Well autoprefixer has you covered.
- [**TailwindCSS.**](https://tailwindcss.com/) Tailwind is the CSS framework all the kids are tweeting about. If you aren't familiar, it basically generates like 4.8 million CSS classes so you never have to write CSS again. And it cleans up after itself, which is nice.
- [**Sass.**](https://webpack.js.org/loaders/sass-loader/) Compiles Sass down into CSS so browsers can read it.

**JS**

- [**BabelJS.**](https://babeljs.io/) Allows you to use next gen Javascript by transpiling it (dumbing it down) to something IE 4 can understand (that claim isn't tested).

## Requirements

- [Node.js](https://docs.npmjs.com/downloading-and-installing-node-js-and-npm)
- [NPM](https://docs.npmjs.com/downloading-and-installing-node-js-and-npm)
- [Yarn](https://classic.yarnpkg.com/en/docs/install/#mac-stable)

---

<img src = "https://i.imgflip.com/5gak9s.jpg" width= 50%; alt = "How do you do fellow coders?">

### Hey.

So this template has 2 major sections, depending on what you need.

---

# Section 1: I Know What I'm Doing.

You've got it then. 

```bash
# 1-- Set up a local instance of Worpress in Local or something.
# 2-- Clone this into your themes folder (as a new theme)

$ git clone https://github.com/Myzwer/Pre-Launch-WP.git

# 2-- Edit the BrowserSync settings in `webpack.config.js`. Ya can't miss it.
# 3-- Install yarn and all the project dependencies

$ yarn install

# 4-- Run a command and start making some magic.
yarn dev
yarn dev:watch
yarn prod
yarn prod:watch
```

# Section 2: Lol I have no idea what I'm doing.

Good. You're like me. This guide aims to be pretty extensive, so buckle up. Some of this might already be up and running on your machine, and that's great, but this guide assumes you are starting from scratch. If you haven't gathered it already, I have a pretty unique sense of humor, but hopefully it makes this more fun to read. Or maybe Comedy Central will give me a call if this doesn't work out.

Couple Notes before we start:

- I am developing on a MacBook Pro running Catalina. If you are developing on a mac, everything should be the same, but Windows users might have other issues. At this time I do not have the bandwidth to check for issues / incompatibilities on windows. Sorry. :(
- If the rest of this seems hella incomplete, it probably is. I am currently pushing new commits pretty frequently, and so guides will come with that.
- While the aim of this guide is to help users get set up as much as possible, I am not going to cover how to build out a complete theme in WordPress. The goal is to get you from 0 to a working template, then run on your own.

Nothing yet. Sorry if you found this already. Lotta hype for nothing.
Things I plan to Cover:

- Yarn
- NPM
- Webpack
- Node JS
- Xcode
- Iterm
- PHPStorm
- Local by FW

---

- Dart Sass
- Babel
- Browsersync
- TailwindCSS
- Mini CSS extractor
- PostCSS
- PostCSS preset env
- ESlint
- StylelintCSS
- Url Loader
- File Loader

---

- Different Commands (yarn run)
- Prod / Dev
- What all the files do
- Adding Custom Colors in TailwindCSS
- Preflight specifics
- Add fonts (custom + google)
- Stylelint Settings

### How To Add Fonts To Your Project
#### Google Fonts
1. Go to https://fonts.google.com/
2. Pick a font family that you like, and select a few styles. (as a note, the more files you choose the slower the site will be. So only pick ones you need to use)
3. Under "use on the web" section, make sure < link > is selected, and look at the code that is generated. It should look _something_ like this: 
``<link rel="preconnect" href="https://fonts.googleapis.com">
   <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
   <link href="https://fonts.googleapis.com/css2?family=Roboto:ital,wght@0,400;0,500;0,700;1,400&display=swap" rel="stylesheet">``
4. Copy the link from the 3rd block, minus the &display=swap. In the example above, it would be this:
```css
https://fonts.googleapis.com/css2?family=Roboto:ital,wght@0,400;0,500;0,700;1,400
```
5. Navigate to functions.php, specifically the fonts part.
6. Wrap your code in the wp function:
```php
wp_register_style( 'FONTNAME_font', 'FONTLINK' );
wp_enqueue_style('FONTNAME_font');
```
7. Name it whatever where FONTNAME_font is (it doesn't matter what you call it, but it does make sense to name it the fontname for ease of reference later), and add the link to FONTLINK. So to complete our example:
```php
wp_register_style( 'roboto_font', 'https://fonts.googleapis.com/css2?familY=Roboto:ital,wght@0,400;0,500;0,700;1,400' );
wp_enqueue_style('roboto_font');
```
8. Go back to google, copy the font family section and you can begin using it in your CSS!
9. (optional) If you are still using tailwind, go into tailwind.config.js and update the fontFamily section. 
```css
fontFamily: {
       'myfontname': ['Roboto', 'sans-serif'], // text-roboto
      }
  ```
---
#### Custom Fonts
1. Purchase or download font files. They will most likely come as .otf or .ttf or something like that. It doesn't matter which you use. 
2. Go to [Transfonter](https://transfonter.org/) and select the fontses you want to include. The more files you include the slower your website will be, so only get the ones you need. 
3. Upload the font files to the site.
4. You do not need to adjust any settings on the bottom section unless you want to.
5. Download your @font-face kit zip file with new fonts!
6. Upzip. ;)
7. You don't need demo.html, though can see what your fonts looks like on a page if you load it up. 
8. Copy all .woff and .woff2 files into ./assets/src/webfonts in the wordpress project. You can delete any existing files that you no longer need including 'hello.txt'.
9. Open up stylesheet.css, copy all the code out of it, and paste that into fonts.css. (.assets/src/sass/fonts/)
10. Lastly, you'll need to tell your fonts where they can find the woff files. This means adding ``../../webfonts/`` to the beginnging of all of your URL's.
```css
font-family: "MYFONT";
  src: url("../../webfonts/MYFONT.woff2") format("woff2"),
    url("../../webfonts/MYFONT.woff") format("woff");
  font-weight: 900;
  font-style: normal;
  font-display: swap;
```
11. Once added, if you have prettier and stylelint up and running, both of those will throw errors, so hop over to iterm and type ``yarn stylelint`` to get it fixed. 
12. Once linked like this, you are free to use your new font families! The name is whatever fontfamily is called. In the above example (where I showed linking) MYFONT would be the name you'd use. 