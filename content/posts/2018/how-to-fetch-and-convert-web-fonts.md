---
title: "How to Fetch and Convert Web Fonts"
date: 2018-09-16T08:07:20-04:00
draft: true
hero: /images/1535602148429.png
---

Sometimes I just want to try a font before handing over my sweet sweet cash.

And if you've ever tried a live preview of a font, you've already downloaded a copy without even knowing it; it just takes a few more steps to save to disk and convert it.

# Let's get cracking.

## Tools

* Chrome or Firefox
* cURL
* Any WOFF2 > TTF conversion tool

## Asset Inspection

In Chrome we're going to open up our inspector and navigate to our `Network`
tab.

* Click `FONT` in the filters row
* Refresh your browser

You'll begin to see a list of fonts in `woff or
woff2` format. Your browser is making `GET` requests to load these assets for
you to use in your browser. And, well, anything that can be loaded in your
browser can just as well be saved to your hard drive.

* Right click the desired font
* Select Copy > copy as cURL

This will store in your clipboard something similar to below:

```bash
curl 'http://www.fake-font-foundry.com/fonts/fakey-grotesque/pro/fakey-grotesque-regular-pro.woff2' -H 'Origin: http://www.fake-font-foundry.com' -H 'Accept-Encoding: gzip, deflate' -H 'Accept-Language: en-US,en;q=0.8' -H 'User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_12_6) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/61.0.3163.100 Safari/537.36' -H 'Accept: */*' -H 'Referer: http://www.fake-font-foundry.com/css/fake-font-foundry.com?v=0.0.726' -H 'Cookie: __cfduid=dff5fc1bbbdffe9722b5a746d2235427d1506517676' -H 'Connection: keep-alive' --compressed
```

Append the switch `-O` to cURL:

```bash
curl -O ...
```

## WOFF

> "The Web Open Font Format (WOFF) is a font format for use in web pages. It was developed during 2009[3] and is now a World Wide Web Consortium (W3C) Recommendation."

[Wikipedia](https://en.wikipedia.org/wiki/Web_Open_Font_Format)
