---
layout: post
title: "GitHub Pages with a Custom URL"
date: 2020-02-15 16:05 -0600
---

If you have ever attempted to have a custom URL for your GitHub Pages main page (gh-username.github.io) while trying to have a blog or another subsite in another GitHub repo (e.g., gh-username.github.io/blog), you know all to too well the pain of getting your paths right.

I am a Software Developer. As such, I wanted to have a custom website which I hand designed to show off my work and share with the world. I also wanted to host it on Github Pages since hosting is free and pushing out changes is easy. Lastly, I wanted to have a blog so that I can journal and share with the world (and the future me) any challenges or interesting solutions which I come accros. Such a blog had to be something that I could customize the UI on so that I could match it to my website. I could have written my own blogging site from scatch, but hey if there is a good solution out there in the wild and you don't have to reinvent the wheel, then don't, right? Jekyll of course is by far the best solution for such a blogging site since it is robust and makes it easy to have a static site which takes markdown files for your posts. No CMS needed, this makes me happy. Plus, you can host it right from GitHub as well through GitHub pages.

Nevertheless, to keep a restful structure for my site and to separate my own website from the Jekyll blog portion, there are some challenges. In this blog post, I would like to share with you some quick and easy steps which will help any developer who wishes to do the same and who is struggling with getting the paths working for their blog posts. I will start by illustrating the structure of two such repos so that you know the relevant folder in Jekyll. The structure of the main GitHub pages repo is rather irrelevant, so I include just a minimal structure so that I can reference back to sections of it in this article:

## Main GitHub Pages Repo:
```
# https://www.github.com/WilliamBarela.github.io

├── src
│   └── css
│       └── style.css
│   └── js
│       └── script.js
├── CNAME
├── index.html
├── README.md

```

## Blog Repo
```
# https://www.gitub.com/WilliamBarela/blog

├── assets
│   └── css
│       └── style.scss
├── _config.yml
├── index.html
├── _layouts
│   ├── default.html
│   └── post.html
├── _posts
│   ├── 2020-02-14-love_is_in_the_air.markdown
│   └── 2020-02-15-github_pages_subsite_with_custom_url.markdown
├── README.md

```

So, first off if you search for my website, [https://williambarela.com](https://williambarela.com "William Barela's Website") on the [WhoIs](https://who.is "Who.is domain name repository") repository, you will see that my domain name was purchased on [Namecheap](https://www.namecheap.com/ "Namecheap Domain Names"). To link this domain name to my main GitHub pages repo using HTTPS, I had to add GitHub's DNS settings on Namecheap and specify my domain name in the CNAME of GitHub (i.e., in the settings). I may write a post on that separately and link it back here at a later date. Once all of that was done, I wrote the basic landing page of my website and pushed it up to the `master` branch of my main GitHub Pages repo and set enforcement of HTTPS. Easy.

Next, I created my blog repo at [https://www.github.com/WilliamBarela/blog](https://www.github.com/WilliamBarela/blog "William Barela's Blog Repo).
But, for all repos that you wish to be hosted at GitHub Pages which are not on the main repo, you need to create a branch called `gh-pages`, push that to get GitHub and set it as the default repository. This is the only way to ensure that the content will be shown using GitHub pages.

Again, since the intent is to have the blog home page with the posts at `https://williambarela.com/blog`, a basic `index.html` which we can use is:

```
---
layout: default
title: Posts
---
{% raw %}
<h1>{{ page.title }}</h1>
<ul class="posts">

  {% for post in site.posts %}
    <li>
      <h2><span>{{ post.date | date_to_string }}</span> » <a href="{{ post.url }}" title="{{ post.title }}">{{ post.title }}</a></h2>
      <p>{{ post.excerpt | strip_html | truncatewords:40 }}</p>
    </li>
  {% endfor %}
</ul>
{% endraw %}
```

The index page of `https://williambarela.github.io/blog` will redirect to `https://williambarela.com/blog`. However, when you try to click one of the posts, the hyperlink is not correct because it is routing off of the base url of the site like this: `https://williambarela.com/2020/01/01/some_blog_title` while it should be like this: `https://williambarela.com/blog/2020/01/01/some_blog_title`.

This is because as we can see, the href for each post is pointing to post.url which expands to `/2020/01/01/some_blog_title`.
To fix this, we should set the full url in the `_config.yml` file and prepend it to the href of each post by setting the href to `{% raw %}{{ post.url | prepend:site.url }}{% endraw %}`. The changes in the `_config.yml` page which need to be made to fix this is as follows:

```yml
theme: jekyll-theme-minimal
title: "William Barela's Blogspot"
description: "williambarela.com/blog is meant to serve a treasure trove of knowledge on how to program both front-end and back-end websites, as well as provide insights into DevOps"

url: "https://williambarela.com/blog"
permalink: /posts/:year/:month/:day/:title
```

So, here we have set a site variable for the URL for our site. This will be the address which is prepended to the blog posts when set the href for the posts as follows:

```
{% raw %}
{{ post.url | prepend:site.url }}
{% endraw %}
```

And then lastly, the permalink is set to `/posts` followed by the year, month, day and title of the blog to keep a RESTful structure. So now, you have a working blog which belongs to a dedicated repo on GitHub and it serves off of your website! _Yah!_
