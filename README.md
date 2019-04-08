
# Swift a todo o "Vapor" 🚂

The basics, Server-Side using Vapor and more 😍🎉 🚀

Swift is an open source and high-performance language with a clean and modern syntax, that offers access to C code and is **memory safe** by default. 🚨

You can find more information at [GitHub](https://github.com/apple/swift) and [Swift.org](https://swift.org/)

# Let's Start Cooking  🍰👨‍🍳👩‍🍳

## And the first ingredient is **Swift** 🥚

You can run Swift on all the operating systems, some of them easily than in others.

There are some very good articles in the internet explaining how you can get Swift working on your system, i will provide some of them and also basic instructions.

### macOS

This is the easiest one, you can get it in the nearest market, also known as AppStore 🛍

[Download Xcode from the AppStore](https://itunes.apple.com/us/app/xcode/id497799835?mt=12)

Now launch Xcode create a new playground and get ready to have some fun 🎮🎳

### Linux

Unfortunately, only Ubuntu 14.04, 16.04 or 18.04 (64-bit), is fully supported by the community.

Let's install the swift dependencies

> apt-get install clang libicu-dev libpython2.7

Now download the swift 5.0 DEVELOPMENT toolchain version specific to your system and the corresponding signature, from the [swift.org downloads page](https://swift.org/download/#snapshots).

Download and import PGP keys into your keyring

> wget -q -O - https://swift.org/keys/all-keys.asc | gpg --import -

Assmuning your download goes to the downloads folder in your system, i will provide basic commands to setup the swift toolchain that you just downloaded.

```
cd ~/Downloads
gpg --verify swift-<VERSION>-<PLATFORM>.tar.gz.sig
tar xzf swift-<VERSION>-<PLATFORM>.tar.gz
sudo cp -r swift-<VERSION>-<PLATFORM>/usr /usr
```

### Windows

It is possible to run Swift on Windows, although not as easy as for Linux or macOS, of course.

https://swiftforwindows.github.io/


