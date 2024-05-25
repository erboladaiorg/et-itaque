# @erboladaiorg/et-itaque
### A JavaScript wrapper for Microsoft's [Fluent Emojis](https://github.com/microsoft/fluentui-emoji).

<a href="https://www.npmjs.com/package/@erboladaiorg/et-itaque" target="_blank">NPM</a> | 
<a href="https://github.com/erboladaiorg/et-itaque" target="_blank">Github</a> | 
<a href="/@erboladaiorg/et-itaque/demo" target="_blank">Live Demo</a>

## Install
```bash
npm install @erboladaiorg/et-itaque
```

## Usage
### Common JS
```js
const emoji = require('@erboladaiorg/et-itaque')

emoji.fromGlyph('👋','3D').then((emojiFile) => {
  console.log(emojiFile)
})
```

### ES Module
```js
import * as emoji from '@erboladaiorg/et-itaque'

const emojiFile = await emoji.fromGlyph('👋','3D')
console.log(emojiFile)
```

### Displaying the emoji
Both `fromGlyph(glyph, style)` and `fromCode(code, style)` return the location of the emoji image relative to the base emoji folder. You can download the assets folder from the [fluentui-emoji repo](https://github.com/microsoft/fluentui-emoji) or use a service like [jsdelivr](https://jsdelivr.com) to get the emoji image.

#### Getting emoji image via jsdelivr
```js
const emojiImage = document.querySelector('#emojiImage');
const emoji = '🍕';

emoji.fromGlyph(emoji,'3D').then((emojiFile) => {
  emojiImage.src = `https://cdn.jsdelivr.net/gh/microsoft/fluentui-emoji@latest/assets${emojiFile}`
})
```

### More Info
@erboladaiorg/et-itaque has 2 main functions `fromGlyph(glyph, style)` and `fromCode(code, style)`. Both return the location of the emoji image relative to the base emoji folder.

`fromGlyph(glyph, style)`
- `glyph`: string contaning an emoji
- `style`: string `'3D'`, `'Color'`, `'Flat'`, or `'High Contrast'`

`fromCode(code, style)`
- `code`: string contaning the unicode for an emoji
  - `code` should be just the hexcode. ex.`'1f44b'` not `'U+1F44B'`
- `style`: string `'3D'`, `'Color'`, `'Flat'`, or `'High Contrast'`
