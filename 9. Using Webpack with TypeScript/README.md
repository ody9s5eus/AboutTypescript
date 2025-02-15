# Using Webpack with TypeScript

tags: #TypeScript #Webpack 

---

## **1. What is Webpack and Why Do We Need It?**
Webpack is a module bundler for JavaScript applications. It helps in managing dependencies and optimizing code for production.

---

## **2. Installing Webpack and Dependencies**

Install Webpack and necessary dependencies:
```sh
npm install --save-dev webpack webpack-cli
```

---

## **3. Adding Entry & Output Configurations**

Create a `webpack.config.js` file:
```js
const path = require('path');

module.exports = {
  entry: './src/index.ts',
  output: {
    filename: 'bundle.js',
    path: path.resolve(__dirname, 'dist'),
  },
  resolve: {
    extensions: ['.ts', '.js'],
  },
};
```

---

## **4. Adding TypeScript Support with ts-loader Package**

Install `ts-loader` and TypeScript:
```sh
npm install --save-dev ts-loader typescript
```

Update `webpack.config.js`:
```js
module.exports = {
  module: {
    rules: [
      {
        test: /\.ts$/,
        use: 'ts-loader',
        exclude: /node_modules/,
      },
    ],
  },
};
```

---

## **5. Finishing Setup and Adding Webpack Dev Server**

Install Webpack Dev Server:
```sh
npm install --save-dev webpack-dev-server
```

Update `webpack.config.js`:
```js
module.exports = {
  devServer: {
    contentBase: './dist',
    port: 3000,
  },
};
```

Run the development server:
```sh
npx webpack serve
```

---

## **6. Adding a Production Workflow**

Optimize Webpack for production:
```sh
npm install --save-dev terser-webpack-plugin
```

Update `webpack.config.js`:
```js
const TerserPlugin = require('terser-webpack-plugin');
module.exports = {
  mode: 'production',
  optimization: {
    minimize: true,
    minimizer: [new TerserPlugin()],
  },
};
```

Now, build the project:
```sh
npx webpack --mode production
```

---

This completes the Webpack setup for TypeScript! 🚀
