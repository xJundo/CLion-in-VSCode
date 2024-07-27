# CLion-in-VSCode

So, you want to combine CLion's intelligence with VSCode's lightweight nature?

## Introduction

I used to work with CLion on all of my C/C++ projects, and it works perfectly. However, one thing I noticed about VSCode is that it's incredibly fast. CLion is called an intelligent IDE, so it thinks with you, but it doesn't work as fast. On the other hand, VSCode is lightweight but not intelligent.

## Description

We're going to have the same UI as in CLion within VSCode!

## Tutorial

### Disable IntelliSense of VSCode

To disable IntelliSense in VSCode, follow these steps:

1. Open VSCode.
2. Go to `File` > `Preferences` > `Settings` or press `Ctrl+,` to open the settings.
3. In the search bar, type `IntelliSense`.
4. Find the setting `C_Cpp: IntelliSense Engine` and set it to `Disabled`.

### Install CLANGD Extension on VSCode

To install the CLANGD extension, which is used for error detection and solutions (but not compilation):

1. Open VSCode.
2. Go to the Extensions view by clicking on the Extensions icon in the Activity Bar on the side of the window or by pressing `Ctrl+Shift+X`.
3. In the search bar, type `clangd`.
4. Click `Install` on the `clangd` extension by LLVM.

### Install Bear for Makefile Projects

If you're only using a makefile in your project, you need to install Bear. Bear is a tool that generates a compilation database for clang tooling.

1. Install Bear:
   - On Debian/Ubuntu: `sudo apt-get install bear`
   - On Fedora: `sudo dnf install bear`
   - On macOS: `brew install bear`

2. For the first `make` command, use `bear -- make` instead of just `make`.

#### Explanation

The `bear -- make` command runs your `make` command while generating a JSON compilation database. This database is used by tools like `clangd` to understand your project's build process and provide accurate diagnostics and code navigation.

### Reload the Window

To reload the VSCode window:

1. Press `Ctrl+Shift+P` to open the Command Palette.
2. Type `Reload Window` and select the `Developer: Reload Window` option.

