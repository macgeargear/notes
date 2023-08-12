Keys are typically encoded in software as raw binary data. 
in Golang

```go
[]byte{0xAA, oxBB}
```



## Single-use Keys
### Avoid Key reuse
- Keys can be used many time but it was not good practice. single-use keys are often the most secure.
- the biggest problem with single-use keys is that it's hard to remember a new key for each message, so it can be inconvenient.
#### KEY TAKEAWAYS
1. Using a key more than once adds security risks. That doesn't mean you should never reuse a key, but you should be aware of the risks.
2. We can't always use single-use keys, sometimes we need to use a key. For example, if two parties need to share a key, they probably can't generate a new key every time they need to use it.
3. If a key doesn't need to be remembered by a human, you can make it long and random. We only use short, less secure passwords when humans need to remember them.
4. Humans kind of suck. They make security hard.
