# hexify

> **Deprecated:** This library is no longer maintained. Use the built-in alternatives below instead.

## Alternatives

### Node.js (recommended)

Use the built-in `Buffer` class:

```javascript
// Hex string → bytes
Buffer.from('00ff6c0a', 'hex');  // <Buffer 00 ff 6c 0a>

// Bytes → hex string
Buffer.from([0x00, 0xff, 0x6c, 0x0a]).toString('hex');  // '00ff6c0a'
```

### Browser / Universal

Pure JavaScript one-liners that work everywhere:

```javascript
// Hex string → Uint8Array
const toByteArray = (hex) =>
  new Uint8Array(hex.match(/.{1,2}/g)?.map(b => parseInt(b, 16)) ?? []);

// Uint8Array → hex string
const toHexString = (bytes) =>
  [...bytes].map(b => b.toString(16).padStart(2, '0')).join('');
```

---

## Legacy Usage

If you're still using this library:

```javascript
hexify.toHexString([0x00, 0xFF, 0x6C, 0x0A]) === '00ff6c0a'
hexify.toByteArray('00ff6c0a') // [0x00, 0xFF, 0x6C, 0x0A]
```

## License

ISC



