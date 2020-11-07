---
layout: post
title: "Redirection using HTML instead of Javascript"
date: 2020-11-07 08:11
---

Looking through the [HTML specification](https://www.w3.org/TR/WCAG20-TECHS/H76.html), I recently found a very interesting way to redirect a page automatically using a meta tag.
In the past, when I have worked on vanilla Javascript based frontends, I have always relied on Javascript to handle this. However, if a user has Javascript disabled, then one has to rely on the noscript tag to let them know they need to enable it.
However, if you own mutliple domains, one which might be better known but not the current location of your site, it is important that a user be redirected seamlessly so that they do not have a poor experience.
The way you can acomplish this is using the HTML meta tag for _refresh_ and then specify the content exactly as follows where you indicate the time to redirect and the site to redirect to.

```html
 <meta http-equiv="refresh" content="0;URL='https://williambarela.com/'" />
```

So, this is a very short blog post, but I hope this will help some of you who are facing a similar situation and you would like your users to be redirected automatically.
