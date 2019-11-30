# xkeyscan

Simple script for parsing keycodes from an X-based keylogger on Linux. Requires no installation, and can run as a rootless keylogger on Linux based machines.

## Usage
```
$ python xkeyscan.py -h
Usage: python [-u] xkeyscan.py [LOGFILE]

A simple script for converting xinput output to legible keystokes.
Can process a log file directly when passed as an argument, or can
convert keystrokes in near real-time if tailing a log file.
If tailing a log file, use python's -u switch to avoid buffering.

If you have ssh'd into a box, you may not be able to use xinput. If that is the case, run export DISPLAY=:0.0.

Use xinput --list to find the keyboard device. 

Run script -c "xinput test <XID>" /dev/null > xkey.log.

Examples:
  python xkeyscan.py xkey.log (post-process log file)
  cat xkey.log | python xkeyscan.py (accept logs from stdin)
  tail -f -n +1 xkey.log | python -u xkeyscan.py (tail log file)

Type -h or --help for a full listing of options.
```
