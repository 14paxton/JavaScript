## Leave only Alpha Chars and remove space

```javascript
 const removeSpecialChar = /[^a-zA-Z\d ]/g
const replaceSpace = /\s/g
const onlyAlpha = (fileName
                   ? fileName
                   : title).replaceAll(removeSpecialChar, '')
const strippedFName = onlyAlpha.replaceAll(replaceSpace, '_')
```
