# freeswitch-sounds

Debian packages for freeswitch-sounds and moh files.

## Building ([adapted from fs wiki](https://wiki.freeswitch.org/wiki/Debianbuild2))

### freeswitch-sounds-en-us-callie

```bash
cd $BUILDDIR
git clone https://github.com/traviscross/freeswitch-sounds.git
cd freeswitch-sounds
./debian/bootstrap.sh -p freeswitch-sounds-en-us-callie
./debian/rules get-orig-source
tar -xv --strip-components=1 -f *_*.orig.tar.xz && mv *_*.orig.tar.xz ../
dpkg-buildpackage -uc -us -Zxz -z9
```

### freeswitch-music-default

```bash
cd $BUILDDIR
rm -rf freeswitch-sounds
git clone https://github.com/traviscross/freeswitch-sounds.git
cd freeswitch-sounds
./debian/bootstrap.sh -p freeswitch-music-default
./debian/rules get-orig-source
tar -xv --strip-components=1 -f *_*.orig.tar.xz && mv *_*.orig.tar.xz ../
dpkg-buildpackage -uc -us -Zxz -z9
```

