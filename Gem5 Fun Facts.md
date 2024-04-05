Fun things about the gem5 project I randomly discovered.

# Can't UTF-8 in README

The whole universe knows the python interpreter is embedded into the compiled gem5 binary. But did you know that while building the gem5 binary, even the `README.md` file is turned into a `.py` file.

And as all sane readme files are encoded in UTF-8 and as all UTF-8 characters are converted to their ASCII equivalents when building the binary, there is a slight chance to encounter a character that doesn't have such an equivalent.

Emoji's for example.

So get this. If you put an emoji in your local gem5's `README.md`, you will break the build process.