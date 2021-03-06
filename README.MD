# Magisk

## How to build Magisk

#### Building has been tested on 3 major platforms: macOS, Ubuntu, Windows 10

### Environment Requirements

1. A 64-bit machine: `cmake` for Android is only available in 64-bit
2. Python 3.5+: run `build.py` script
3. Java Development Kit (JDK) 8: Compile Magisk Manager and sign zips
4. Latest Android SDK: `ANDROID_HOME` environment variable should point to the Android SDK folder
5. Android NDK: Install NDK along with SDK (`$ANDROID_HOME/ndk-bundle`), or specify custom path `ANDROID_NDK`
6. (Windows Only) Python package Colorama: Install with `pip install colorama`, used for ANSI color codes
7. (Unix only) C compiler: Build `zipadjust`. Windows users can use the pre-built `zipadjust.exe`

### Instructions and Notes
1. Magisk can be built with the latest NDK (r16 as of writing), however binaries released officially will be built with NDK r10e due to ELF incompatibilities with the binaries built from the newer NDKs.
2. The easiest way to setup the environment is by importing this folder as an Android Studio project. The IDE will download required components and construct the environment for you. You still have to set the `ANDROID_HOME` environment variable to point to the SDK path.
3. Run `build.py` with argument `-h` to see the built-in help message. The `-h` option also works for each supported actions, e.g. `./build.py binary -h`
4. Build everything with `build.py`, don't directly call `gradlew` or `ndk-build`, since most requires special setup / dependencies.
5. By default, `build.py` will build binaries and Magisk Manager in debug mode. If you want to build Magisk Manager in release mode (through the flag `--release`), you will need to place a Java Keystore file at `release_signature.jks` to sign Magisk Manager's APK. For more information, check out [Google's Official Documentation](https://developer.android.com/studio/publish/app-signing.html#signing-manually).


## License

```
Magisk, including all git submodules are free software:
you can redistribute it and/or modify it under the terms of the 
GNU General Public License as published by the Free Software Foundation, 
either version 3 of the License, or (at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program.  If not, see <http://www.gnu.org/licenses/>.
```

## Credits

**MagiskManager** (`app`)

* Copyright 2016-2017, John Wu (@topjohnwu)
* All contributors and translators on Github

**MagiskSU** (`core/jni/su`)

* Copyright 2016-2017, John Wu (@topjohnwu)
* Copyright 2015, Pierre-Hugues Husson (phh@phh.me)
* Copyright 2013, Koushik Dutta (@koush)
* Copyright 2010, Adam Shanks (@ChainsDD)
* Copyright 2008, Zinx Verituse (@zinxv)

**MagiskPolicy** (`core/jni/magiskpolicy`)

* Copyright 2016-2017, John Wu (@topjohnwu)
* Copyright 2015, Pierre-Hugues Husson (phh@phh.me)
* Copyright 2015, Joshua Brindle (@joshua_brindle)

**MagiskHide** (`core/jni/magiskhide`)

* Copyright 2016-2017, John Wu (@topjohnwu)
* Copyright 2016, Pierre-Hugues Husson (phh@phh.me)

**resetprop** (`core/jni/resetprop`)

 * Copyright 2016-2017 John Wu (@topjohnwu)
 * Copyright 2016 nkk71 (nkk71x@gmail.com)

**External Dependencies** (`core/jni/external`)

* Makefile for busybox, generated by [ndk-busybox-kitchen](https://github.com/topjohnwu/ndk-busybox-kitchen)
* Each dependencies has its own license/copyright information in each subdirectory.  
All of them are either GPL or GPL compatible.

**Others Not Mentioned**

* Copyright 2016-2017, John Wu (@topjohnwu)
