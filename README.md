# PyCharm-Vite-Tailwind setup

## Initial setup
1. **PyCharm**: create a new Vite - Vanilla JS project.

```shell
cd pycharm-vite-tailwind-template
npm install
```
* Edit `index.html` to change the name of your app.
```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>My App</title>
  </head>
  <body>
    <div id="app"></div>
    <script type="module" src="/main.js"></script>
  </body>
</html>
```

* Delete `counter.js`, `javascript.svg`, and `./public/vite.svg`.
* Empty the contents of `style.css`.
* Edit `main.js` to keep only the bare bones.
```javascript
import './style.css'


function ui(divID) {
    let divUI = divID ? document.getElementById(divID) : document.createElement('div');

    // <h1 class="text-3xl font-bold underline"> Hello world! </h1>
    let h1 = document.createElement('h1');
    h1.innerHTML = 'Hello world!';
    h1.className = 'text-3xl font-bold underline';

    divUI.appendChild(h1);
}


ui('app');
```

2. **Tailwind CSS**: follow instructions at https://tailwindcss.com/docs/installation/using-postcss

* Install Tailwind CSS and its dependencies (PostCSS and Autoprefixer):
```shell
npm install -D tailwindcss postcss autoprefixer
```
* Generate the `tailwind.config.js` and `postcss.config.js` configuration files:
```shell
npx tailwindcss init -p
```
* Edit `tailwind.config.js` to tell Tailwind CSS to scan all the HTML and JS files in the root directory for classes to include in the CSS:
```javascript
/** @type {import('tailwindcss').Config} */
export default {
  content: ["./*.{html,js}"],
  theme: {
    extend: {},
  },
  plugins: [],
}
```
**Note**: Be careful as to not scan the `node_modules` and the `dist` directories while setting the `content` property.
* Add tailwind directives to the main CSS file `style.css`:
```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

3. Build using `npm run dev` or according to `package.json`.
```shell
vite
```

## Building the Vite app

## Deploying the Vite app on GitHub Pages


## Hosting JavaScript ESM libraries + web app on GitHub Pages