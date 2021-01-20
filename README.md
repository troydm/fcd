# fcd

faster cd - a simple faster cd solution written in Perl

## Installation

Make sure that you have Perl 5.10 installed and copy fcdclient and fcdserver to your $PATH and make them executable

```sh
curl -o /usr/local/bin/fcdclient https://raw.githubusercontent.com/troydm/fcd/master/fcdclient
curl -o /usr/local/bin/fcdserver https://raw.githubusercontent.com/troydm/fcd/master/fcdserver
chmod +x /usr/local/bin/fcdclient
chmod +x /usr/local/bin/fcdserver
```

Add this function to your shell profile (either .bashrc or .zshrc)

```sh
# fcd
fcd() { fcdclient "$@"; cd "$(cat /tmp/fcd_$USER)"; rm -f /tmp/fcd_$USER; }
```
## Usage

Use fcd everywhere instead of cd in your shell.

For example if your in home folder and you have Downloads folder which contains another folder called Recent,
to go into that folder just type, fcd will automatically find suitable folder based on your pattern and fill navigate you to your destination

    fcd dow rec

fcdserver is automatically started when you run fcd first time, it creates ~/.fcddump file
which contains stats about often visited directories and number of times they were visited,
this file is also used as a sort of bookmark when search for a directories

You can customize directory completion prompt using enviroment variable FCD_PROMPT, see Term::ANSIColor, default value is
```sh
export FCD_PROMPT="('rgb543 on_grey4', '  ', 'grey4', '')"
```
