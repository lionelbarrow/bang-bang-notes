# Sorting is as easy as 1, 2, 3 -- but not as easy as a, b, c

Jake Levine

Last year, Meetup added support for Japanese! When a user signs up for Meetup, they're presented with a list of categories that they're interested in. But when this list was translated to Japanese, it wasn't sorted anymore. What gives?

Sorting Integers is pretty easy. But is sorting Strings? Java doesn't correct sort words of multiple case correctly if you use the `Collections.sort` method. However, Java has a `Collator` class which can, in theory, correctly sort in a locale-sensitive way.

```java
Collator c = Collator.getInstance(new Locale("en", "US"));
result = Colections.sort(names, c);
```

This works! But for Japanese words it still doesn't work. It turns out Japenese has 4 alphabets: kanji plus 3 phoenetic alphabets, which were all used in the dataset. Sorting Japanese words depends on the pheonetic pronunciation, which is context dependent. Thus, Japanese cannot be sorted on a word by word basis without more context.

An analogy: in English, if "I would like to READ a book" was sorted from "Have you READ this book". To solve this problem, translate the kanji to phoenetic alphabet (a human process), sort by the phoenetic calendars, but then continue to display the kanji. This didn't fully solve the problem but it's a step in the right direction.

The truly correct solution is to avoid using the text in this way. Developing global products is much harder than expected, and language is hard.
