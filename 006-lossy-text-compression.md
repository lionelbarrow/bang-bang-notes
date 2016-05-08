# Lossy Text Compression, for some reason?

Allison Parrish

Lossy compression: represent values in a small representation with loss of precision.

Any list of values can be represented as the sum of cosine functions at different coefficients (discrete cosine transform). The DST has the same number of coefficients as original values. The trick is that lower frequency components carry more information than higher frequency ones. JPEG compression uses a 2-dimension DCT.

How can we apply this idea to text?

Have to represent text as a number.

First attempt: map each letter to its number in the alphabet. Can compress the text in a lossy way using this technique. This mostly doesn't work.

Second attempt: compress meaning of words. Python library called word2vec created by researchers at Google. word2vec describes a distance function on words -- e.g. 'puppy' is more similar to 'dog' than 'mastadon'. Can also define a distance from an arbitrary point in the vectorspace. So, apply DCT to word2vec'd corpus. This works pretty well.

This likely has no practical applications.
