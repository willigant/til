ECMAScript 6 has a feature called Template Strings. Basically, it allows

```
`foo ${bar} string`
```

to be used instead of 

```js
'foo' + bar + 'string'
``` 
concatenation.

It also allows for multi-line strings in javascript without escaping, which is great for templates:
```
return `
    <div class="${foo}">
         ...
    </div>
`;
```

source: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Template_literals
