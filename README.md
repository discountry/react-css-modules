# React CSS Modules

## 改动部分

### webpack.config.dev.js

```js
// 183
{
  loader: require.resolve('css-loader'),
  options: {
    importLoaders: 1,
    modules: true,
    localIdentName: '[path][name]__[local]--[hash:base64:5]'
  },
},
// 192
```

### webpack.config.prod.js

```js
// 183
{
  loader: require.resolve('css-loader'),
  options: {
    importLoaders: 1,
    modules: true,
    localIdentName: '[path][name]__[local]--[hash:base64:5]'
    minimize: true,
    sourceMap: true,
  },
},
// 193
```

### App.js

```js
import styles from './App.css';

class App extends Component {
  render() {
    return (
      <div className={styles['App']}>
        <div className={styles['App-header']}>
          <img src={logo} className={styles['App-logo']} alt="logo" />
          <h2>Welcome to React</h2>
        </div>
        <p className={styles['App-intro']}>
          To get started, edit <code>src/App.js</code> and save to reload.
        </p>
      </div>
    );
  }
}
```