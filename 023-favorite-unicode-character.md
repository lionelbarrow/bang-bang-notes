### My Favorite Unicode Character

_Anne DeCusatis_

Definitions:
* Character - Unicode code point
* Glyph - appearance of a character on the page

Zero-width-joiner -- control character that joins things.

Before computers, had typewriters. ASCII came next, but it only had English characters. People worked around this by ignoring accents and such. EBCDIC was introduced by IBM and it could maybe handle Italian. Still there wasn't one universal standard. Then, Unicode happened! Unicode is a single standard for using multiple code planes at the same time.

To handle overlapping characters, use a ZWJ. There's also a zero-width-non-joiner, which forcibly separates characters that might automatically be joined.

The emoji "couple with heart, woman woman" is a woman, ZWJ, heart, ZWJ, woman.

In Python, `len(couple with heart woman woman)` is either 20 or 6 characters depending on your version of Python (there's an additional code point on the heart to select the emoji display style).

In Java, `"couple with heart woman woman.length()` returns 8. But `couple with hearth woman woman.codePointCount()` is 6 as "expected".

When writing programs that take user input, thing carefully about Unicode. We want to write apps that work for everyone in the world, not just people who speak English.
