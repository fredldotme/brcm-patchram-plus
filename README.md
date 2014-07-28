brcm-patchram-plus
==================

Specifically meant for use with Mer.

Build:

```shell
PKG=brcm-patchram-plus
SPEC=$PKG
cd $MER_ROOT/devel/mer-hybris
git clone https://github.com/beidl/$PKG.git
cd $PKG
mb2 -s rpm/$SPEC.spec -t $VENDOR-$DEVICE-armv7hl build
mkdir -p $ANDROID_ROOT/droid-local-repo/$DEVICE/$PKG/
rm -f $ANDROID_ROOT/droid-local-repo/$DEVICE/$PKG/*.rpm
mv RPMS/*.rpm $ANDROID_ROOT/droid-local-repo/$DEVICE/$PKG
createrepo $ANDROID_ROOT/droid-local-repo/$DEVICE
sb2 -t $VENDOR-$DEVICE-armv7hl -R -msdk-install zypper ref
```
