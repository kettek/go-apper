# go-apper
This is simply a repository hosting Matt Holt's gist from [here](https://medium.com/@mattholt/packaging-a-go-application-for-macos-f7084b00f6b5).

## Building

```
$ go build -o go-apper
```

## Documentation
Although I may expand upon this in the future, the following text originally written by Holt is provided below (with minor modifications).

----

Bundling the .app is the first thing it does, and creating the DMG is the
second. Making the DMG is optional, and is only done if you provide
the template DMG file, which you have to create beforehand.

Example use:

```
$ go-apper \
	-assets ./folder_with_binary_and_any_resources \
	-bin yourbinary \
	-icon ./appicon1024.png \
	-identifier com.example.whatever
	-name "My App"
	-dmg "My App template.dmg" \
	-o ~/Desktop
```

You may use this whole program or bits and pieces for whatever you want,
but it comes without warranty or support -- I have no idea what I'm doing,
as it is, so don't ask me. Sorry. But feel free to learn from it; it's a
pretty minimal automation of the whole process for simple, single-binary
applications that aren't native Cocoa, and I think I would have found
this helpful to have when I was trying to figure it out.

NOTE: This program *very likely has obvious bugs*. Feel free to suggest
improvements to this gist and comment below, but I don't make any
guarantees; it worked for me and you're on your own beyond that.

I learned from these pages/posts - thanks, whomever you may be:
  * https://developer.apple.com/library/content/documentation/Porting/Conceptual/PortingUnix/distributing/distibuting.html#//apple_ref/doc/uid/TP40002855-TPXREF101
  * https://github.com/Xeoncross/macappshell
  * https://el-tramo.be/blog/fancy-dmg/
  * https://github.com/remko/fancy-dmg/blob/master/Makefile
  * https://github.com/shurcooL/trayhost
