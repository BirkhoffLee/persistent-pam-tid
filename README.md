# persistent-pam-tid (not so persistent)

macOS automatically resets `/etc/pam.d/sudo` to its default state after each system upgrade. This launchd configuration adds pam_tid.so to `/etc/pam.d/sudo` at startup if not present.

Blog post: [Persistent sudo Touch ID Authentication on macOS](https://birkhoff.me/Persistent-sudo-Touch-ID-Authentication-on-macOS/)

Only works for macOS Big Sur and below (not from Monterey; see [issue #1](https://github.com/BirkhoffLee/persistent-pam-tid/issues/1#issuecomment-993465772))

## Installation

```console
git clone https://github.com/BirkhoffLee/persistent-pam-tid.git
sudo cp persistent-pam-tid/pam-tid-installer /usr/local/bin/
sudo cp persistent-pam-tid/me.birkhoff.persistent_pam_tid.plist /Library/LaunchDaemons/
sudo chown root:wheel /Library/LaunchDaemons/me.birkhoff.persistent_pam_tid.plist
sudo launchctl load -w /Library/LaunchDaemons/me.birkhoff.persistent_pam_tid.plist
```

## Uninstalling

```console
sudo rm /usr/local/bin/pam-tid-installer
sudo rm /Library/LaunchDaemons/me.birkhoff.persistent_pam_tid.plist
```

## Disclaimer

Only use codes in this repository if you absolutely understand what it means and what it does. Everything in this project has been tested on my machine and clean macOS virtual machines. I take no responsibility and bear no culpability if anything breaks on your machine after using any piece of code in this repo.

## LICENSE

This project is released under [UNLICENSE](UNLICENSE).
