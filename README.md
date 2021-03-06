# calibre

## Forked Version of Calibre

### Background
The original program automatically translates non-ASCII filenames into English. In my case, all Chinese file names and authors are translated into Pinyin when added to my local library. 

### Changes

File: `src/calibre/db/backend.py`
Function: `construct_file_name`

```
-        author = ascii_filename(author)[:l]
-        title  = ascii_filename(title.lstrip())[:l].rstrip()
+        author = author[:l]
+        title  = title.lstrip()[:l].rstrip()
```

### Recompiling:
After changing the code, run 
1. `cd src && python2 -O -m compileall .` 
2. Update: `cp ./calibre/db/backend.pyo /Applications/calibre.app/Contents/Resources/Python/site-packages/calibre/db/backend.pyo`

### Tested Platform
macOS Catalina 10.15.3
### Reference
[calibre修改倉庫存儲的文件名支持中文](https://www.jianshu.com/p/e108807318e8)

## Original README page
<img align="left" src="resources/images/lt.png?raw=true" height="200" width="200"/>

calibre is an e-book manager. It can view, convert, edit and catalog e-books 
in all of the major e-book formats. It can also talk to e-book reader 
devices. It can go out to the internet and fetch metadata for your books. 
It can download newspapers and convert them into e-books for convenient 
reading. It is cross platform, running on Linux, Windows and macOS.

For more information, see the [calibre About page](https://calibre-ebook.com/about)

[![Build Status](https://github.com/kovidgoyal/calibre/workflows/Continuous%20Integration/badge.svg)](https://github.com/kovidgoyal/calibre/actions?query=workflow%3ACI)

## Screenshots  

[Screenshots page](https://calibre-ebook.com/demo)

## Usage

See the [User Manual](https://manual.calibre-ebook.com)

## Development

[Setting up a development environment for calibre](https://manual.calibre-ebook.com/develop.html)

A [tarball of the source code](https://calibre-ebook.com/dist/src) for the 
current calibre release.

## Bugs

Bug reports and feature requests should be made in the calibre bug tracker at [launchpad](https://bugs.launchpad.net/calibre).
GitHub is only used for code hosting and pull requests.

## Support calibre

calibre is a result of the efforts of many volunteers from all over the world.
If you find it useful, please consider contributing to support its development.
[Donate to support calibre development](https://calibre-ebook.com/donate).

## Building calibre binaries

See [Build instructions](bypy/README.rst) for instructions on how to build the
calibre binaries and installers for all the platforms calibre supports.
