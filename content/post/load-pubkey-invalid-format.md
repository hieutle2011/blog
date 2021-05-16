---
title: "Load pubkey \"/root/.ssh/key.pem\": invalid format"
author: ""
type: ""
date: 2021-05-16T22:14:13+07:00
subtitle: ""
image: ""
tags: [ssh, docker]
draft: false
---

Last week, i tackled a task that required to ssh to remote server from a cron job. Identity is authenticated using PEM file. I can connect successfully from my local terminal with command.

```
$ ssh -i ~/.ssh/key.pem root@host
```

My PEM file format is as such

```
-----BEGIN RSA PRIVATE KEY-----
[actual key]
-----END RSA PRIVATE KEY-----
```

The problem happened when cron job (running within a docker container) try to ssh, there is **Load pubkey "/root/.ssh/key.pem": invalid format** warning which prevented the job to finish.

By docker-compose exec inside the docker, running ssh command let me logging into the remote machine, but still the `invalid format` warning.

```
/app # ssh -i ~/.ssh/key.pem root@host
load pubkey "/root/.ssh/key.pem": invalid format
Welcome to Ubuntu 18.04.4 LTS (GNU/Linux 4.15.0-91-generic x86_64)

Last login: Fri May 14 13:01:58 2021 from 172.1.1.1
root@host:~#
```

That leads me to a vital clue that the issue might lie in the ssh client used to connect to remote server.


```
# My local terminal
$ ssh -V
OpenSSH_8.1p1, LibreSSL 2.7.3

# Inside docker
/app # ssh -V
OpenSSH_8.3p1, OpenSSL 1.1.1g  21 Apr 2020
```

Actually i have no idea what's the difference between the two versions and after googling for a while, i found the solution: the new format. More information can be found [here][link].

```
-----BEGIN OPENSSH PRIVATE KEY-----
[actual key]
-----END OPENSSH PRIVATE KEY——
```

The way is to convert the old format to the new one my running this command (which replace the old file!)

```
$ ssh-keygen -p -f /root/.ssh/key.pem -N '' -P ''
```

It might be a simple solution for a much more complicated issue, but i'm happy with the result as it works!

**Note**: another solution to the same issue can be found [here][pub]

[link]: https://github.com/git-for-windows/git/issues/2743#issuecomment-657847291
[pub]: https://joshtronic.com/2020/06/28/load-pubkey-invalid-format-when-using-ssh/