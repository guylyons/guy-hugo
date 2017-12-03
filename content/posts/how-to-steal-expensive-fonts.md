---
title: "How to Steal Expensive Fonts"
date: 2017-10-26T19:23:35-04:00
---

Every once in a while you need to see a font in action before you purchase it.
And a lot of sites currently allow you this ability to preview them live. This
is a great feature, not because it allows you to preview the text on the fly,
but because the font is actually available for you to download.

## Let's Begin

This is not at all a complicated process, and for our purposes we are going to
be using the following

* Chrome
* iTerm2
* cURL
* And some handy dandy woff2/ttf converters via the web

This is what I'm using, but you can easily reproduce this in your tools of
choice.

## Pick your Font Foundry

I'm not going to provide any locations to try this out at. But by and large, if
there is a font foundry using any sort of live preview of their fonts, whereby
you are able to type in text with the actual font, then you'll be in luck to
follow through with the rest of this tutorial.

## Inspector

In Chrome we're going to open up our inspector and navigate to our `Network`
tab.

* Click `font` in the filters row
* `Cmd-R` to refresh your browser

If all goes according to plan, you'll begin to see a list of fonts in `woff or
woff2` format. Your browser is making `GET` requests to load these assets for
you to use in your browser. And, well, anything that can be loaded in your
browser can just as well be saved to your hard drive.

Right click on the font that you're seeking

* Select Copy > copy as cURL

This will store in your clipboard something similar to below:

```
curl 'http://www.colophon-foundry.org/fonts/basis-grotesque/pro/basis-grotesque-regular-pro.woff2' -H 'Origin: http://www.colophon-foundry.org' -H 'Accept-Encoding: gzip, deflate' -H 'Accept-Language: en-US,en;q=0.8' -H 'User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_12_6) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/61.0.3163.100 Safari/537.36' -H 'Accept: */*' -H 'Referer: http://www.colophon-foundry.org/css/colophon-foundry.css?v=0.0.726' -H 'Cookie: __cfduid=dff5fc1bbbdffe9722b5a746d2235427d1506517676' -H 'Connection: keep-alive' --compressed
```

You'll want to modify the command with like so:

```
curl -O
```
