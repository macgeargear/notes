## Symmetric encryption
- should be used to encrypt information for oneself.
- if you're encrypting data for someone else, you should use `asymmetric encryption`.
	 - bc. you maybe don't have a way to securely transport the key to another person
	 - when use `asymm`, the decrypter will only be able to decrypt, so they can't modify the information in any way.

- `symm` is typically faster then `asymm` and it's easier to impl
Ex. if you encrypt your computer's hard-drive, it's probably done with symmetric encryption because it can be done quick on large amounts of data;

>Q: Symmetric encryption involves how many keys?
>A: 1


>Q: Which is typically faster at encrypting and decrypting information?
>A: Symmetric Encrtyption
