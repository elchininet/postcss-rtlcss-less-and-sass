# Webpack configurations to use postcss-rtlcss plugin with Less and Sass

These are minimum Webpack configurations to use [postcss-rtlcss plugin](https://github.com/elchininet/postcss-rtlcss) with [Less](https://lesscss.org/) and [Sass](https://sass-lang.com/)


### Using Less

```javascript
const postcssRTLCSS = require('postcss-rtlcss');

module.exports = {
    ... // other webpack configurations
    module: {
        rules: [
            {
                test: /\.less$/,
                use: [
                    ... // other loaders
                    {
                        loader: 'postcss-loader',
                        options: {
                            postcssOptions: {
                                plugins: [
                                    postcssRTLCSS()
                                ]
                            }
                        }
                    },
                    // Less loader must come before postcss-loader
                    'less-loader'
                ]
            }
        ]
    }
};
```

### Using Sass

```javascript
const postcssRTLCSS = require('postcss-rtlcss');

module.exports = {
    ... // other webpack configurations
    module: {
        rules: [
            {
                test: /\.s(c|a)ss$/,
                use: [
                    ... // other loaders
                    {
                        loader: 'postcss-loader',
                        options: {
                            postcssOptions: {
                                plugins: [
                                    postcssRTLCSS()
                                ]
                            }
                        }
                    },
                    // Sass loader must come before postcss-loader
                    'sass-loader'
                ]
            }
        ]
    }
};
```
