# ProtoBot

Arduino library for the MicroBots ProtoBot robot (CodeCell ESP32-C6 + DriveCell motors).

## Syncing changes to the installed library

The Arduino IDE builds from the installed copy at `~/Documents/Arduino/libraries/ProtoBot/`, not from this repo. It is a plain copy, not a symlink, so edits here do not reach the robot until they are copied over.

After changing anything in `src/`, copy it to the installed library:

```bash
cp src/* ~/Documents/Arduino/libraries/ProtoBot/src/
```

Check the two are in sync:

```bash
diff -rq src ~/Documents/Arduino/libraries/ProtoBot/src
```

## Building

Compile an example against the installed library (what the IDE uses):

```bash
arduino-cli compile -b esp32:esp32:esp32c6 examples/00_Default
```

Passing `--library "$PWD"` builds against this repo instead, which can hide an out-of-date installed copy.
