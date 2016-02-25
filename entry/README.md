# entry points

## webpack.conf.js
this file is where you define your externals, resolutions, and devServer setup

```javascript
var webpack = require('webpack'),
  path = require('path')

module.exports = {
  externals: {
    // Make sure we use Meteor package for jQuery and react
    'jquery': '$'
  },
  devServer: {
    // You can change this to your server IP address to access it remotely
    host: 'localhost'
  },
  resolve: {
    root: path.join(__dirname, '..', 'modules'),
    extensions: ['', '.js', '.jsx', '.json', '.css']
  }
}
```

## ./client/meteor.startup.js or ./server/meteor.startup.js
this file is sent directly to meteor without going through webpack.
you can initialize anything you need before your app starts in this file.

eg. make FlowRouter wait until the routes are loaded to start serving
```javascript
// /entry/client/meteor.startup.js
FlowRouter.wait()

// /modules/routes/index.js
FlowRouter.route('/',{
  action(){
    ... render code here ...
  }
})

FlowRouter.initialize()
```

## ./client/webpack.conf.js or ./server/webpack.conf.js
this file is where you set up the entry point(s) and loaders the meteor app

```javascript
var webpack = require('webpack')

module.exports = {
  entry: './entry',
  module: {
    loaders: [
      { test: /\.jsx?$/, loader: 'babel', query: babelSettings, exclude: /node_modules/ },
      { test: /\.css$/, loader: 'style!css' },
      { test: /\.less$/, loader: 'style!css!less' },
      { test: /\.(png|jpe?g)(\?.*)?$/, loader: 'url?limit=8182' },
      { test: /\.(svg|ttf|woff|eot)(\?.*)?$/, loader: 'file' }
    ]
  }
}
```