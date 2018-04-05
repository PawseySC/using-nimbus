---
title: "Maintaining your instance"
teaching: 10
exercises: 0
questions:
- "How do you keep your instance up to date and safe?"
objectives:
- ""
keypoints:
- ""
---

| ```sudo``` | Prefix command used to allow ‘super’ privileges to make administrative changes |
| ```sudo  apt-get  install <package_name>``` | Install packages available within your selected Linux distribution's software package repository
| ```sudo  apt-get  update``` | Update all installed packages info (from the repository)|
| ```sudo  apt-get  upgrade``` | Upgrade all installed packages |
| ```sudo  apt-get  dist-upgrade``` | Upgrade all installed packages (to new releases versions and updates the kernel as well. To be used with care. |


Ideally you can combine all this ```sudo apt-get update && sudo apt-get update``` and once every few month run ```sudo apt-get update && sudo apt-get dist-upgrade``` and reboot your instance, this to get the newer kernel releases.

This will keep your instance up to date.
