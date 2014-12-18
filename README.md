# Euclidean #

This is the official manifest of EuclideanROM.

## Downloading the source ##

[Repo](http://source.android.com/source/developing.html) is a tool provided by Google that
simplifies using [Git](http://git-scm.com/book) in the context of the Android source.

### Installing Repo ###

```bash
# Make a directory where Repo will be stored and add it to the path
$ mkdir ~/bin
$ PATH=~/bin:$PATH

# Download Repo itself
$ curl https://storage.googleapis.com/git-repo-downloads/repo > ~/bin/repo

# Make Repo executable
$ chmod a+x ~/bin/repo
```

### Initializing Repo ###

```bash
# Create a directory for the source files
# This can be located anywhere (as long as the fs is case-sensitive)
$ mkdir WORKSPACE
$ cd WORKSPACE

# Install Repo in the created directory
# Use a real name/email combination, if you intend to submit patches
$ repo init -u https://github.com/EuclideanROM/platform_manifest -b psoa_r2
```

### Downloading the source tree ###

This is what you will run each time you want to pull in upstream changes. Keep in mind that on your
first run, it is expected to take a while as it will download all the required Android source files
and their change histories.

```bash
# Let Repo take care of all the hard work
$ repo sync -c -jx
```

where x is the number of jobs e.g. -j4 and -c syncs only the specified branch

## Building ##

```bash
# Go to the root of the source tree...
$ cd WORKSPACE
$ ./rom-build.sh DEVICE
```
## NOTES ##

We have pngcrusher tool. That will reduce the build size, but we'll have to install the following tools:

```bash
$ sudo apt-get install pngquant
$ sudo apt-get install pngcrush
$ sudo apt-get install optipng
```
