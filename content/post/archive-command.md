---
title: "Archive Command"
author: ""
type: ""
date: 2019-08-20T10:49:54+07:00
subtitle: "Quick note for compress files"
image: ""
tags: ["archive", "command", "linux"]
draft: false
---

There are many types of compress file, with each type we should have different command to interact with it. First, we find which type of file we are working with by using `file` command.

```shell
$ file a.zip
a.zip: Zip archive data, at least v1.0 to extract

$ file b.tar
b.tar: POSIX tar archive (GNU)

$ file c.tar.gz
c.tar.gz: gzip compressed data, last modified: Tue Aug 20 04:33:47 2019, from Unix
```

Here are some most common types i've been working with recently.

## Zip archive data

```shell
# Compress
$ zip a.zip file1 file2 file3

$ zip -r a.zip dir_name

# Decompress
unzip -d directory a.zip
```

## Tar archive data

```shell
# Compress
$ tar cvf b.tar file1 file2

# Decompress
$ tar xvf b.tar
```

## Tar.gz archive data

```shell
# Compress
$ tar czvf c.tar.gz file1 file2

# Decompress
$ tar xzvf c.tar.gz
```

### Note

- **c**  compress `|` **x**  extract
- **f**  file
- **z**  gz
- **v**  verbose (optional for debug purpose)

### Reference
[familug][1]

[1]: https://www.familug.org/2012/09/nen-giai-nen-bang-command-line-trong.html