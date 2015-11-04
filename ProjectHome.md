# snipstrip.py #

Tool to split comic strip images into individual rows or frames thus making it easier to read comics on handheld devices such as mobile phones, PDAs and handheld multimedia players.

For example: using this module, you can split [command\_line\_fu.png](http://xkcd.com/196/) from xkcd.com ...

[![](http://imgs.xkcd.com/comics/command_line_fu.png)](http://xkcd.com/196/)

to ...

![http://lonetwin.net/00-command_line_fu.png](http://lonetwin.net/00-command_line_fu.png)

![http://lonetwin.net/01-command_line_fu.png](http://lonetwin.net/01-command_line_fu.png)

![http://lonetwin.net/02-command_line_fu.png](http://lonetwin.net/02-command_line_fu.png)

# API Usage: #

## Initialization: ##
```
>>> from snipstrip import ComicPage
>>> p = ComicPage('some_comic.png')

To snip off the rows within the comic page ...
>>> rows = p.get_by_row()           # returns all the rows from the comic
>>> for row in rows:
...    p.page.crop(row).show()      # displays snipped rows in sequence
...

To snip the frames of any row
>>> frames = p.get_by_frame(row)    # returns all the frames from the row
>>> for frame in p.frames[row]:
...    self.page.crop(frame).show() # displays snipped frames
...

To 'parse' the entire ComicPage in one go
>>> p.process()  # call p.get_by_frame() over all p.get_by_row() rows
```
## CLI Usage: ##
```
$ python snipstrip.py <filename> [...]

where arguments are comic strip images
```

## TODO ##
  * Improved the commandline
  * Distutils-lify the module
  * Complete the dump() method to serialize the process()ed data