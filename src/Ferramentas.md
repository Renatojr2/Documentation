# Ferramentas por trás do React

 ## Babel
      * Converter (Traspilar) o código do react para um código que o browser entenda

## babel.config.js

```javascript
module.exports = {
  presets: [ 
    '@babel/preset-env',
    '@babel/preset-react'
  ]
}
```

### @babel/preset-env
    * Ele entende o ambiente que a aplicação está executando e converterá seu código baseado apenas naquele ambiente.

### @babel/preset-react
    * Adiciona as funcionalidades do react na conversão do codigo


  ## Webpack
    * Para cada tipo de arquivo (.js, .css, .png) eu vou converter o código de uma maneira diferente

    * Loader- babel-loader, css-loader, image-loader...

    
## webpack.config.js

```javascript
const path = require('path')

module.exports = {
  //arquivo de entrada da nossa aplicação
  entry: path.resolve(__dirname, 'src', 'index.js'),
  //o arquivo que será gerado depois de convertido
  output: {
    path: path.resolve(__dirname, 'public'),
    filename: 'bundle.js'
  },
  devServer: {
    contentBase: path.resolve(__dirname, 'public')
  },

  // regras
  module: {
    rules: [
      {
        test: /\.js$/,
        exclude: /node_modules/,
        use: {
          loader: 'babel-loader'
        }
      }
    ]
    
  } 
}
```