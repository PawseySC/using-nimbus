---
title: "Maintaining your instance"
teaching: 0
exercises: 0
questions:
- "How do you keep your VM up to date and safe?"
objectives:
- ""
keypoints:
- ""
---

| ```sudo``` | Prefix command used to allow ‘super’ privileges to make administrative changes |
| ```sudo  apt-get  install <package_name>``` | Install packages available within your selected Linux distribution's software package repository
| ```sudo  apt-get  update``` | Update all installed packages info (from the repository)|
| ```sudo  apt-get  upgrade``` | Upgrade all installed packages |
| ```sudo  apt-get  dist-upgrade``` | Upgrade all installed packages and handle dependancies |


Ideally you can combine all this ```sudo apt-get update && sudo apt-get dist-upgrade```

This will keep your VM up to date.
