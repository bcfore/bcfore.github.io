### Resume ###

I used Mac Pages to write my resume, then exported it as pdf. But doing so left the 'Title' metadata of the pdf at the old '.pages' name of the file.

To view the pdf's metadata from the command line:

```
pdfinfo my_file.pdf
```

To change the metadata from the command line, I used exiftool:

```
sudo apt install libimage-exiftool-perl
exiftool -Title="the_new_title.pdf" my_file.pdf
```
