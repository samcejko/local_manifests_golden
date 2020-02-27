
# local_manifests_golden

## Building instructions

Create a folder named "lineage" in your home folder.
```
$ cd
$ mkdir lineage && cd lineage
```

Download repo tool.
```
# Debian/Ubuntu
$ sudo apt install repo

# Gentoo
$ sudo emerge dev-vcs/repo
```
or get via script
```
$ mkdir -p ~/.bin
$ PATH="${HOME}/.bin:${PATH}"
$ curl https://storage.googleapis.com/git-repo-downloads/repo > ~/.bin/repo
$ chmod a+rx ~/.bin/repo
```

To initialize LineageOS trees.
```
$ repo init -u git://github.com/LineageOS/android.git -b lineage-15.1
```

Then to sync up(this step will take long time and will download ~50GB of data).
```
repo sync
```
alternatively you can enable multi thread download using -j parameter.
```
repo sync -j8
```

After that clone this repository using this command.
```
git clone  -b lineage-15.1 https://github.com/oguzbakir/local_manifests_golden.git .repo/local_manifests
```

Then sync repos again.
```
repo sync
```

All required files will be downloaded for successful build(Don't forget to apply patches given on device tree).

