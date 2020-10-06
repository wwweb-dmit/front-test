# Webpack 4 Configuration

This is a `webpack 4` configuration based on @dvlden, @marharyta and @damonbauer work.
I use it on small projects when I am not using Symfony or React and I need a "simple" compilation flow with a module bundler.


## Technologies

> Here is a quick list of the main packages used : 

- Webpack 4 (Module Bundler)
- Babel (Js Compiler)
  - Preset Env
- Postcss (convert css for older browsers and future features)
  - [Preset Env](https://preset-env.cssdb.org/) instead of [cssnext](https://moox.io/blog/deprecating-cssnext/)
- Sass 
- [BrowserSync](https://www.browsersync.io/) with Webpack Dev Server
- _Optional_ : jQuery (Used to display how modules work, not mandatory)




## Configuration


> Common for development & production environment

- it accepts two entry points; one for the `app` and one for the `vendor`
- it compiles `sass/scss` to the `css` file
- it is using postcss-preset-env so you can use new css features no supported yet (see [cssdb](https://cssdb.org/))
- it compiles `es6` to the syntax that every browser can understand
- it has alias as `~` for importing your `js` files, no more mess with directory back-levels


> Development environment

- it runs webpack-dev-server with browser-sync support
- it builds source-maps


> Production environment

- it copies html files to dist folder and injects the right css and js files
- it minifies `js`
- it minifies multiple image types _(gif, png, jpg, jpeg, svg)_
- it copies all `web fonts`
- it has subresource-integrity
- it does not build source-maps, but you may specify it on line `211` if you want them
- it hashes js and css name files to avoid cache problem


## How to use it 

- `npm install` - to install all dependencies for your local project
- `npm run dev` – to start developping
- `npm run build` - to package your application on production (dist folder)
