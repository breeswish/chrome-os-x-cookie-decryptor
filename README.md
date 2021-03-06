chrome-os-x-cookie-decryptor
============================

Decrypt cookie values from Chrome OS X database.

## Dependencies

[NSS](https://developer.mozilla.org/en-US/docs/Mozilla/Projects/NSS)

Install dependencies via Homebrew:

```bash
brew install nss
```

## Build

```bash
g++ decryptor.cpp -I/usr/local/opt/nspr/include/nspr -I/usr/local/opt/nss/include/nss -L/usr/local/opt/nspr/lib -L/usr/local/opt/nss/lib -lnspr4 -lnss3 -o decryptor
```

## Usage

```bash
decryptor encrypted_blob chrome_master_key
```

## Example

```bash
./decryptor "`echo -e "\x76\x31\x30\xe9\xfb\xa2\x56\xb9\xaf\x2e\x15\x4c\x27\xca\xe1\x5d\xd5\xce\xb7"`" "pnEJCoY/wk62HRX0MGggkQ=="
# => 140771623
```

## Extract Chrome master key from keychain

```bash
security find-generic-password -ga "Chrome"
```
