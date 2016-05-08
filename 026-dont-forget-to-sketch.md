### Don't forget to sketch

_Adam Marcus_

Often have too much data to study in depth, but want to get some broad sketches of it. Here are two sketching algorithms: the bloom filter and the count min function.

Bloom filter - Is item X in dataset D?

Bloom filter is a bitset plus a collection of hash functions. To insert a new value into the filter, compute the hash for each hash function and set those indices to true. Keep the bitset and repeat as you add elements. Then to check membership, see if all three hash functions on the value return indices that are already true. Note that this condition can be met by chance on elements that were never added to the set.

Thus, bloom filters never have false negatives but can have false positives. How many false positives? Not too many.

Count min - How many of X are in a dataset D?

Again using a collection of N hash functions, this time we have N rows of counters. When we add a value, we increment the counter at each hash location in that hash's respective buckets. To estimate the true count of a value in the dataset, we look at the minimum of the counter values for each hash row on that value.

Thus, we have a risk of overestimating the count, but not under-estimating it. The count will be more accurate for the more common elements in D.

Embrace randomness. By being OK with a bit of randomness, we can create powerful algorithms.
