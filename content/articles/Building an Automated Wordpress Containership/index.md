---
date: 2025-12-19
title: Building an Automated Wordpress Containership
description: "Building an Automated Wordpress Containership"
tags: ["articles"]
summary: ""
draft: true
---

Set up .image quadlets
Yeah you just specify the name of the .image file in the .container file
And quadlet wires it up as a dependency
Then the pull becomes the service and it doesn't time our starting the container service

Set up template files
you should prefer the template module when you're trying to control file content entirely, rather than blockinfile where you want to edit a block within a larger file that you're not trying to own with ansible

Daemon reload handler

Set up array for pod

How to run podman has another user

uid=$(id -u seal)  
sudo systemd-run --property User=seal --property Requires=user@${uid}.service --property After=user@${uid}.service --property Environment=XDG_RUNTIME_DIR=/run/user/${uid} --collect --pipe --quiet --wait podman ps

```
sudo systemd-run --property User=seal --property Requires=user@${uid}.service --property After=user@${uid}.service --property Environment=XDG_RUNTIME_DIR=/run/user/${uid} --collect --pipe --quiet --wait podman ps
```