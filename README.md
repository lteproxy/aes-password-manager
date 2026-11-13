# AES password manager

a local command line password manager written in C++

the program stores entries in an encrypted vault file, protects the vault with a master password, and includes a password generator.
the implementation uses botan 3.11.1, which is vendored in this repository.

## features

- AES-256-GCM authenticated encryption
- PBKDF2-HMAC-SHA256 key derivation
- master password protected vault
- random salt and nonce on every save
- password generator
- local vault file
- makefile build

## build

```bash
cd AES
make
```

requires a C++20 compiler and `make`.

## usage

```bash
./passmgr init
./passmgr add github -u yourname --url https://github.com --generate
./passmgr list
./passmgr get github --show
./passmgr gen 32
```

by default, the tool uses `vault.cpm` in the current directory.
Use `--file` to choose another vault file.

## repository

```text
AES/
├── passmgr.cpp
├── Makefile
├── README.md
└── vendor/botan/
```

vault files like `vault.cpm` and the compiled `passmgr` binary are intentionally ignored by Git.

## security note

this project has not been professionally audited.

## license

this project is MIT licensed. botan keeps its own BSD license in `AES/vendor/botan`.
