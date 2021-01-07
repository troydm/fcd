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
fcd() { cd "$(fcdclient "$@")"; }
```
