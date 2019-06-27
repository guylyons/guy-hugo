+++
date = "2019-06-27T04:00:00+00:00"
tags = ["drupal"]
title = "Debugging Drupal 7 Templates"

+++
In the world of development, I learn something new every day and today was no exception. While I knew Drupal 8 had some handy features for debugging twig templates, which proves extremely helpful with assessing template hierarchy, I had no clue that this was also available in D7 as of 7.33.

In all its glory, add this to your settings.local.php

    $conf['theme_debug'] = TRUE;
    

<iframe src="[https://giphy.com/embed/xT0GqtcVR0jOXzmmPK](https://giphy.com/embed/xT0GqtcVR0jOXzmmPK "https://giphy.com/embed/xT0GqtcVR0jOXzmmPK")" width="480" height="270" frameBorder="0" class="giphy-embed" allowFullScreen></iframe><p><a href="[https://giphy.com/gifs/nickelodeon-nick-nicktoons-harvey-beaks-xT0GqtcVR0jOXzmmPK](https://giphy.com/gifs/nickelodeon-nick-nicktoons-harvey-beaks-xT0GqtcVR0jOXzmmPK "https://giphy.com/gifs/nickelodeon-nick-nicktoons-harvey-beaks-xT0GqtcVR0jOXzmmPK")">via GIPHY</a></p>

After adding this, open you your inspector and give it a hard reload to see all the commented helpers inserted. The link below provides a much better detail of this setting.

[https://www.drupal.org/docs/7/theming/overriding-themable-output/working-with-template-suggestions](https://www.drupal.org/docs/7/theming/overriding-themable-output/working-with-template-suggestions "https://www.drupal.org/docs/7/theming/overriding-themable-output/working-with-template-suggestions")