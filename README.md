# UTF-7

Encodes and decodes JavaScript (Unicode/UCS-2) strings to UTF-7 ASCII strings. It supports two modes: UTF-7 as defined in [RFC 2152](http://tools.ietf.org/html/rfc2152) and Modified UTF-7 as defined by the IMAP standard in [RFC 3501, section 5.1.3](http://tools.ietf.org/html/rfc3501#section-5.1.3)

## Usage

**RFC 2152**

```javascript
var utf7 = require('utf7');

var encoded = utf7.encode('Jyväskylä');
assert.equal('Jyv+AOQ-skyl+AOQ-', encoded);

var decoded = utf7.decode(encoded);
assert.equal('Jyväskylä', decoded);
```

**IMAP (RFC 3501)**

```javascript
var utf7 = require('utf7').imap;

var encoded = utf7.encode('"你好" heißt "Hallo"');
assert.equal('"&T2BZfQ-" hei&AN8-t "Hallo"', encoded);

var decoded = utf7.decode(encoded);
assert.equal('"你好" heißt "Hallo"', decoded);
```
