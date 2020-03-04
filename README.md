# Tailwind CSS & create-react-app setup

## `Steps for the setup`

- ▶️ Step 1

  Install the list of development dependency packages

  - tailwindcss
  - postcss-cli
  - concurrently
  - autoprefixer

```
npm i -D tailwindcss postcss-cli autoprefixer concurrently
```

- ▶️ Setp 2

create tailwind config file

```
npx tailwind init tailwind.js --full
```

- ▶️ Step 3
  create postcss config file in the root directory

  `postcss.config.js`

  inside the `postcss.config.js`

```
const tailwindcss = require('tailwindcss');
module.exports = {
  plugins: [
    tailwindcss('./tailwind.js'),
    require('autoprefixer')
    ]
};
```

- ▶️ Step 4
  make changes to the `package.json` scripts to

```
"scripts": {
   "start": "concurrently \"npm run watch:css\" \"react-scripts start\"",
   "build": "npm run build:css && react-scripts build",
   "test": "react-scripts test",
   "eject": "react-scripts eject",
   "watch:css": "postcss src/tailwind.css -o src/index.css -w",
   "build:css": "postcss src/tailwind.css -o src/index.css"
 }
```

## To Run the Dev Server

```
npm start
```

To Build

```
npm run build
```

Made with ❤️
