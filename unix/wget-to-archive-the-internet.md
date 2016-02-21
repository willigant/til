I never realized how powerful a simple `wget` could be. You can download and transform any url to be viewed locally

```
wget --mirror -p --convert-links -D static.socialblendr.com,www.socialblendr.com -H -P ./socialblendr-recap http://socialblendr.com

```

#### Options explained:

- `-m`  mirror site (Enable infinite recursion and time-stamping. aka follow links) 
- `-p` download resources too (images, css, js, etc.)
- `–-convert-links`  after the download, convert the links in document for local viewing.
- `-D cdn.domain.com,www.domain.com` specify witch domains to follow, otherwise will follow every link from the page
- `-H` span hosts (follow other domains too)
- `-P ./LOCAL-DIR`  save all the files and directories to the specified directory.

##### Other options
- `--no-cache`  get the real object, do not return server cached object
- `-e robots=off`  disregard robots and no-follow directions
- `-o site1.log`  log to file site1.log
- `-U "Mozilla/5.0"`  optional: fake the user agent - useful if server returns different data for different browser
