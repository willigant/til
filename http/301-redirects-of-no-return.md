# 301 Redirects - No Turning Back
What you probably didn’t realize is that browsers cache 301 redirects 
aggressively and there is nothing short of a complete cache wipe by the user 
that you can do to re-vive a url that has been redirected

You can improve a bit on this by sending along a bunch of cache control 
headers to at least limit the damage. But that won’t change a thing for people 
that already have your old 301 cached.

If you're testing out 301 redirects and unsure, might want to take note of this
and set headers like so:
```
// cache for 100 days
Last-Modified: Fri, 19 Feb 2016 12:54:49 +0100
Expires: Sun, 29 May 2016 12:54:49 +0200

```

[cache header resource](https://www.mnot.net/cache_docs/#CONTROL)
[source](http://jacquesmattheij.com/301-redirects-a-dangerous-one-way-street)
