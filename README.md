# A tiny sha256 implementation

Written in one rage burst after finding that browsers only provide
promises (the most absurd interface I could think of for such a job,
only a committee or someone insanely obsessed with promises would be
able to come up with that).

Written by reading specs, tested a bit but not much... YMMV.

Speed is decent for my use.

## Interface

     sha256(data) → digest

     let s = sha256();
     s.add(data);
     s.digest() → digest

The returned digest is an `Uint8Array` instance of 32 bytes with a
stapled on addition of a `.hex()` method returning a string.

Input is expected to be a string (converted to utf-8 for hashing) or
an `Uint8Array` object (or anything for which `.forEach` behaves in a
similar way).
