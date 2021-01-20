# Dependencies Explained

**vue**: The JavaScript framework
**vue-loader**: and **vue-template-compiler**: Used to convert our `*.vue` files into JavaScript
**webpack**: Code bundler
**webpack-cli**: Needed to run Webpack commands
**webpack-dev-server**: Serve our project from a development server
**babel-loader**: Transform our ES6 code into ES5 code
**@babel/core** and **@babel/preset-env**: The add-ons that Babel uses to actually transform the code
**css-loader**: Webpack CSS loader to find where the CSS is in the project
**vue-style-laoder**: Takes the CSS we find from `css-loader` and inject it into our HTML file
**html-webpack-plugin**: Takes our `index.html` file and injects the bundled JS into the head. Then, copy this to the `dist` folder

# Webpack config

Here, we are requiring the external plugins we will use for Webpack

```js
const HTMLWebpackPlugin = require('html-webpack-plugin')
const VueLoaderPlugin = require('vue-laoder/lib/plugin')
```

Then, we are exporting the entire configuration as an object to use externally:

```js
module.exports = {
...
}
```

Webpack needs a place to start (a place to begin sifting through our code). So let's tell it where that is:

```js
module.exports = {
  ...
  entry: './src/main.js',
  ...
}
```

Then, we define which loaders we want to use with certain file types.

```js
module.exports = {
  ...
  module: {
    rules: [
      {
        test: '/.js$/',
        use: 'babel-loader',
      },
      {
        test: '/.vue$/',
        use: 'vue-loader',
      },
      {
        test: '/.css$/',
        use: ['vue-style-loader', 'css-loader'],
      },
    ],
  },
  ...
}
```

Last, we add our plugins, which are tied to the rules we wrote:

```js
module.exports = {
  ...
    plugins: [
    new HTMLWebpackPlugin({
      template: './src/index.html',
    }),
    new VueLoaderPlugin(),
  ],
  ...
}
```

# References

Based off of [this guide](https://www.freecodecamp.org/news/how-to-create-a-vue-js-app-using-single-file-components-without-the-cli-7e73e5b8244f/) by [Brandon](https://www.freecodecamp.org/news/author/brandon/)
