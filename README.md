# pam_tid

macOS automatically resets `/etc/pam.d/sudo` to its default state after each system upgrade. This launchd configuration adds pam_tid.so to `/etc/pam.d/sudo` at startup if not present.

## Installation

```console
git clone https://github.com/BirkhoffLee/pam_tid.git
sudo cp pam_tid/pam_tid_installer /usr/local/bin/
sudo cp pam_tid/me.birkhoff.pam_tid.plist /Library/LaunchDaemons/
sudo chown root:wheel /Library/LaunchDaemons/me.birkhoff.pam_tid.plist
sudo launchctl load -w /Library/LaunchDaemons/me.birkhoff.pam_tid.plist
```

## Disclaimer

Only use codes in this repository if you absolutely understand what it means and what it does. Everything in this project has been tested on my machine and clean macOS virtual machines. I take no responsibility and bear no culpability if anything breaks on your machine after using any piece of code in this repo.

## LICENSE

This project is released under [UNLICENSE](UNLICENSE).
