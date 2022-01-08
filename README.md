# 🚀 MY WAY HTML


## INSTALL
```
npm install --save webpack
npm i --save-dev html-webpack-plugin@4
npm install --save-dev style-loader
npm install --save-dev css-loader
npm install --save compile-sass
```


## USING VIM
```
https://github.com/mattn/emmet-vim
https://github.com/cakebaker/scss-syntax.vim 
https://github.com/hail2u/vim-css3-syntax.git
```


## INIT
```
webpack init --template=default
```



## SET IN <webpack.config.js>
```
const HtmlWebpackPlugin = require('html-webpack-plugin');
const path = require('path');
...

  entry: {
    'page1': './src/main1.js',
    'page2': './scr/main2.js',
  },
  output: {
    path: path.resolve(__dirname, "dist"),
    filename: "[name].js"  
  },


  ...
  devServer: {
    open: true,
    host: "localhost",
    hot: true,	                                    //<----- hot reload
    watchFiles: ['./src/*.sass', './src/*.html'],   //<----- watching
  },

  plugins: [
        new HtmlWebpackPlugin({
	    chunks: ['page1'],                         //<---- entry
            template: './src/index1.html',           
            filename: './index1.html',                 //<---- in dist folder           
        }),

        new HtmlWebpackPlugin({
	    chunks: ['page2'],                         //<---- entry
            template: './src/index2.html',           
            filename: './index2.html',                 //<---- in dist            
            favicon: './src/favicon2.ico',
        }),
  ....

  rules: [{
  ....
        test: /\.s[ac]ss$/i,
        use: ["style-loader", "css-loader", "sass-loader"],  //<---- SASS preprocess
      },
  ....
```



## ADD TO SRC/main1.js
```
import "./index1.sass";
```



## AND RUN
```
npx webpack serve   <OR>    npx webpack build
```



## EMMET HINTS
```
https://docs.emmet.io/cheat-sheet/
```


















  





