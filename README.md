# nanobsd
Cloned from FreeBSD source partially 

# Caution
Please read the official nanobsd documents. This repository doesn't add any new feature on nanobsd.

# Background
Main motivation is to create nanobsd image for RPI4 as easy as possible.

I found one post on FreeBSD forum (https://forums.freebsd.org/threads/building-a-nanobsd-image-quickly-using-pre-compiled-binaries.43590/). The approach is very helpful to reduce the build time. The original file is located in embedded/binary_build.nano and the idea is copied into the file (embedded/no_build.nao) together with small modification. I modified the file to download the released files from FreeBSD site if DO_DOWNLOAD_RELEASE is true and files don't exist under INSTALLFILESDIR yet.

# Installation
1. Go to to the directory that contain nanobsd (/usr/src/tools/tools).
2. Rename the orignal nanobsd to nanobsd.bak.
3. Deploy this repository there.

# Build
1. Go to embedded directory under nanobsd.
2. Execute command 'sudo ../nanobsd.sh -c rpi4.cfg'.

# Note
typical_embedded in embedded/common configures some files, such as etc/rc.conf, boot/loader.conf. This function also sets root password as root, and timezone if NANO_TIME_ZONE is set.

# Limitation
Currently only one partition is allocated for nanobsd, no secondary partition is available for backup.

