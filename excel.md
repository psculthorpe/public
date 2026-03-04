Open Terminal (Applications > Utilities > Terminal)

Run:

```
caffeinate
```

Nothing will appear to happen, but leave this window as it is and it will keep your Mac awake.

Open another Terminal window (Cmd-N, or Shell > New Window from menu bar)

Run:

```
brew install hashcat
```

Wait a bit and eventually you'll be back at a prompt. Close this Terminal window (keep the caffeinate one open) then open a fresh one. It's the easiest/laziest way to make the 'hashcat' command work from anywhere.

In the fresh window, with caffeinate still running in a separate window, run:

```
mkdir ~/Desktop/excelcrack
```

(makes a new folder on your desktop)

Then run:

```
cd ~/Desktop/excelcrack
```

(to move into that new folder)

Then run:

```
open .
```

(this will just open a Finder window in the new folder for you)

Drag the file I emailed to you (hash_only.txt) into this new folder.

Back in Terminal, run:

```
hashcat -m 9600 -a 3 ~/Desktop/excelcrack/hash_only.txt -1 '?l?u?d' '?1?1?1?1?1' --increment --increment-min 5 --increment-max 8
```

This starts hashcat guessing passwords against the hash file. You can press S at any time to get a status report. Or C to take a checkpoint (so you can resume from that point later). It'll keep going until it finds a match. The parameters we're sending it basically say "alphanumeric, between 5 and 8 chars". If you give the command above to AI and ask it to explain, it can rewrite bits of it if needed. Ideally though we're alphanumeric and between 5 and 8 chars.
