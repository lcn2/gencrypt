# gencrypt and gdecrypt

* gencrypt - gpg encrypt file(s)

* gdecrypt - gpg decrypt file(s)


# To install

```sh
sudo make install
```


# To use


## gencrypt - gpg encrypt file(s)

```sh
/usr/local/bin/gencrypt [-h] [-v level] [-V] [-n] [-N] [-k] [-g gpg] [-w wipe] key_name file ...

    -h          print help message and exit
    -v level    set verbosity level (def level: 0)
    -V          print version string and exit

    -n          go thru the actions, but do not update any files (def: do the action)
    -N          do not process anything, just parse arguments (def: process something)

    -k          keep encrypted file
    -g gpg      path to the gpg tool (def: )
    -w wipe     path to the wipe tool (def: )

    key_name    gpg key name to encrypt with
    file ...    file(s) to encrypt

Exit codes:
     0         all OK
     1         some internal tool exited non-zero
     2         -h and help string printed or -V and version string printed
     3         command line error
 >= 10         internal error

gencrypt version: 1.6.1 2025-03-28
```


## gdecrypt - gpg decrypt file(s)

```sh
/usr/local/bin/gdecrypt [-h] [-v level] [-V] [-n] [-N] [-k] [-g gpg] file.gpg ...

    -h          print help message and exit
    -v level    set verbosity level (def level: 0)
    -V          print version string and exit

    -n          go thru the actions, but do not update any files (def: do the action)
    -N          do not process anything, just parse arguments (def: process something)

    -k          keep encrypted file
    -g gpg      path to the gpg tool (def: )

    file.gpg ...    gpg encrypted files to decrepit

Exit codes:
     0         all OK
     1         some internal tool exited non-zero
     2         -h and help string printed or -V and version string printed
     3         command line error
 >= 10         internal error

gdecrypt version: 1.6.1 2025-03-28
```


# Examples


## gencrypt - gpg encrypt file(s)

Encrypt `file1` and `file2` using the gpg key `user@example.org`, and then wipe the original files after encrypting:

```sh
/usr/local/bin/gencrypt -v 1 user@example.org file1 file2
```

Encrypt `file3` using the gpg key `user@example.org`, but keep the original:

```sh
/usr/local/bin/gencrypt -v 1 -k user@example.org file3
```


## gdecrypt - gpg decrypt file(s)

Decrypt `file1.gpg` and `file2.gpg` and then remove the encrypted files:

```sh
/usr/local/bin/gdecrypt -v 1 file1.gpg file2.gpg
```

Decrypt `file3.gpg` and keep the encrypted file:

```sh
/usr/local/bin/gdecrypt -v 1 -k user@example.org file3.gpg
```


# Reporting Security Issues

To report a security issue, please visit "[Reporting Security Issues](https://github.com/lcn2/XXX/security/policy)".
