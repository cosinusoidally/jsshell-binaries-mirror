# jsshell-binaries-mirror
Spidermonkey jsshell binaries (just 45.8.0esr)

## Verifying and extracting

eg for linux-x86_64:

```
$ cd linux-x86_64/
$ gpg --verify firefox-45.8.0esr.checksums.asc
gpg: Signature made Thu Mar  2 03:40:50 2017 UTC using RSA key ID 5E9905DB
gpg: Good signature from "Mozilla Software Releases <release@mozilla.com>"
gpg: Note: This key has expired!
Primary key fingerprint: 14F2 6682 D091 6CDD 81E3  7B6D 61B7 B526 D98F 0353
     Subkey fingerprint: F2EF 4E6E 6AE7 5B95 F11F  1EB5 1C69 C4E5 5E99 05DB
$ sha512sum jsshell-linux-x86_64.zip
a62c6fa15e46de1099b989ea664356cedfe47042f98dec62c0f302a59039f075ca1347089a5eec0961c38bdedc06625fcae96f5394833c2a7926c0980f45ad47  jsshell-linux-x86_64.zip
$ grep a62c6fa15e46de1099b989ea664356cedfe47042f98dec62c0f302a59039f075ca1347089a5eec0961c38bdedc06625fcae96f5394833c2a7926c0980f45ad47 firefox-45.8.0esr.checksums
a62c6fa15e46de1099b989ea664356cedfe47042f98dec62c0f302a59039f075ca1347089a5eec0961c38bdedc06625fcae96f5394833c2a7926c0980f45ad47 sha512 7032567 jsshell-linux-x86_64.zip
```

If gpg errors out saying it doesn't have the key you will have to get the key:

```
$ gpg --recv-key F2EF4E6E6AE75B95F11F1EB51C69C4E55E9905DB
```

If for whatever reason that command fails you can also get the key from:

```
https://archive.mozilla.org/pub/firefox/releases/45.8.0esr/KEY
```

Simply extract with ``unzip`` (or whatever your platform uses to extract zip files).

To run on Linux you will need to set your ``LD_LIBRARY_PATH``
```
export LD_LIBRARY_PATH=${PWD}
```

and then just run ``./js``

On windows you just run ``js.exe``
