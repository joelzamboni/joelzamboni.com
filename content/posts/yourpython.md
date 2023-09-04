---
title: 'Keep Python for yourself'
date: 2021-10-24T00:00:00-04:00
draft: false
---

We often want to use Python utilities like black or newer pip versions. But we don’t necessarily contaminate our OS or other virtual environments.

A suggestion is to use a virtual environment and load it on your login without changing your shell prompt (PS1). Here is how I do on my Ubuntu.

First, you have to make sure you have the basic development packages and Python modules:

```
sudo apt install -y \
  build-essential \
  python3-dev \
  python3-pip \
  python3-venv
```

Then you can create your Python virtual environment

```
python -m venv .venv
```
Now you need to add to your .bashrc script the following lines:

Now, after reloading your .bashrc file, or logout and login in again. All the Python commands will point to the ones in your home directory.
