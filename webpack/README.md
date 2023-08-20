1. Create a new npm project with npm init -y
2. Install webpack and its server/cli with `npm install webpack webpack-cli webpack-dev-server -D`
   - Also add `tailwindcss ts-loader autoprefixer style-loader css-loader postcss postcss-loader postcss-preset-env` if starting a standard project
3. Remove the main key, and add "private": true unless you're planning on developing an npm package.
4. Add my usual custom scripts to package.json

```
"build": "export NODE_ENV=production && webpack",
"dev": "NODE_ENV=development webpack serve --open",
"pages": "git subtree push --prefix dist origin gh-pages"
```

5. Add [webpack.config.js](./webpack.config.js), [postcss.config.js](./postcss.config.js) and [tsconfig.json](./tsconfig.json) then run `npx tailwindcss init` to create [tailwind.config.js](./tailwind.config.js)
   - Don't forget to replace the purge array with a content array, as that's now where it looks for content
6. Finally, add the tailwind declarations to your main CSS file and remember to import it in at least one of your .ts files or webpack won't bundle it.

```
@tailwind base;
@tailwind components;
@tailwind utilities;
```
