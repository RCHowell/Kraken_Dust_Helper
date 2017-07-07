# Kraken.js Dust Helper Tutorial

Version 2.0 of Kraken changes how one should write dust helpers. This short tutorial will include an example helper and how to configure helpers.

[Helper API](http://www.dustjs.com/docs/helper-api/)

## Requirements
dustjs-helpers

## Creation

**helper-shout.js**
```javascript
let dust = require('dustjs-helpers');

dust.helpers.shout = (chunk, context, bodies, params) => {

    // All helper code goes here. See: http://www.dustjs.com/docs/helper-api/

    return chunk.write(params.text.toUpperCase();

}
```


**./config/config.json**
```javascript

// more config

// Be sure to set the full path to your custom helper.
// This is written as if 'helper-shout.js' were in the root directory

"dust": {
    "helpers": [
        "dustjs-helpers",
        "./helper-shout.js"
    ]
},


// more config

```

## Usage

**template**
```dust
<h1>{@shout text="{key}"}</h1>
```

**data**
```javascript
{
    "key": "value"
}
```

**result**
```html
<h1>VALUE</h1>
```
