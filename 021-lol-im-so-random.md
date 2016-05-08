# lol im so random

Mark Wunsch

`Math.random()` exists in both Java and Javascript. How do we teach a computer to flip a coin?

In 1955 the RAND corporation published a book called "a million random digits".

"There is no such thing as random numbers" - John Von Neumann. Computer's cannot generate a truly random sequence because computers do math; the output of a given function is deterministic. So we use pseudo-random numbers, which are mathematical functions with apparently random outputs (but they are not truly random).

PRNGs are seeded; based on the seed, the output of the PRNG is determined. A PRNG is a state machine; every time you call `generate()` on it, it advances some determinable internal state.

An application of this is property-based testing such as quickcheck.

PRNG algorithms. The Mersenne Twister is a popular PRNG algorithm; it's a twisted linear feedback shift register. A Mersenne Prime is a prime number one less than a power of 2. The _period_ of a PRNG is how long it can produce numbers before the sequence starts to repeat itself.

The balancing act of a PRNG is:
* Period length
* Quality of randomness
* Generation speed

Note that PRNGs are not suited for cryptographic purposes.

What does it mean for a PRNG to be cryptographically secure?

In cryptographic applications, you want the next return value from `generate` to be hard to predict based on the previous one. A cryptographically secure random number generator heavily emphasizes this property.

A CSPRNG will periodically reseed itself, for example, using an entropy pool. 
