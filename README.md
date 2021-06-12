# mybulma-template

<a href="https://bulma.io">
  <img
    src="https://bulma.io/images/made-with-bulma.png"
    alt="Made with Bulma"
    width="128"
    height="24">
</a>

## Customize bulma for Javascript apps.

### Either use the default `scss` variables Bulma provides along with `node-sass` or apply your own branding for extra flair.

---

You only need 2 packages to customize Bulma: `node-sass` and `bulma` itself.

> Start by installing the dependencies--

```bash
npm install
```

To build a CSS file from a Sass file, we can use node scripts. In package.json, we have added the following:

```json
"scripts": {
  "css-build": "node-sass --omit-source-map-url sass/mystyles.scss css/mystyles.css",
  "css-watch": "npm run css-build -- --watch",
  "start": "npm run css-watch"
}
```

* `css-build` takes `sass/mystyles.scss` as an input, and outputs `css/mystyles.css`, while omitting the source map
* `css-watch` builds the CSS and watches for changes
* `start` is simply a shortcut for `css-watch`

To test it out, go in your terminal and run the following command:

```bash
npm run css-build
```

If set up correctly, you will see the following message:

```bash
Rendering Complete, saving .css file...
Wrote CSS to /path/to/mybulma/css/mystyles.css
```

Reload the page and it should be styled with Bulma's default styles.

> Replace the content of the `mystyles.scss` file with the following:

```scss
@charset "utf-8";

// Import a Google Font
@import url('https://fonts.googleapis.com/css?family=Nunito:400,700');

// Set your brand colors
$purple: #8A4D76;
$pink: #FA7C91;
$brown: #757763;
$beige-light: #D0D1CD;
$beige-lighter: #EFF0EB;

// Update Bulma's global variables
$family-sans-serif: "Nunito", sans-serif;
$grey-dark: $brown;
$grey-light: $beige-light;
$primary: $purple;
$link: $pink;
$widescreen-enabled: false;
$fullhd-enabled: false;

// Update some of Bulma's component variables
$body-background-color: $beige-lighter;
$control-border-width: 2px;
$input-border-color: transparent;
$input-shadow: none;

// Import only what you need from Bulma
@import "../node_modules/bulma/sass/utilities/_all.sass";
@import "../node_modules/bulma/sass/base/_all.sass";
@import "../node_modules/bulma/sass/elements/button.sass";
@import "../node_modules/bulma/sass/elements/container.sass";
@import "../node_modules/bulma/sass/elements/title.sass";
@import "../node_modules/bulma/sass/form/_all.sass";
@import "../node_modules/bulma/sass/components/navbar.sass";
@import "../node_modules/bulma/sass/layout/hero.sass";
@import "../node_modules/bulma/sass/layout/section.sass";
```

Since you are watching for changes, simply save the file to see the result, which should represent your changes.

> Voila!

This page is [Open Source](https://creativecommons.org/licenses/by-nc-sa/4.0/) and derived from Bulma's [comprehensive version](https://bulma.io/documentation/customize/with-node-sass/) of this template.

All credit for the creation of Bulma goes to [Jeremy Thomas](https://twitter.com/jgthms), and all source code is licensed [MIT](https://opensource.org/licenses/mit-license.php).
