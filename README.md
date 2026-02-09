# Nintendo File Formats
> The documentation used to be available as a GitHub wiki, but has been moved to a static website to gain more control over the content and allow pull requests to be made.

### Documentation
https://nintendo-formats.com.

### Goals
This repository documents various file formats that are seen in Nintendo games. It is meant for people that want to build tools, create mods, mine data, or are simply curious about what's inside.

The information is provided for free and can be used for any purpose. However, consider adding a link to this repository to your credits or becoming a [sponsor](https://github.com/sponsors/kinnay).

The scope of the documentation includes all file formats that are seen in games that are published by Nintendo and exclusively available on Nintendo systems. Older systems may be added to the documentation as well.

### Contributing
Feel free to open a pull request on [GitHub](https://github.com/kinnay/Nintendo-File-Formats). Please try to follow the current style as much as possible. Here are some guidelines:
* Offset / size / description tables are the preferred way to document a file format.
* Type / description tables may be used when they are more natural for the given file format, such as when the file format has many fields with a variable length.
* The documentation should be mostly technical. It is okay to add context or textual explanations, as long as it helps people that want to write tools.
* Every page should have a title that includes a link to the library or game that the page is related to.

When a new page is created, it must be added to [SUMMARY.md](https://github.com/kinnay/Nintendo-File-Formats/blob/master/src/SUMMARY.md) (otherwise, no HTML will be generated for it). Don't forget to add new file formats to [formats.md](https://github.com/kinnay/Nintendo-File-Formats/blob/master/src/formats.md) as well.

### Communication
A Discord server can be found here: https://discord.gg/x8np6Hhxwk.

Alternatively, feel free to open a [discussion](https://github.com/kinnay/Nintendo-File-Formats/discussions) on GitHub. 
