## Format date with local

```javascript
    const userLocale = navigator.languages && navigator.languages.length
                       ? navigator.languages[0]
                       : navigator.language;
new Date().toLocaleDateString(userLocale)
```
