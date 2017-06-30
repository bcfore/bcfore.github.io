### Dev environment ###

I'm switching back and forth between my Linux laptop and an iMac (running El Capitan). I'm using Github as the go-between (hence all the small commits).


### Running on localhost:4000 ###

Run:

```
bundle exec jekyll serve
```

(or just `jekyll serve`, but running via `bundle exec` is cleaner on the iMac).

### Resume ###

I used Mac Pages to write my resume, then exported it as pdf. But doing so left the 'Title' metadata of the pdf at the old '.pages' name of the file. (It seems that the title -- not the filename -- appears in the browser when you download a file.)

To view the pdf's metadata from the command line:

```
pdfinfo my_file.pdf
```

To change the metadata from the command line, I used exiftool:

```
sudo apt install libimage-exiftool-perl
exiftool -Title="the_new_title.pdf" my_file.pdf
```

### Gemfile ###

Using the latest version (ie, 0.10.1) of rb-fsevent led to an error. I don't know the details of what this Gem does, but it's related to the watching of files. I set it to version 0.9 in the Gemfile, which resolved the problem.

### Liquid templating ###

In order to keep the selected nav link highlighted (I mean Home, Projects, Notes) I do this:

```
  <li><a href="{% link pages/projects.html %}" class="{% if page.url == '/projects' %}active{% endif %}">Projects</a></li>
```

It seems like there should be a cleaner way of doing this.
