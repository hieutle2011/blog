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

There are many types of compress file, with each type we should have different command to interact with it. To find which archive type we are working with, use `file` command.

```shell
$ file a.zip
a.zip: Zip archive data, at least v1.0 to extract

$ file b.tar
b.tar: POSIX tar archive (GNU)

$ file c.tar.gz
c.tar.gz: gzip compressed data, last modified: Tue Aug 20 04:33:47 2019, from Unix
```

Here are some most common types i've been working with recently.

### Zip

```shell
# Compress
$ zip a.zip file1 file2 file3 # from individual files

$ zip -r a.zip dir_name       # from a folder, -r = recursive

# Decompress
$ unzip -d directory a.zip
```

### Tar

```shell
# Compress
$ tar cvf b.tar file1 file2

# Decompress
$ tar xvf b.tar
```

### Tar.gz

```shell
# Compress
$ tar czvf c.tar.gz file1 file2

# Decompress
$ tar xzvf c.tar.gz
```

## Note

- **c**  compress `|` **x**  extract
- **f**  file
- **z**  gz
- **v**  verbose (optional for debugging)

- You can compress without declaring the extension **.zip**, **.tar**, or **.tar.gz**. The former will automatically put .zip into a new file, however it's not true for the laters. When in doubt of archive file type, use command `file`.

## Reference
- [familug][1]

[1]: https://www.familug.org/2012/09/nen-giai-nen-bang-command-line-trong.html