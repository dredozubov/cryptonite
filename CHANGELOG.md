## 0.16

* Fix basepoint for Ed448

* Enable 64-bit Curve25519 implementation

## 0.15

* Fix serialization of DH and ECDH

## 0.14

* Reduce size of SHA3 context instead of allocating all-size fit memory. save
  up to 72 bytes of memory per context for SHA3-512.
* Add a Seed capability to the main DRG, to be able to debug/reproduce randomized program
  where you would want to disable the randomness.
* Add support for Cipher-based Message Authentication Code (CMAC) (Kei Hibino)
* *CHANGE* Change the `SharedKey` for `Crypto.PubKey.DH` and `Crypto.PubKey.ECC.DH`,
  from an Integer newtype to a ScrubbedBytes newtype. Prevent mistake where the
  bytes representation is generated without the right padding (when needed).
* *CHANGE* Keep The field size in bits, in the `Params` in `Crypto.PubKey.DH`,
  moving from 2 elements to 3 elements in the structure.

## 0.13

* *SECURITY* Fix buffer overflow issue in SHA384, copying 16 extra bytes from
  the SHA512 context to the destination memory pointer leading to memory
  corruption, segfault. (Mikael Bung)

## 0.12

* Fix compilation issue with Ed448 on 32 bits machine.

## 0.11

* Truncate hashing correctly for DSA
* Add support for HKDF (RFC 5869)
* Add support for Ed448
* Extends support for Blake2s to 224 bits version.
* Compilation workaround for old distribution (RHEL 4.1)
* Compilation fix for AIX
* Compilation fix with AESNI and ghci compiling C source in a weird order.
* Fix example compilation, typo, and warning

## 0.10

* Add reference implementation of blake2 for non-SSE2 platform
* Add support\_blake2\_sse flag

## 0.9

* Quiet down unused module imports
* Move Curve25519 over to Crypto.Error instead of using Either String.
* Add documentation for ChaChaPoly1305
* Add missing documentation for various modules
* Add a way to create Poly1305 Auth tag.
* Added support for the BLAKE2 family of hash algorithms
* Fix endianness of incrementNonce function for ChaChaPoly1305

## 0.8

* Add support for ChaChaPoly1305 Nonce Increment (John Galt)
* Move repository to the haskell-crypto organisation

## 0.7

* Add PKCS5 / PKCS7 padding and unpadding methods
* Fix ChaChaPoly1305 Decryption
* Add support for BCrypt (Luke Taylor)

## 0.6

* Add ChaChaPoly1305 AE cipher
* Add instructions in README for building on old OSX
* Fix blocking /dev/random Andrey Sverdlichenko

## 0.5

* Fix all strays exports to all be under the cryptonite prefix.

## 0.4

* Add a System DRG that represent a referentially transparent of evaluated bytes
  while using lazy evaluation for future entropy values.

## 0.3

* Allow drgNew to run in any MonadRandom, providing cascading initialization
* Remove Crypto.PubKey.HashDescr in favor of just having the algorithm
  specified in PKCS15 RSA function.
* Fix documentation in cipher sub section (Luke Taylor)
* Cleanup AES dead functions (Luke Taylor)
* Fix Show instance of Digest to display without quotes similar to cryptohash
* Use scrubbed bytes instead of bytes for P256 scalar

## 0.2

* Fix P256 compilation and exactness, + add tests
* Add a raw memory number serialization capability (i2osp, os2ip)
* Improve tests for number serialization
* Improve tests for ECC arithmetics
* Add Ord instance for Digest (Nicolas Di Prima)
* Fix entropy compilation on windows 64 bits.

## 0.1

* Initial release
