# flatpak-gnuradio
To build GNU Radio in a Flatpak environment, use `flatpak-builder` in the base directory. It will also download and build all dependencies.

```
flatpak-builder build-dir org.gnuradio.GnuRadio.yml
```

To install the resulting package directly for the current user:

```
flatpak-builder --force-clean build-dir org.gnuradio.GnuRadio.yml --install --user
```

To generate the single file flatpak-bundle, you need to build into a local repository first, afterwards you can create the bundle `gnuradio.flatpak`.
```
flatpak-builder --repo=repo --force-clean build-dir org.gnuradio.GnuRadio.yml
flatpak build-bundle repo gnuradio.flatpak org.gnuradio.GnuRadio
```