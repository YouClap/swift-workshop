
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

Now is where you need the blender and all the wooden spoon 🤣

Unfortunately, only Ubuntu 14.04, 16.04 or 18.04 (64-bit), is fully supported by the community.

Let's install the swift dependencies

> sudo apt install curl git clang libsqlite3-dev libblocksruntime-dev libncurses5-dev libicu-dev libpython2.7

Now download the swift 5.0 DEVELOPMENT toolchain version specific to your system and the corresponding signature, from the [swift.org downloads page](https://swift.org/download/#snapshots).

Download and import PGP keys into your keyring

> wget -q -O - https://swift.org/keys/all-keys.asc | gpg --import -

Assmuning your download goes to the downloads folder in your system, i will provide basic commands to setup the swift toolchain that you just downloaded.

```
cd ~/Downloads
gpg --verify swift-<VERSION>-<PLATFORM>.tar.gz.sig
tar xzf swift-<VERSION>-<PLATFORM>.tar.gz
sudo cp -r swift-<VERSION>-<PLATFORM>/usr/* /usr
```

You also have to install SourceKit-LSP. SourceKit-LSP is an implementation of language server protocol to enable features like code completion and jump to definition for Swift. Although this is a project under heavy development 🚧 with a lot of changes almost every day.

Basically you have to clone the sourcekit-lsp, build it linked to your swift instalation and copy it to a location on your path.

Those are basic instructions if you followed my instructions to setup swift for linux:

```
cd /tmp
git clone https://www.github.com/apple/sourcekit-lsp.git
cd sourcekit-lsp
swift package update
swift build -Xcxx -I/usr/lib/swift -Xcxx -I/usr/lib/swift/Block
sudo mv .build/x86_64-unknown-linux/debug/sourcekit-lsp /usr/bin
```

Now let's build the libSwiftPM.so

```
cd /tmp
git clone https://github.com/apple/swift-package-manager.git
cd swift-package-manager
swift package update
swift build -Xcxx -I/usr/lib/swift
sudo mv .build/x86_64-unknown-linux/debug/libSwiftPM.so /usr/lib/swift/linux
```

Now let's build the extension for VSCode. VSCode is an Electron app and the extension built with JavaScript, so we need node and npm installed.

If you are used to this, you may use `nvm` i assume 😅, just make sure you are using node v11 to build the extension if not (shame on you again 🤣🙃i'm kidding).

If you are not used to this and you don't have node and npm installed, you can install it with

```
curl -sL https://deb.nodesource.com/setup_11.x | sudo -E bash -
sudo apt install -y nodejs
```

Now let's build the extension and install the extension

```
cd /tmp/sourcekit-lsp/Editors/vscode
npm run createDevPackage
code --install-extension out/sourcekit-lsp-vscode-dev.vsix
```

### Windows

It is possible to run Swift on Windows, although not as easy as for Linux or macOS, of course 😁.

https://swiftforwindows.github.io/

This information was gathered from a few articles (do not blame me 🤣)

- [The best one, Google for Swift on Linux 🤣](https://www.google.com/search?q=swift+on+linux&oq=swift+on+linux)
- [Open Source Linux on Ubuntu Linux](https://medium.com/@agavatar/open-source-swift-on-ubuntu-linux-cd00e697dff0)
- [Swift for Linux](https://swift-linux.refi64.com/en/latest/)
- [Swift.org](https://swift.org/getting-started/#installing-swift)

## The Second Ingredient is **Vapor** 🍞

### macOS

I'm assuming you know what `brew` is, if you don't shame on you 🤣🙃 (i'm kidding). 
It's just the best package manager for macOS, if you don't have it 👉 https://brew.sh/

Brew to the rescue, install vapor with two simple commands

```
brew tap vapor/tap
brew install vapor/tap/vapor
```

### Linux

Unfortunately, Vapor toolbox is not compiled to work with Swift 5 yet. We will have to wait.

We will by pass this by downloading a pre-created project from a likk that i will provide later.

If you want to give a shot making Vapor working with Swift 5 on linux and sourcekit, check out those links to see if they can help you 🙂

- [Reddit with Swift, SourceKit-LSP, Vapor and VSCode](https://www.reddit.com/r/swift/comments/a1wv4h/linux_development_vscode_swift_autocompletion/)
- [Vapor macOS](https://docs.vapor.codes/3.0/install/macos/)
- [Vapor Linux](https://docs.vapor.codes/3.0/install/ubuntu/)


## Let's mix the ingredients 🥧

As Quim Barreiros says, let's use pressure cooker to see if we cook faster 🤣. 

In this case and since vapor toolbox doesn't work well with linux and swift 5, you can download the bootstrap project from [here](https://github.com/YouClap/swift-workshop/raw/master/bookstore.tar.gz)

Or if you prefer, a better way to download

```
curl -L -O https://github.com/YouClap/swift-workshop/raw/master/bookstore.tar.gz
```

And uncompress it

```
tar xfz bookstore.tar.gz
```



# About

With ❤️ from [YouClap](https://youclap.tech) [Development team](mailto://development@youclap.tech)