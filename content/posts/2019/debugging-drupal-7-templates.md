+++
date = "2019-06-27T19:30:00+00:00"
tags = ["drupal", "d7"]
title = "Debugging Drupal 7 Templates"
draft = false

+++
Drupal 7.33 introduced the ability to add helpful comments to your source code for
better debugging of your templates. This is similar to how it now works in Drupal 8
with inspecting your Twig templates. I hadn't known about this feature until quite
recently, and since I still maintain some Drupal 7 sites, this feature is incredibly
helpful when trying to debug a template.

Add this line to your settings.local.php and then clear cache.

    $conf['theme_debug'] = TRUE;

![](https://media.giphy.com/media/xT0GqtcVR0jOXzmmPK/source.gif)

Simple, I know, but after adding this, open you your inspector and give it a hard reload to see all the commented helpers inserted. The link below provides a much better detail of this setting.

[https://www.drupal.org/docs/7/theming/overriding-themable-output/working-with-template-suggestions](https://www.drupal.org/docs/7/theming/overriding-themable-output/working-with-template-suggestions "https://www.drupal.org/docs/7/theming/overriding-themable-output/working-with-template-suggestions")

[https://www.drupal.org/node/1089656](https://www.drupal.org/node/1089656 "Template (theme hook) suggestions") (Template suggestions)
