# Bloom Filter

It's a data structure mainly used to verify if a given piece of data is not present. In this data structure there are false positives, but no false negatives. That is, the data might be there or definitely is not there.

A bloom filter begins with an bit array with all values set to 0. Whenever data is inserted it will be hashed by one or more (deterministic) hash functions. The function returns a number that will be used to access and set the array's index value to 1.

The quantity of hash functions will decrease the chance of false positive.

It's not recommended to remove elements from a bloom filter because you can't be sure if it's the element you want or false positive.

An example to make things more clear:

Let's say you have a database table with seats for a game. You don't want to query the database just to know if the seat is free. If it's free, you want a fast response.

So you create a bloom filter and an algorithm to return the corresponding index for the seat.

The bloom filter will be an bit array of size 5 (it should be bigger, this is just for the sake of example)

0 0 0 0 0 (an array of size 5, filled with 0s)

User A wants to buy the seat 10 in row 20. You pass to your hash function the string "1020" and it returns the numbers 1 and 3.

These numbers will be used to access the array element and set it to 1.

0 1 0 1 0 (changed values of index 1 and 3)

User B tries to buy the same seat a few seconds later. The same value is passed to the hash function and 1 and 3 are returned. When you check your array you see that those indexes are set to 1 meaning this seat is taken. You return an error to the client.

Observation: remember that the only assurance bloom filter gives is that the data is not present. In the above example, depending on the hash function, another seat could return 1 and 3 (false positive). But never there will be a false negative. So we will always be sure that the seat is free (that is, at least one index set to 0).