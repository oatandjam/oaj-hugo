---
title: "Welcome to my new blog!"
date: 2021-06-04T03:39:11+02:00
draft: true
tags: 
- meta
- test 
---

![](https://share.dmca.gripe/CbfjEqPIXda2eC9Q.png)

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Phasellus finibus tortor ut molestie ultricies. Sed rhoncus, erat in ullamcorper scelerisque, ipsum sapien cursus leo, in auctor lectus mi in ligula. Quisque auctor quam non commodo sollicitudin. Sed eros odio, pretium eget risus ac, cursus blandit sem. Morbi in ipsum tortor. Suspendisse sit amet aliquet elit. Mauris lacinia in nisi vitae dictum. Cras dignissim nisl a lorem facilisis sollicitudin. Pellentesque fringilla lorem vitae nunc finibus, vitae pellentesque dui lobortis. Etiam egestas libero a ante pretium, eget aliquam elit volutpat.

Etiam consequat lacus molestie quam porttitor, non vestibulum sapien iaculis. Suspendisse sodales eu mi congue pharetra. Integer dignissim justo at urna suscipit facilisis. Donec scelerisque mauris vitae sodales venenatis. Sed sit amet velit arcu. Etiam neque elit, pellentesque quis iaculis ut, mollis vitae orci. Praesent placerat libero in nibh pellentesque posuere. Etiam quam lacus, accumsan at magna auctor, lacinia vestibulum felis. Nulla dapibus felis eget maximus volutpat. Mauris convallis nibh in quam tristique, eget vulputate odio dapibus. Nulla fringilla hendrerit tortor sit amet elementum. Sed vestibulum libero erat, et elementum tellus viverra ut. Nunc eu suscipit quam. Ut rhoncus eget ex non rhoncus.

![](https://share.dmca.gripe/1ISLV8ZvDXM7N6WM.png)

Suspendisse euismod lacus in nisi cursus, vitae tempus massa accumsan. Praesent eu euismod urna. Duis congue velit vel tortor hendrerit vestibulum. Vestibulum maximus magna magna, id porta odio elementum quis. Mauris ut libero ac magna consequat suscipit et et sapien. Class aptent taciti sociosqu ad litora torquent per conubia nostra, per inceptos himenaeos. Integer nulla arcu, viverra a libero interdum, laoreet euismod tellus. Vivamus lobortis pharetra dolor a tempus. Quisque mattis elit accumsan nisi eleifend, quis porttitor lacus egestas. Nullam ullamcorper augue ac tempus interdum. Fusce ac odio egestas, blandit massa eu, finibus lacus. Donec id erat vitae odio condimentum rhoncus. Praesent eget ligula eget libero aliquet dapibus. Curabitur varius, quam nec ullamcorper vulputate, ex orci faucibus velit, non porta orci nibh vitae dolor. Pellentesque in enim ac nisl mattis hendrerit.

# Borelis vulpa

{{< highlight python "linenos=table,hl_lines=8 15-17,linenostart=1" >}}
try:
    from rich.console import Console
    from rich.prompt import Prompt
    from rich.table import Table
    from rich import box
    import feedparser as fp
    import subprocess
except ImportError:
    print("Please make sure that all requiered dependancies are installed!")
    quit() 
# DOWNLOAD PATH
path = ("/downloads/nyaatorrents/")
try:
    nyaa_rss = fp.parse('https://nyaa.si/?page=rss')
except:
    print("Could not establish connection to nyaa.si.\nPlease make sure you are connected to the internet and try again.")
    exit()
else:
    print(nyaa_rss['feed']['link'])
    entries = nyaa_rss['entries']
    
def torrent_table():
    console = Console()
    table = Table(title = "Nyaa.si Torrents", box = box.ROUNDED)
    table.add_column(style="green")
    table.add_column("Name")
    table.add_column("Link", style = "blue")
    for entry in entries:
        table.add_row(str(entries.index(entry)),entry['title'],entry['link'])
    console.print(table)
torrent_table()

torrent_dl = Prompt.ask("Enter the the number of the torrent(s) you would like to download seperated by a comma")
torrent_dl = tuple(torrent_dl.split(","))
print(torrent_dl)
def torrent_download():
        link = (entries[int(item)]['link'])
        cmd = ("wget " +link +" -P " +path)
        subprocess.call((cmd), shell = True)
for item in torrent_dl:
    torrent_download()
print("Downloads complete!")
exit()
{{< / highlight >}}

Mauris velit dolor, efficitur a massa ornare, laoreet tristique massa. Cras a risus id sem elementum cursus. Donec dui massa, feugiat at pulvinar a, sodales et enim. Proin sed felis magna. Donec aliquet purus urna, sit amet efficitur ligula viverra eget. Quisque sed justo a leo faucibus volutpat at non ipsum. Vivamus quis cursus elit. Nunc accumsan odio et dolor finibus iaculis. Aenean consectetur fermentum justo vel posuere. Proin finibus felis at arcu tincidunt, vitae pharetra lacus dapibus. Nulla nunc massa, malesuada nec pellentesque sit amet, volutpat vel nisi. Suspendisse vehicula feugiat condimentum. Morbi malesuada vehicula tellus vitae dictum. Donec commodo sagittis nisi ut imperdiet. Mauris porta ipsum ut dictum convallis. Cras varius eget odio lacinia volutpat.

Duis non sem vel diam ultrices aliquam. Pellentesque in lectus leo. Duis non elit ac magna cursus pretium. Nulla convallis pulvinar semper. Sed pretium at nibh nec varius. Nulla in ipsum efficitur ante molestie iaculis et nec massa. Maecenas scelerisque ipsum sit amet sem condimentum, quis scelerisque justo ultrices. Aenean et pharetra augue. Praesent venenatis est eu dolor pellentesque vehicula. Vivamus ac est suscipit, semper velit nec, aliquam sem. Proin laoreet tristique arcu, at convallis nulla. Praesent diam ipsum, egestas laoreet massa et, vehicula faucibus odio. Class aptent taciti sociosqu ad litora torquent per conubia nostra, per inceptos himenaeos. Donec sollicitudin urna non condimentum semper.