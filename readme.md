# term-img [![Build Status](https://travis-ci.org/sindresorhus/term-img.svg?branch=master)](https://travis-ci.org/sindresorhus/term-img)

> Display images in your terminal

![](screenshot.jpg)

Even [animated gifs](https://github.com/vdemedes/gifi)!

*Currently only supported on iTerm >=2.9.*


## Install

```
$ npm install --save term-img
```


## Usage

```js
const termImg = require('term-img');

termImg('unicorn.jpg').catch(err => {
	if (err.name === 'TermImgNotSupported') {
		// implement fallback for terminals not supporting the image escape
		fallback();
		return;
	}

	throw err;
});
```


## API

### termImg(input, [options])

Returns a promise.

#### input

Type: `string` `buffer`

Filepath to an image or an image as a buffer.

#### options

##### width
##### height

Type: `string` `number`

The width and height are given as a number followed by a unit, or the word "auto".

- `N`: N character cells.
- `Npx`: N pixels.
- `N%`: N percent of the session's width or height.
- `auto`: The image's inherent size will be used to determine an appropriate dimension.

##### preserveAspectRatio

Type: `boolean`<br>
Default: `true`


## License

MIT © [Sindre Sorhus](https://sindresorhus.com)