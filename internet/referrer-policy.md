Today I learned that sites can use the [`Referrer-Policy`
header](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Referrer-Policy)
to tell browsers what parts of the URL should be transmittel to other
pages as a referrer header. By default they strip off parameters (except
if the header value is `unsafe-url`), but they can also strip off pages or
the whole header, based on the origin of tha page and if the protocol is
SSL or not.

Unsupported By IE, fallback values not supported by Safari
