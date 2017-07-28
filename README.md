<h1 align="center">
  <a href="https://github.com/channable/icepeak"><img src="docs/icepeak.png" alt="Icepeak" width="256"></a>
</h1>

<p align="center">
  <a href="https://travis-ci.org/channable/icepeak"><img src="https://travis-ci.org/channable/icepeak.svg?branch=master" alt="Build Status"></a>
  <img src="https://img.shields.io/badge/license-BSD3-blue.svg" alt="BSD3 Licensed">
</p>

Icepeak is a fast json document store with push notification support.

## Disclaimer

This is alpha-quality software developed under Hackathon conditions.
Do not use it.

## Building and running Icepeak

Build with `stack build`.
Run the tests with `stack test`.
And run `icepeak` itself with `stack exec icepeak`.
Install with `stack install`

Integration tests are in `/integration-tests`.
They are stand-alone scripts that can be executed directly, e.g. `./connection_test.py`.

## Connecting a client

The websocket connection can be interactively tested with ipython.
First install the `websocket-client` library:

```bash
pip install websocket-client
ipython
```

Then create a websocket and receive the the current value at `foo`, and updates
when it is modified:

```python
import websocket
conn = websocket.create_connection("ws://localhost:3000/foo")
while True:
    result = conn.recv()
    print result
```
