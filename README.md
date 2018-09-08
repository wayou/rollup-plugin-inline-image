# rollup-plugin-inline-image

[![npm package](https://img.shields.io/npm/v/rollup-plugin-inline-image.svg)](https://www.npmjs.com/package/rollup-plugin-inline-image)
[![npm package](https://img.shields.io/npm/dt/rollup-plugin-inline-image.svg)](https://www.npmjs.com/package/rollup-plugin-inline-image)


inline JPG, PNG, GIF and SVG images into rollup bundle.

**Same as [rollup/rollup-plugin-image](https://github.com/rollup/rollup-plugin-image) but the ouput of rollup-plugin-image is module code witch won't work in umd format. This fork ouput plain string code which can be transformed by Typescript or babel and available in umd format.**

## Installation

```bash
npm install --save-dev rollup-plugin-inline-image
```


## Usage

```js
// rollup.config.js
import image from 'rollup-plugin-inline-image';

export default {
  entry: 'src/index.js',
  dest: 'dist/my-lib.js',
  plugins: [
    image()
  ]
};
```

You can now use images in your bundle like so:

```js
import logo from './rollup.png';
document.body.appendChild( logo );
```

Images are encoded using base64, which means they will be 33% larger than the size on disk. You should therefore only use this for small images where the convenience of having them available on startup (e.g. rendering immediately to a canvas without co-ordinating asynchronous loading of several images) outweighs the cost.


## License

MIT
