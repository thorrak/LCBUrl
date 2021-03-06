# LCBUrl - An Arduino library for handling URLs

This library was written by and for a non-programmer.  If you find some use out of it, that will make me happy but if not I'm still using it in my own works.

This library will parse a url, and normalize it according to the information provided in [RFC3986](https://tools.ietf.org/html/rfc3986).  For instance, pass in `http://%7EFoo:%7Ep@$$word@servername.local/%7Ethis/is/a/./path/test.php#frag` and access the hostname, user name, password, path, query string, fragment, etc.

## Public Methods

- `bool setUrl(String)` - Pass the URL to be handled to the class
- `String getUrl()` - Return a processed URI in the following format: `scheme:[//authority]path[?query][#fragment]`
- `String getScheme()` - Get the scheme (currently only handles http and https)
- `String getUserInfo()` - Return username and password (if present)
- `String getUserName()` - Returns username (if present)
- `String getPassword()` - Returns password (if present)
- `String getHost()` - Return host name
- `word getPort()` - Return port (if present) if non-standard
- `String getAuthority()` - Return the authority (if present) in the following format: `[userinfo@]host[:port]`
- `String getPath()` - Returns the path segment (if present) with any query or fragment removed
- `String getAfterPath()` - Returns query and fragment segments (if present)
- `String getQuery()` - Returns query (if present)
- `String getFragment()` - Returns fragment (if present)

## Progress:

- [X] Convert percent-encoded triplets to uppercase
- [X] Convert the scheme and host to lowercase
- [X] Decode percent-encoded triplets of unreserved characters
- [ ] Remove dot-segments
- [X] Convert an empty path to a "/" path
- [X] Remove the default port
- [X] Add a trailing "/" to a non-empty path (may remove this)

## Installation
--------------------------------------------------------------------------------

To install this library, just place this entire folder as a subfolder in your
Arduino/lib/targets/libraries folder.

When installed, this library should look like:

```
Arduino/lib/targets/libraries/LCBUrl                    (this library's folder)
Arduino/lib/targets/libraries/LCBUrl/examples           (the examples in the "open" menu)
Arduino/lib/targets/libraries/LCBUrl/keywords.txt       (the syntax coloring file)
Arduino/lib/targets/libraries/LCBUrl/library.properties (properties of this libraary)
Arduino/lib/targets/libraries/LCBUrl/LICENSE            (the license for this library)
Arduino/lib/targets/libraries/LCBUrl/README.md          (this file)
Arduino/lib/targets/libraries/LCBUrl/src/LCBUrl.cpp     (the library implementation file)
Arduino/lib/targets/libraries/LCBUrl/src/LCBUrl.h       (the library description file)
```

## Building
--------------------------------------------------------------------------------

After this library is installed, you just have to start the Arduino application.
You may see a few warning messages as it's built.

To use this library in a sketch, go to the Sketch | Import Library menu and
select LCBUrl.  This will add a corresponding line to the top of your sketch:
#include <LCBUrl.h>

To stop using this library, delete that line from your sketch.
