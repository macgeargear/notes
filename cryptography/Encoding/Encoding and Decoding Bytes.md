>Encoding and encryption are `not the same`

when we take about encoding, we are talking about converting raw data(binary) into a format that can be stored or transitted as text.

There're many ways to `encode` data as text. Some include
- Hexadecimal
- Base64
- ASCII

### Binary Literals in GO
```go
zeroWrittenInBinary := ob0000
fmt.Println(zeroWrittenInBinary)
// print: 0

oneWrittenInBinary := ob0000
fmt.Println(oneWrittenInBinary)

// print: 1
```

### Encoding != Encryption
---
#### Encoding
when we talk about encoding in the context of cryptography, we are talking about converting raw data (binary) into a format that can be stored or transmitted as text.

if someone gain access to encode data, they'll be able to very easily and very trivially to get the original information
#### Encryption
Encryption, on the other hand, is a secure way to transmit secret information. The critical difference is that encryption requires a key to decrypt the message. Without the key, the message is unreadable.

**Encoding in go**
```go
myData := 32

fmt.Printf("%b\n", myData)
// prints binary: 100000

fmt.Printf("%d\n", myData)
// prints decimal: 32

fmt.Printf("%x\n", myData)
// prints hexadecimal: 20
```

**Padding with zero**
When encoding data in binary, it's common to pad the data with zeroes to make it a certain length. 
Ex. if we want to encode the number `32` tin binary, we can pad it with zeroes to make it 8 bits long
```go
myData := 32

fmt.Printf("%08b\n", myData)
// prints binary: 00100000


fmt.Printf("%04x\n", myData)
// prints hexadecimal: 0020
```


#### Example
package main

```go
import (
	"fmt"
	"strings"
)

func getHexString(b []byte) string {
	res := []string{}
	for _, v := range b {
		res = append(res, fmt.Sprintf("%02x", v))
	}
	return strings.Join(res, ":")
}

func getBinaryString(b []byte) string {
	res := []string{}
	for _, v := range b {
		res = append(res, fmt.Sprintf("%08b", v))
	}
	return strings.Join(res, ":")
}

func testHex(s string) {
	myBytes := []byte(s)
	fmt.Printf("String: '%s', Hex: %v\n", s, getHexString(myBytes))
	fmt.Println("========")
}

func testBinary(s string) {
	myBytes := []byte(s)
	fmt.Printf("String: '%s', Bin: %v\n", s, getBinaryString(myBytes))
	fmt.Println("========")
}

func main() {
	testHex("Hello")
	testHex("World")
	testBinary("Hello")
	testBinary("World")
}


```


#### Decode string

```go
package main

import (
	"encoding/hex"
	"fmt"
	"strings"
)

func getHexBytes(s string) ([]byte, error) {
	final := []byte{}
	parts := strings.Split(s, ":")
	for _, v := range parts {
		dec, err := hex.DecodeString(v)
		if err != nil {
			return nil, err
		}
		final = append(final, dec...)
	}
	return final, nil
}

func testHex(s string) {
	myBytes, err := getHexBytes(s)
	if err != nil {
		fmt.Println(err)
		return
	}
	fmt.Printf("Hex: '%s', String: %v\n", s, string(myBytes))
	fmt.Println("========")
}

func main() {
	testHex("48:65:6c:6c:6f")
	testHex("57:6f:72:6c:64")
	testHex("50:61:73:73:77:6f:72:64")
}

```
