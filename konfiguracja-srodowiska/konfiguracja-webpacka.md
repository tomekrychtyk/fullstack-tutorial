# Konfiguracja Webpacka

Webpack posiada mnóstwo możliwości konfiguracyjnych, jednak wszystkie są bardzo dobrze udokumentowane. Jak wspomniałem na wstępie, chcę, aby ten tutorial był maksymalnie praktyczny więc poniżej przedstawię po prostu wstępną konfigurację dla naszego projektu, a zainteresowanych tematem odsyłam do [**dokumentacji**](https://webpack.js.org/configuration/), gdzie można znaleźć dużo teorii. Jeszcze raz podkreślę - ja w tym kursie będę się skupiał bardziej na pokazaniu, jak użyć tej teorii \(oczywiście nie dotyczy to tylko Webpacka\).

Generalnie konfigurację dzielę na trzy pliki: **webpack.common.js**, **webpack.prod.js** oraz **webpack.dev.js**. Myślę, że jest dość jasne do czego będą one służyć:

* webpack.prod.js - będzie zawierać konfigurację odpowiedzialną za wygenerowanie paczki wynikowej, gotowej do podpięcia na produkcji
* webpack.dev.js - będzie zawierać konfigurację środowiska developerskiego
* webpack.common.js - będzie zawierać konfigurację wspólną dla obu wspomnianych środowisk

{% code-tabs %}
{% code-tabs-item title="webpack.common.js" %}
```javascript
const path = require('path');
const CleanWebpackPlugin = require('clean-webpack-plugin');
const HtmlWebpackPlugin = require('html-webpack-plugin');

module.exports = {
  entry: {
    app: './src/index.js',
  },

  module: {
    rules: [
      {
        test: /\.js$/,
        exclude: /node_modules/,
        use: {
          loader: 'babel-loader',
        },
      },
      {
        test: /\.html$/,
        use: [
          {
            loader: 'html-loader',
          },
        ],
      },
      {
        test: /\.css$/,
        use: [
          {
            loader: 'style-loader',
          },
          {
            loader: 'css-loader',
          },
        ],
      },
    ],
  },

  plugins: [
    new CleanWebpackPlugin(['dist']),
    new HtmlWebpackPlugin({
      title: 'FullStack Unsplashed',
      template: './src/index.html',
      filename: './index.html',
    }),
  ],

  output: {
    publicPath: '/',
    filename: '[name].bundle.js',
    path: path.resolve(__dirname, 'dist'),
  },
};

```
{% endcode-tabs-item %}
{% endcode-tabs %}

{% code-tabs %}
{% code-tabs-item title="webpack.dev.js" %}
```javascript
const { BundleAnalyzerPlugin } = require('webpack-bundle-analyzer');
const merge = require('webpack-merge');
const common = require('./webpack.common.js');

module.exports = merge(common, {
  mode: 'development',
  devtool: 'inline-source-map',
  devServer: {
    contentBase: './dist',
    historyApiFallback: true,
  },
  plugins: [new BundleAnalyzerPlugin()],
});


```
{% endcode-tabs-item %}
{% endcode-tabs %}

{% code-tabs %}
{% code-tabs-item title="webpack.prod.js" %}
```javascript
const merge = require('webpack-merge');
const common = require('./webpack.common');

module.exports = merge(common, {
  mode: 'production',

  optimization: {
    splitChunks: {
      chunks: 'all',
    },
  },
});


```
{% endcode-tabs-item %}
{% endcode-tabs %}

