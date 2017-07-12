---
layout: post
title: 'How to create a post'
categories: jekyll update
featured_image: ''
comments: false
tags:
summary: 'Summary Here'
---

## Using shell script

{% highlight bash %}
function new_post() {
  cd _posts
  SLUGIFIED="$(echo -n "$1" | sed -e 's/[^[:alnum:]]/-/g' | tr -s '-' | tr A-Z a-z)"
  SLUG=$(date + "%Y-%m-%d"-$SLUGIFIED.md)
  echo -e "---\layout: post\ntitle: '$1'\nfeatured_image: ''\ncomments: false\ntags: \nsummary: 'Summary here' \n##Be Brilliant" > $SLUG
  echo $SLUG
  cd ../
}
{% endhighlight shell %}
