# Sudo-Heap-Overflow
PoC for CVE-2021-3156 (sudo heap overflow). Exploit by @gf_256 aka cts. Thanks to r4j from super guesser for help. Credit to Braon Samedit of Qualys for the original advisory.

Demo video

Important note
The modified time of /etc/passwd needs to be newer than the system boot time, if it isn't you can use chsh to update it. Unfortunately this means you will have to know the password for the account you are running as. Remember that chsh doesn't accept empty passwords by default so if it is empty you may have to set one with passwd.

Instructions
wget/curl
tune RACE_SLEEP_TIME
gcc exploit.c
cp /etc/passwd fakepasswd
modify fakepasswd so your uid is 0
./a.out
Tested on Ubuntu 18.04 (sudo 1.8.21p2) and 20.04 (1.8.31)

this bug freaking sucked to PoC, it took like 3 sisyphean days and then suddenly today I just got insanely lucky
