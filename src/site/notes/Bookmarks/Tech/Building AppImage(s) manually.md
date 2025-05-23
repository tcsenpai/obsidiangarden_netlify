---
{"dg-publish":true,"permalink":"/bookmarks/tech/building-app-image-s-manually/","tags":["linux","tutorial"]}
---


ithub

# Building AppImage(s) manually

# [docs.appimage.org/source/packaging-guide/manual.rst at master · AppImage/docs.appimage.org · GitHub](https://github.com/AppImage/docs.appimage.org/blob/master/source/packaging-guide/manual.rst1)

Create an AppDir manually, then turn it into an AppImage. Start out with the example below, then check the examples on bundling certain applications or type of applications as AppImages from the right-hand side **"Pages"** menu.

Contents

In practice, you will probably never do this by hand. So this is mainly to illustrate the concept.

Create an AppDir structure that looks (as a minimum) like this:

```
MyApp.AppDir/
MyApp.AppDir/AppRun
MyApp.AppDir/myapp.desktop
MyApp.AppDir/myapp.png
MyApp.AppDir/usr/bin/myapp
MyApp.AppDir/usr/lib/libfoo.so.0

```

The `AppRun` file can be a script or executable. It sets up required environment variables such as `$PATH` and launches the payload application. You can write your own, but in most cases it is easiest (and most error-proof) to use a precompiled one from this repository.

Of course you can leave out the library if your app does not need one, or if all libraries your app needs are already contained in every base operating system you are targeting.

Your binary, myapp, must not contain any hardcoded paths that would prevent it from being relocateable. You can check this by running

```
strings MyApp.AppDir/usr/bin/myapp | grep /usr
```

Should this return something, then you need to modify your app programmatically (e.g., by using relative paths, using [binreloc](https://github.com/limbahq/binreloc), or using `QString QCoreApplication::applicationDirPath()`).

If you prefer not to change the source code of your app and/or would not like to recompile your app, you can also patch the binary, for example using the command

```
sed -i -e 's#././' MyApp.AppDir/usr/bin/myapp
```

This usually works as long as the application is not doing a `chdir()` which would break this workaround, because then `././` would not be pointing to `$APPDIR/usr` any more. You can run the following command to see whether the application is doing a `chdir()` (99% of GUI applications don't)

```
strace -echdir -f ./AppRun
```

Also see:[https://www.gnu.org/software/gnulib/manual/html_node/Supporting-Relocation.html](https://www.gnu.org/software/gnulib/manual/html_node/Supporting-Relocation.html)

It has been a pain for many users of GNU packages for a long time that packages are not relocatable. The relocatable-prog module aims to ease the process of making a GNU program relocatable.

Note

The same is true for any helper binaries and/or libraries that your app depends on. You check this and patch it with

```
cd MyApp.AppDir/usr/
find . -type f -exec sed -i -e 's#././' {} \;cd -
```

which replaces all occurrences of `/usr` with `././`, which simply means "here".

myapp.desktop should contain (as a minimum):

```
[Desktop Entry]Name=MyApp
Exec=myapp
Icon=myapp
Type=Application
Categories=Utility;
```

Be sure to pick one of the [Registered Categories](https://standards.freedesktop.org/menu-spec/latest/apa.html), and be sure that your desktop file passes validation by using `desktop-file-validate your.desktop`. If you are not deploying an application with a graphical user interface (GUI) but a command line tool (for the terminal), make sure to add `Terminal=true`.

To create an AppImage, run `appimagetool` on the AppDir in order to turn it into an AppImage. You can get it from this repository's [Releases](https://github.com/AppImage/AppImageKit/releases) page (it comes as an AppImage itself; yes, we eat our own dogfood).

‍
