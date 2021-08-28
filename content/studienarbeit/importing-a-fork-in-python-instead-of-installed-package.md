---
title: Importing a fork in Python instead of installed package
date: "2021-07-23"
tags:
  - software/python
  - -sa/processed
---

<http://stackoverflow.com/questions/23075397/python-how-to-edit-an-installed-package>

Run this in repo that uses the fork (this installs the package as a submodule):
python3 -m pip install -e git+[ssh://git@github-feudalism/feudalism/spatialmath-python.git
- egg=f-spatialmath](ssh://git@github-feudalism/feudalism/spatialmath-python.git
- egg=f-spatialmath) --upgrade

![unknown_filename.png](./_resources/Importing_a_fork_in_Python_instead_of_installed_package.resources/unknown_filename.png)

Instructions:

1.  Fork the package repo
2.  cd to own repo where you want to use the package
3.  Install the fork using the above pip install command. This creates ./src/submodule
4.  When making changes to fork:
    make changes in either
    *   the submodule folder (for immediate effect), or
    *   in the fork subdirectory + push + reinstall

