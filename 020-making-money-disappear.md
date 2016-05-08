# Making Money Disappear With Hash Functions

Brendan Cordy

What is a bitcoin address?

Bitcoin is essentially a gigantic balance sheet. Addresses are the bitcoin equivalent of account numbers. This balance sheet is maintained by a huge anonymous peer to peer network.

Two problems:
* How to stop people from spending other people's money? -> Public Key Cryptography
* How to stop spending the same money simultaneously? -> Bitcoin Mining

Bitcoin addresses are a 25-byte string in base 58. We use 58 to remove ambiguous letters like i and l.

To make an address:
* Get a public key based on an eliptic curve
* Hash the public key
* Base58 and append a checksum

Since we only need a correct public key when spending money, simple to create addresses that don't have a valid public key backing them -- equivalent to an ATM account with no PIN number. Turns out a few bogus addresses have significant amounts of money associated with them.

So why hash? Mostly for compression. Security benefits are negligible. Another question is whether or not the leak of money into unusable addresses is an intentional feature of Bitcoin or an unintended side effect of the protocol.
