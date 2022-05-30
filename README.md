# cordova-plugin-apple-wallet-passes

This plugin provides support for showing Passbook passes to your users and allows them to add it to their native Wallet (regardless of how you create your passes, whether you do it on your own or using any third-party services like [PassSlot](http://www.PassSlot.com))

**NOTE**: This plugin does not allow you to create Passbook passes.

> This is a fork of https://github.com/yinzara/cordova-plugin-passbook in order to integrate it with Ionic Native

## Installation

```
cordova plugin add cordova-plugin-apple-wallet-passes
```

Or the latest (unstable) version:

```
cordova plugin add https://github.com/MrMitch/cordova-plugin-passbook-2
```


## Supported Platforms

- iOS

## Example

### Simple Call

```js
Passbook.downloadPass('https://d.pslot.io/cQY2f', function (pass, added) {
    console.log(pass, added);
    if (!added) {
        alert('Please add the pass');
    }
}, function (error) {
    console.error(error);
});
```

### Adding Headers

```js
var callData =  {
    url:'https://d.pslot.io/cQY2f',
    headers:{ authorization: 'Bearer <token>' },
};

Passbook.downloadPass(callData, function (pass, added) {
    console.log(pass, added);
    if (!added) {
        alert('Please add the pass');
    }
}, function (error) {
    console.error(error);
});
```

### Multiple passes

```js
Passbook.downloadPasses(['https://d.pslot.io/cQY2f', 'https://d.pslot.io/AeY3D'], function (passes, added) {
    console.log(passes, added);
    if (!added) {
        alert('Please add the passes');
    }
}, function (error) {
    console.error(error);
});
```

### Multiple passes with headers

```js
Passbook.downloadPasses({
    urls: ['https://d.pslot.io/cQY2f', 'https://d.pslot.io/AeY3D'],
    headers: { authorization: 'Bearer <token>' },
}, function (passes, added) {
    console.log(passes, added);
    if (!added) {
        alert('Please add the passes');
    }
}, function (error) {
    console.error(error);
});
```

## Documentation

Plugin documentation: [doc/index.md](doc/index.md)


## Creating Passbook Passes
This Plugin was written by [PassSlot](http://www.PassSlot.com).

PassSlot is a Passbook service that makes Passbook usage easy for everybody. It helps you design and distribute mobile passes to all major mobile platforms.
