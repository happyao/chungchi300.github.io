---
layout: post
title: >-
  Few command and knowledge you need to know to do 99% job what you want yum to
  do on centos7.
category: Linux
keywords: null
---

# Before Reading(Before Reading)

1.  What you can learn after reading this article? commands and basic knowledge to use yum
2.  How much time you will use for reading this article? minutes minutes 25minutes

# What is yum?repo?package?version?

* **Yum** is a command in centos to install software.
* **Repo** is a remote file server that hold the software in binary form.
* **Package** is the software you want to install
* **Version** is the software version

# Frequent Commands

* **Add Repo**[How To Install EPEL Repo on a CentOS and RHEL 7.x](http://www.cyberciti.biz/faq/installing-rhel-epel-repo-on-centos-redhat-7-x/)

* **List Repo**[CentOS / RHEL: List All Configured Repositories](https://www.cyberciti.biz/faq/centos-fedora-redhat-yum-repolist-command-tolist-package-repositories/)

* **List version of package and install specific version of package**[How can I instruct yum to install a specific version of package X? - Unix & Linux Stack Exchange](https://unix.stackexchange.com/questions/151689/how-can-i-instruct-yum-to-install-a-specific-version-of-package-x)

* **Install software for specific repo** ![](/blog_accessary/blog_images/moved_from_atom/Image Capture 2.png) ![](/blog_accessary/blog_images/moved_from_atom/Image Capture.png) P.S Yum Select Non-conflict Package if Base Repo Is Disabled(if Base Is Enable,it More Prefer the Conflict One)
