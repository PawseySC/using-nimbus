---
title: "Cloud best practices"
teaching: 10
exercises: 0
questions:
- "What's the best way to use cloud?"

---

1. **Snapshot your instance!**

    This saves your Root Disk and allows you to launch a fully configured instance with all packages already installed

2. **Document your steps so you know what you did**

    Create a configuration script, save a copy out of the cloud and keep it up to date
    history -> prints all previous commands
    history  |  keyword -> searches a specific command

3. **Update! Every time you login!**

    ```sudo apt-get update && sudo apt-get dist-upgrade```-> updates packages and security
    Older versions of packages and operating systems eventually lose support from their creators

4.  **Be Green and keep it elastic**

    The cloud still uses electricity and is shared, when you’re no longer using it -> turn it off!


## To get access: https://apply.pawsey.org.au
