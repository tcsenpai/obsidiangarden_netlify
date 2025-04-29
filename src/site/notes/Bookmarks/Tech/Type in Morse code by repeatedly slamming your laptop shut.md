---
{"dg-publish":true,"permalink":"/bookmarks/tech/type-in-morse-code-by-repeatedly-slamming-your-laptop-shut/","tags":["halloffame","interesting","weird"]}
---


# [tcsenpai/open-and-shut: Type in Morse code by repeatedly slamming your laptop shut - open-and-shut - GiTCSenpai - Powered by Gitea](https://git.tunnelsenpai.win/tcsenpai/open-and-shut)

Type in Morse code by repeatedly slamming your laptop shut[](https://git.tunnelsenpai.win/tcsenpai/open-and-shut)
hub

Original: [GitHub - veggiedefender/open-and-shut: Type in Morse code by repeatedly slamming your laptop shut](https://github.com/veggiedefender/open-and-shut/)

- [Features]()
- [Setup]()
  - [Dependencies]()
  - [Installation]()
  - [Configure acpid]()
  - [Disable screen lock]()

Type in Morse code by repeatedly slamming your laptop shut

[![4e2082de81ad010d5ef022b423e74a24_MD5 1.gif](/img/user/_resources/4e2082de81ad010d5ef022b423e74a24_MD5%201.gif)](https://youtu.be/UAQ60P61vYw)

## Features

- Use a battle-tested encoding trusted by pilots, submariners, and amateur radio nerds
- Type at 100+ words per ~~minute~~ hour
- Innovative [SIGTERM-based concurrency control](https://github.com/veggiedefender/open-and-shut/blob/master/morse_code_close.sh). Semaphores _who??_
- Closing your laptop now types the letter E instead of locking

## Setup

Note: For wayland support, check out the [`wayland` branch](https://github.com/veggiedefender/open-and-shut/tree/wayland).

### Dependencies

### Installation

Clone this repository and copy files into `/etc/acpi`

```
git clone git@github.com:veggiedefender/open-and-shut.git
sudo cp morse_code_close.sh morse_code_open.sh morse_code_acpi.sh /etc/acpi/

```

### Configure acpid

Acpid needs to know how and when to run our scripts. Create a file `/etc/acpi/events/lm_lid` with the following contents:

```
event=button/lid.*
action=/etc/acpi/morse_code_acpi.sh

```

### Disable screen lock

**Temporarily:** Run `systemd-inhibit --what=handle-lid-switch cat` and press Ctrl+C when you're done.

**Permanently:** Add `HandleLidSwitch=ignore` to `/etc/systemd/logind.conf` and either run `sudo systemctl restart systemd-logind.service` (this will log you out), or reboot your computer.
