# firebase-scrypt-python

[![PyPi](https://img.shields.io/pypi/v/firebase-scrypt.svg)](https://pypi.python.org/pypi/firebase-scrypt/)
[![PyPI - Status](https://img.shields.io/pypi/status/firebase-scrypt)](https://pypi.python.org/pypi/firebase-scrypt/)
[![Python Versions](https://img.shields.io/pypi/pyversions/firebase-scrypt.svg)](https://github.com/nhairs/firebase-scrypt-python)
[![License](https://img.shields.io/github/license/nhairs/firebase-scrypt.svg)](https://github.com/nhairs/firebase-scrypt-python)

Python implementation of Firebase's scrypt password hashing algorithm. Based on [firebase/scrypt](https://github.com/firebase/scrypt).

This is a fork of [Jaakkol/firebase-scrypt-python](https://github.com/JaakkoL/firebase-scrypt-python) to allow packaging for PyPI.

## Installation
### Install via pip
```shell
pip3 install firebase-scrypt
```

## Usage

```python

import firebase_scrypt

# Sample Password hash parameters from Firebase Console.
salt_separator = "Bw=="
signer_key = "jxspr8Ki0RYycVU8zykbdLGjFQ3McFUH0uiiTvC8pVMXAn210wjLNmdZJzxUECKbm0QsEmYUSDzZvpjeJ9WmXA=="
rounds= 8
mem_cost=14

# Exported user user accounts salt and password hash.
salt = "42xEC+ixf3L2lw=="
password_hash="lSrfV15cpx95/sZS2W9c9Kp6i/LVgQNDNC/qzrCnh1SAyZvqmZqAjTdn3aoItz+VHjoZilo78198JAdRuid5lQ=="

# User's plain text password
password = "user1password"

is_valid = firebase_scrypt.verify_password(
    password=password,
    known_hash=password_hash,
    salt=salt,
    salt_separator=salt_separator,
    signer_key=signer_key,
    rounds=rounds,
    mem_cost=mem_cost
)

is_valid # True / False

```

## Bugs, Feature Requests etc
TLDR: Please [submit an issue on github](https://github.com/nhairs/firebase-scrypt/issues).

In the case of bug reports, please help me help you by following best practices [1](https://marker.io/blog/write-bug-report/) [2](https://www.chiark.greenend.org.uk/~sgtatham/bugs.html).

In the case of feature requests, please provide background to the problem you are trying to solve so to help find a solution that makes the most sense for the library as well as your usecase.

## Development
The only development dependencies are bash and docker. All actions are run within docker for ease of use. See `./dev.sh help` for commands. Typical commands are `format`, `lint`, `test`, `repl`, `build`.

## Licence
This project is licenced under the MIT Licence - see [`LICENCE`](https://github.com/nahirs/firebase-scrypt-python/blob/master/LICENCE).

This project may include other open source licenced software - see [`NOTICE`](https://github.com/nhairs/firebase-scrypt-python/blob/master/NOTICE).


## Authors
- Nicholas Hairs - [www.nicholashairs.com](https://www.nicholashairs.com)
- [Jaakko Laurila](https://github.com/JaakkoL)
